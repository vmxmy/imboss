# Example — Manager / eng-lead weekly report

Filled sample using [templates/weekly-report.md](../templates/weekly-report.md).

---

# Weekly Report — Payments squad — 2026-04-07

**Status:** Yellow  
**One-line:** Core Checkout is live on staging; production cutover blocked on webhook idempotency review.

**Audience:** founder  
**Author:** imboss (from eng notes)  
**Period:** 2026-03-31 → 2026-04-06

---

## Wins / outcomes

- Staging Checkout path works end-to-end with test cards (happy path recorded in Loom).  
- Reduced time-to-first-invoice prototype from “manual Notion” to automated entitlement flag.  
- Closed incident INC-20260328-02 (email spam loop) — root cause fixed, monitor added.

## Progress vs plan

| Initiative | Plan this week | Actual | Notes |
|------------|----------------|--------|-------|
| Checkout MVP | Staging complete | Done | |
| Webhook hardening | Prod-ready | 80% | Idempotency PR open |
| Dashboard seats | Start | Not started | Cut to protect Checkout |
| SOC2 questionnaire | First draft | Deferred | Per plan non-goal |

## Metrics

| Metric | Previous | Current | Window / notes |
|--------|----------|---------|----------------|
| Staging checkout success | n/a | 14/14 | Manual test cards only |
| Prod payment volume | $0 | $0 | Not live |
| p95 dashboard load | 1.8s | 1.6s | Staging, n small |

## Risks & incidents

| Item | Severity | Status | Owner |
|------|----------|--------|-------|
| Double entitlement if webhook retries | High | Mitigating | Contractor BE |
| Single owner for Stripe config | Med | Accepted (review 2026-04-20) | Founder |

## Blockers

- Need Stripe live keys in secrets manager (founder admin access).  

## Asks / decisions needed

| Ask | From | Needed by |
|-----|------|-----------|
| Approve prod cutover **after** idempotency merge, not before | Founder | 2026-04-09 |
| Confirm demo will use staging URL | Founder | 2026-04-08 |

## Next week — top 3

1. Merge idempotency + run replay drill  
2. Production cutover behind flag (5% staff only)  
3. Start seats widget only if cutover is Green  

## Cut / defer list (if capacity tight)

- Seats widget polish  
- Customer portal link  
- Any SOC2 documentation  

---

## Appendix

### Shipped detail

- PR #128 Checkout session  
- PR #131 Webhook signature verify  
- PR #134 (open) Idempotency keys  

### Notes

- Contractor offline Friday AM; async handoff doc prepared.
