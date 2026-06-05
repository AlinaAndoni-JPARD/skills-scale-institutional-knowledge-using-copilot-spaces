# OctoAcme — Execution & Tracking

## Purpose
Guidance for managing day-to-day execution and tracking progress toward project milestones.

## Team Rhythm
- Daily standups (15 min) — focus on progress, blockers, dependencies
- Weekly delivery sync — show progress, updates, and flagged risks
- Demo/Review at the end of each sprint or milestone

## Workflows
- Use the project board (e.g., GitHub Projects) with columns: Backlog, Ready, In Progress, In Review, QA, Done
- Pull Request workflow:
  - Small PRs (<= 400 lines when possible)
  - Include issue link and acceptance criteria in PR description
  - Run automated tests and linting in CI before requesting review
  - Require at least one approval before merging (or team-defined policy)

## Quality & Testing
- Unit tests for new logic
- Integration tests where applicable
- End-to-end smoke tests for critical flows before release
- Security scanning in CI
- Manual QA for feature acceptance when needed

## Reporting & Metrics
- Track velocity and burndown
- Monitor success metrics identified in the Project One-pager
- Use dashboards for key signals (errors, latency, usage)

## Blocker Management & Escalation

### What Constitutes a Blocker?
A blocker is any issue that prevents a team member from completing their assigned work:
- **Technical:** Build fails, infrastructure down, dependency issues
- **Process:** Missing approval, unclear requirements, pending design review
- **Resource:** Waiting for another team member, blocked on third-party response
- **External:** Vendor issue, regulatory approval, third-party API outage

### Blocker Escalation Framework

#### Level 1: Team Standup Triage (Daily)
**When:** During daily standup
**Who:** Team lead or PM facilitates
**Action:**
- Owner describes blocker and attempted resolution
- Team brainstorms quick fixes or workarounds
- If resolved → move on
- If unresolved → escalate to Level 2

**Example:**
```
Developer: "I'm blocked on the payment API integration. The vendor's staging
environment is down and they said it'll be back in 2 hours."
PM: "Can we mock the API response in the meantime to unblock other tests?"
Developer: "Good idea, I'll create mocks. That should unblock integration testing."
Resolution: No escalation needed, team solved it.
```

#### Level 2: PM Escalation (Within 4 hours)
**When:** Blocker not resolved in standup or blocks critical path
**Who:** Project Manager escalates to Product Lead and dependent teams
**Action:**
- PM creates brief escalation summary (see template below)
- PM notifies stakeholders and dependent teams
- Identify interim solutions or workarounds
- Set clear timeline for resolution

**Escalation Trigger:**
- Blocker unresolved after standup discussion
- Blocker affects critical path or release date
- Multiple team members are waiting
- External escalation required (vendor, other team)

**Example:**
```
BLOCKER ESCALATION - Level 2
Title: Database backup/restore procedure untested
Impact: Cannot deploy to production until tested and documented
Owner: DevOps team
Status: Escalating to Infrastructure Lead
Needed By: Tomorrow EOD (release is Friday)
Interim Solution: Manual backup on staging, document steps for QA review
```

#### Level 3: Sponsor-Level Escalation (Immediate)
**When:** Business-impacting issue that threatens delivery or customer SLA
**Who:** Product Lead or Project Manager escalates to Sponsor/Director
**Action:**
- Immediate notification with context and recommended actions
- Request decision on scope reduction, timeline extension, or resource reallocation
- Document decision and communicate to team

**Escalation Trigger:**
- Blocker threatens release date by >1 week
- Customer SLA or contract at risk
- Security or compliance issue
- Resource constraint requiring leadership intervention

**Example:**
```
BLOCKER ESCALATION - Level 3 (URGENT)
Issue: Key backend engineer hospitalized; no backup for critical feature
Impact: Release delayed 2+ weeks without intervention
Options:
  1. Defer non-critical feature; reduce scope
  2. Bring in contractor from vendor (cost: $15K)
  3. Ask partner team to temporarily loan engineer
Decision Needed: By tomorrow 10am
Owner: Project Manager + Sponsor
```

### Blocker Escalation Template

Copy and use when escalating:

```
BLOCKER ESCALATION

Project: [Name]
Reporter: [Your name]
Date: [Today's date]
Severity: 🔴 Critical / 🟡 High / 🟢 Medium

Blocker Title:
[Clear, concise description of what's blocked]

Detailed Description:
[What exactly is blocked? Who is affected? How long have we been blocked?]

Impact:
- Who is affected: [e.g., "Backend team, QA, release timeline"]
- Business impact: [e.g., "Release delayed 1 week"]
- Customer impact: [e.g., "Feature delayed to customers"]

What We've Already Tried:
- [Action 1 and result]
- [Action 2 and result]
- [Why those didn't work]

What We Need:
[Specific request: approval, resource, decision, etc.]

Interim Solution / Workaround:
[What can we do in the meantime while waiting?]

Timeline:
- When we discovered: [Date and time]
- How long we've been blocked: [X hours/days]
- Resolution needed by: [Specific date/time]
- Consequence if not resolved: [Impact]

Escalation Path:
- Level 1: [Team discussion outcome]
- Level 2: [Next escalation point]
- Level 3: [Sponsor/leadership if needed]

Owner: [Name] | Contact: [Slack handle, email]
```

### Blocker Tracking in Project Board

Use labels and columns to track blockers:
- Column: Create a "Blocked" column or status
- Labels: `blocker`, `critical`, `escalated`
- Example card:
  ```
  [Issue] Payment API integration blocked
  Labels: blocker, critical, escalated-to-PM
  Assigned: Alice
  Blocker Since: Jan 15 2pm
  Escalation Status: Waiting on vendor response (ETA: Jan 16 10am)
  ```

## Daily Standup Blocker Protocol

**Standup Agenda (15 min):**
1. **Progress** (3 min): What did we complete?
2. **Blockers** (7 min): Any issues preventing progress?
3. **Next Steps** (5 min): What's next?

**If blocker raised:**
- Describe clearly (what, impact, how long blocked)
- Suggest solutions or workarounds
- If team can solve → assign action, move on
- If escalation needed → PM captures and follows up after standup

## Weekly Blocker Summary

Include in weekly status report to stakeholders:

```
Weekly Blocker Summary (Week of Jan 15-19)
- New blockers this week: 2
- Resolved blockers: 1
- Active blockers: 3
  🔴 CRITICAL: Database migration backup procedure untested (Est. 24h to resolve)
  🟡 HIGH: Design review delayed 2 days waiting on stakeholder feedback
  🟡 HIGH: Third-party API rate limits hit in staging (Contingency: use mocks)

Action: Escalating DB blocker to Infrastructure Lead; expecting resolution by EOW.
```

## Execution Checklist
- [ ] Branching and PR conventions documented in repo
- [ ] CI configured for tests and lint
- [ ] Daily standup scheduled and blocker protocol defined
- [ ] Project board actively used and synced with issue tracker
- [ ] Regular demos scheduled (sprint or milestone-based)
- [ ] Risk register updated weekly and blockers logged
- [ ] Escalation paths clear and communicated to team
- [ ] Status reports include blocker summary

## Additional Resources
- See **OctoAcme — Risk Management & Communication** for detailed escalation process
- See **OctoAcme — Definition of Done** for acceptance criteria
- See **OctoAcme — Capacity Planning** for resource and dependency management
