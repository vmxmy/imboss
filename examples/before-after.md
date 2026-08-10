# Before / After — imboss voice

Side-by-side examples of typical agent output vs imboss.

---

## 1. Status update

### Before

> This week we worked on a lot of things. Refactored the auth module, updated dependencies, had discussions about the database, and made progress on the dashboard. Next week we will continue improving the system and potentially look at performance. Overall things are going well.

### After (imboss weekly, founder mode)

> **Status: Yellow** — dashboard demo for Friday is at risk if auth edge cases slip.  
>  
> **Wins:** Password login + session cookies live on staging; 12 invite-only testers unblocked.  
> **In progress:** Dashboard widgets (70%); remaining = empty states + CSV export.  
> **Risk:** Auth “remember me” path can issue duplicate sessions — fix before any paid user.  
> **Ask:** Confirm Friday demo is internal-only (recommend) vs investor-facing.  
> **Next week top 3:** (1) ship auth fix, (2) finish CSV export, (3) freeze scope for demo.

---

## 2. Explaining a technical choice

### Before

> We should use Kubernetes with a service mesh to ensure scalability, observability, and resilience across microservices leveraging industry best practices.

### After (imboss-explain, founder mode)

> **In one sentence:** For our current stage (one product, one region, small team), a single well-run app on a managed platform beats Kubernetes.  
>  
> **Why it matters:** K8s would add ops load you feel every week before you feel scale benefits.  
> **Recommendation:** Stay on managed containers (or even a PaaS) until we have sustained load or multi-service pain that is costing real money.  
> **Revisit if:** we need multi-region active-active, or platform fees exceed eng cost of self-managing.  
> **Risk of overbuilding now:** slower features, bus-factor on infra, false confidence.

---

## 3. Turning a fuzzy ask into a ticket

### Before

> User: “Make onboarding better.”  
> Agent: “Sure, I’ll improve the onboarding UX and add animations.”

### After (imboss-request)

> **Problem:** New users drop before first value; we don’t know if it’s confusion or trust.  
> **Outcome:** ≥40% of new signups complete “first project created” within 24h (baseline 22%).  
> **In scope:** 3-step guided path, sample project, progress checklist.  
> **Out of scope:** redesign of billing, mobile app, localization.  
> **Acceptance:**  
> - [ ] New user reaches first project with ≤3 screens  
> - [ ] Sample project loads <2s p95 on staging  
> - [ ] Event `onboarding_completed` fired once per user  
> **Open question (blocking):** Is “first project” the north-star event, or “first share link”?

---

## 4. Risk before launch

### Before

> Looks good to ship. We tested on my machine.

### After (imboss-risk, go/no-go)

> **Overall: Yellow — GO WITH ACCEPTS**  
>  
> | ID | Risk | Score | Treatment |  
> |----|------|-------|-----------|  
> | R1 | Double charge on payment retry | 9 | **Must fix** idempotency key before GO |  
> | R2 | No on-call this weekend | 6 | Accept: founder watches Slack + Stripe; rollback flag ready |  
> | R3 | Email deliverability untested | 4 | Mitigate: manual invite list only for 48h |  
>  
> **Decision:** NO-GO until R1 closed. Then GO WITH ACCEPTS on R2.

---

## Takeaway

imboss replaces **activity language** and **vague confidence** with **status, evidence, risks, and asks**.
