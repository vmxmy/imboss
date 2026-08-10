# Example — Founder mode full pass

Scenario: solo non-technical founder building a B2B waitlist + billing MVP with one contractor engineer and coding agents.

---

## 1) Raw founder input

> “Investors want a demo in three weeks. We need payments, team invites, and a prettier dashboard. Also someone said we should do SOC2. Can we just ship everything?”

---

## 2) imboss-plan (excerpt)

### Outcome

A **credible demo** of paid B2B signup → invite teammate → see usage dashboard, without over-claiming compliance.

### Recommendation

Ship a **narrow vertical slice**: Stripe Checkout + single-seat upgrade + email invite + read-only dashboard. Defer SOC2, multi-role admin, and custom branding.

### Scope

**In**

- Stripe test + live Checkout for Pro plan  
- “Invite member” email magic link (one role: member)  
- Dashboard: seats used, last 7d activity counts  

**Out**

- SOC2 / pen-test  
- SSO, RBAC matrix  
- Mobile app  
- Usage-based billing  

### Sequenced work

| Phase | Deliverable | Target | Dependencies |
|-------|-------------|--------|--------------|
| 0 | Demo script + success criteria | Day 2 | Founder |
| 1 | Checkout + webhook → entitlement | Day 10 | Stripe keys |
| 2 | Invite flow | Day 14 | Email provider |
| 3 | Dashboard read models | Day 18 | Events from 1–2 |
| 4 | Hardening + rehearsal | Day 21 | — |

### Cut list (if late)

1. Pretty charts → single number cards  
2. Live Stripe → test mode + “simulated paid” for demo  
3. Invites → pre-seeded second user  

### Risks

| Risk | Score | Mitigation |
|------|-------|------------|
| Webhook double-apply entitlement | 9 | Idempotency + manual Stripe audit script |
| Demo uses production keys on laptop | 6 | Separate demo account; no real customer data |
| SOC2 mentioned in pitch | 6 | Script line: “roadmap; not certified” |

### Decisions needed

| Decision | Recommend | By when |
|----------|-----------|---------|
| Demo on test vs live Stripe | Test mode + narrative | This week |
| Promise SOC2 timeline? | No date; “exploration” | Before investor meeting |

### Next actions

1. Founder — lock demo script (happy path only) — 48h  
2. Eng/agent — payment entitlement vertical slice — start today  
3. Founder — write one sentence on compliance posture — before deck refresh  

---

## 3) imboss-explain (SOC2, founder altitude)

**In one sentence:** SOC2 is an auditor’s attestation that your security practices match a standard — not a product feature you toggle on.

**Why it matters:** Some buyers require it; investors may ask; faking it is worse than deferring.

**Recommendation:** Do not start a full SOC2 project before first revenue and basic security hygiene (SSO later, access logs, least privilege, backups). Budget months and money when a deal requires it.

**What to say in the room:** “We’re implementing the controls that SOC2 cares about as we grow; formal audit when enterprise pipeline needs it.”

---

## 4) imboss-request (first agent ticket)

**Title:** Stripe Checkout → Pro entitlement (idempotent)

**Acceptance criteria**

- [ ] User completes Checkout and lands on `/dashboard?upgraded=1`  
- [ ] Webhook grants `plan=pro` exactly once per `checkout.session.id`  
- [ ] Replay of same webhook does not duplicate seats  
- [ ] Failed payment leaves user on free plan  
- [ ] Staging uses test keys only; keys not in git  

**Out of scope:** Customer portal, invoices PDF, usage metering.

**Agent tasks**

1. Add Checkout session creation endpoint  
2. Webhook handler with signature verify + idempotency store  
3. Minimal entitlement check on dashboard  
4. Script to list entitlements vs Stripe for manual audit  

---

## 5) What “founder mode” optimized for

- Demo outcome over feature completeness  
- Explicit **lies we will not tell** (SOC2)  
- Cut list before heroics  
- One vertical slice agents can execute without mind-reading  
