---
name: imboss-report
description: >
  Produce weekly, executive, or incident reports from notes, git history,
  chat logs, or bullet dumps. Triggers: imboss report, weekly report,
  executive summary, status update, incident report, board update.
---

# imboss-report

Convert raw activity into **stakeholder-ready reports** following [reporting.md](../../reporting.md).

## Pick a report type

| User signal | Type | Template |
|-------------|------|----------|
| “weekly”, “this week”, standup rollup | Weekly | [weekly-report.md](../../templates/weekly-report.md) |
| “exec”, “board”, “for my investor” | Executive | [executive-summary.md](../../templates/executive-summary.md) |
| outage, severity, postmortem | Incident | [incident-report.md](../../templates/incident-report.md) |
| decision needed from leadership | Decision request | [decision-request.md](../../templates/decision-request.md) |

If unclear, default to **weekly** for recurring status, **executive** for one-shot milestones.

## Process

1. Detect audience mode (founder / product / board / eng)  
2. Extract outcomes, not task lists  
3. Assign status color with reason  
4. Surface risks, blockers, and asks  
5. Fill the matching template; delete empty optional sections  
6. Keep founder weekly ≤ ~1 page  

## Input handling

Accept messy inputs:

- bullet journals, Slack paste, PR lists, commit logs, meeting notes  

Curate ruthlessly. Link out instead of dumping inventories.

## Output rules

- Headline first  
- Outcomes > activity  
- No invented metrics — mark missing data  
- **Asks** section mandatory if anything is blocked on a human  
- Match [communication.md](../../communication.md) tone  

## Incident mode extras

- User impact before internal narrative  
- Timeline with timezone  
- Working theory vs confirmed root cause — label which  
- Prevention actions with owners  

## Example invoke

> “imboss-report: weekly for founder from these notes: …”  
> “Write an executive summary of the v0.3 launch.”  
> “Draft S1 incident report from this timeline.”  
