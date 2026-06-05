# OctoAcme — Risk Management & Assessment Template

## Purpose
Standardize how we identify, assess, and track project risks to prevent surprises and enable proactive mitigation.

## Risk Identification Process

### When to Identify Risks
- During project initiation and planning
- Weekly during execution standups
- During retrospectives and post-mortems
- After any significant change in scope, timeline, or resources
- Continuously as new information emerges

### Risk Categories

| Category | Examples |
|----------|----------|
| **Technical** | New technology, architecture changes, performance unknowns, integration complexity |
| **Resource** | Key person dependency, skill gaps, unavailable vendor, capacity constraints |
| **Schedule** | Tight timelines, external dependencies, approval delays, sequential workflows |
| **External** | Vendor delays, regulatory changes, third-party API outages, market shifts |
| **Scope** | Unclear requirements, changing priorities, feature creep, unclear acceptance criteria |
| **Quality** | Test coverage gaps, manual testing, deployment complexity, observability gaps |
| **Security** | Data protection, authentication/authorization, third-party risks, compliance gaps |
| **Communication** | Misaligned stakeholders, unclear decisions, distributed team challenges |

## Risk Assessment Template

### Basic Risk Record
```
Risk ID: PROJ-R01
Title: Database migration complexity
Category: Technical
Date Identified: 2024-01-15
Owner: [Team member responsible for mitigation]

Description:
Current database schema has no version control. Migration to new schema may
require downtime and risks data loss if rollback is needed.

Impact: High
  - If realized: Production downtime, potential data loss, customer impact
  - Duration: Could be 2-4 hours of service interruption

Probability: Medium
  - Current schema has 5+ years of accumulated tech debt
  - Team has no prior experience with this migration complexity

Risk Score: 6 out of 9 (High × Medium)
  Impact High (3 pts) × Probability Medium (2 pts) = 6

Mitigation Plan:
1. Conduct proof-of-concept migration on staging environment (Week 1)
2. Create detailed rollback procedure and test it (Week 2)
3. Implement zero-downtime migration strategy using feature flags (Week 3)
4. Schedule migration during low-traffic window with on-call support standing by
5. Monitor database and application metrics for 24 hours post-migration

Owner: [Name] | Due: [Date] | Status: In Progress

Related Issues:
- [Link to tech spike]
- [Link to rollback runbook]
```

## Risk Assessment Matrix

### Impact & Probability Scale

**Impact Levels:**
- **High (3):** Project delayed >2 weeks, major feature cut, customer-facing outage, security breach
- **Medium (2):** Project delayed 1-2 weeks, feature scope reduced, quality concerns, moderate customer impact
- **Low (1):** Minor delays, small scope changes, internal impact only

**Probability Levels:**
- **High (3):** >70% likely to occur; conditions are present today
- **Medium (2):** 30-70% likely; possible but not inevitable
- **Low (1):** <30% likely; unlikely but conceivable

### Risk Score Grid

```
          | Low Impact | Med Impact | High Impact
----------|-----------|-----------|------------
High Prob |  1-3      |  4-6      |  7-9 (🔴)
Med Prob  |  1-2      |  4-6      |  6-8 (🟡)
Low Prob  |  1        |  2-4      |  3-5 (🟢)
```

**Risk Prioritization:**
- **🔴 Critical (7-9):** Escalate immediately, reassign resources if needed
- **🟡 High (4-6):** Active mitigation required, weekly review
- **🟢 Low (1-3):** Monitor, document mitigations, review monthly

## Risk Register Template

Maintain this table in your project repository (README, wiki, or docs/):

| Risk ID | Title | Category | Impact | Probability | Score | Owner | Mitigation | Status | Due | Notes |
|---------|-------|----------|--------|-------------|-------|-------|-----------|--------|-----|-------|
| R01 | DB migration | Technical | High | Medium | 6 | Alice | POC + rollback testing | In Progress | Jan 31 | Staging test passed Jan 20 |
| R02 | Stakeholder alignment | Communication | High | Low | 3 | Bob | Weekly stakeholder sync | Active | Ongoing | Sync scheduled Thu |
| R03 | Third-party API timeout | External | Medium | Medium | 4 | Carol | Implement circuit breaker | Mitigated | Feb 15 | Test in staging |

## Risk Lifecycle & Status Tracking

### Status Values
- **Identified:** Risk recorded but mitigation not started
- **Active:** Mitigation in progress, risk being actively managed
- **Mitigated:** Mitigation implemented, risk reduced below acceptable threshold
- **Escalated:** Risk requires leadership intervention or resource reallocation
- **Realized:** Risk has occurred; trigger incident response
- **Closed:** Risk no longer relevant or project complete

### Risk Review Cadence
- **Daily standup:** Flag any realized risks or new high-probability risks
- **Weekly PM sync:** Review risk register; update status and mitigations
- **Sprint planning:** Identify new risks based on upcoming work
- **Retrospective:** Analyze realized risks and capture learnings

## Escalation Protocol

### When to Escalate
- Risk score moves to 🔴 Critical (7-9)
- Mitigation plan is blocked and owner cannot unblock
- Risk is realized (incident)
- New external dependency or constraint emerges
- Stakeholder alignment breaks down

### Escalation Path
1. **Level 1 (Team Lead):** PM brings risk to standup or weekly sync
2. **Level 2 (Product Lead/Manager):** PM escalates with recommended actions
3. **Level 3 (Executive/Sponsor):** For business-impacting or security risks

### Escalation Message Template
```
Risk ID: [ID]
Title: [Title]
Current Status: [Status]
Issue: [What changed? Why escalation needed?]
Recommended Actions: [Options]
Decision Needed By: [Date]
Owner: [Name]
```

## Mitigation Strategies

### Common Mitigation Approaches

| Strategy | Approach | Example |
|----------|----------|----------|
| **Avoid** | Change project scope or approach to eliminate risk | Replace untested third-party library with proven alternative |
| **Reduce** | Actions to lower probability or impact | Additional testing, proof-of-concept, smaller batch sizes |
| **Accept** | Acknowledge risk and prepare contingency | For low-probability risks; document why accepted |
| **Transfer** | Shift responsibility to vendor or third party | SLA agreement with vendor, insurance, support contract |
| **Mitigate** | Implement controls and monitoring | Feature flags, gradual rollout, monitoring/alerts |

### Contingency Planning
For high-impact risks, document:
- **Trigger:** When is the contingency activated?
- **Actions:** What do we do if risk realizes?
- **Timeline:** How quickly must we act?
- **Owner:** Who makes the call and executes?

Example contingency:
```
Risk: Third-party payment processor outages
Trigger: Payment API down for >10 minutes
Contingency: Switch to fallback processor; queue transactions for retry
Timeline: Automatic failover within 2 minutes
Owner: On-call engineer
```

## Risk Communication

### Stakeholder Updates
Include risk summary in weekly status reports:
- **New Risks Identified:** Count and severity
- **Escalated Risks:** Any moved to Critical?
- **Realized Risks:** Any occurred this week? Actions taken?
- **Mitigated Risks:** Any no longer a concern?

### Risk Reporting Template
```
Weekly Risk Summary (Week of Jan 15-19)
- Total Active Risks: 12
- Critical (🔴): 1 (DB migration)
- High (🟡): 3 (Stakeholder alignment, API dependency, Resource constraint)
- Low (🟢): 8 (Monitored, no action needed)
- New This Week: 2
- Mitigated This Week: 1
- Realized This Week: 0
- Action: Continue daily standups on DB migration; schedule stakeholder alignment call
```

## Risk Management Checklist

- [ ] Risk identification process defined and communicated
- [ ] Risk register created and accessible to team
- [ ] Risk categories and assessment criteria agreed
- [ ] Mitigation owners assigned for Critical and High risks
- [ ] Risk review cadence established (daily, weekly, etc.)
- [ ] Escalation paths and decision-makers documented
- [ ] Contingency plans drafted for top risks
- [ ] Risk communication integrated into status reporting
- [ ] Post-incident reviews capture risk learnings

## Risk Register Tools

Recommend using:
- **GitHub Issues:** Tag with `type:risk`, use labels for priority and category
- **Spreadsheet:** Simple CSV in docs/ folder, version controlled
- **Project Board:** Dedicated column for risks, visibility across team
- **Wiki/Confluence:** Centralized risk hub with context and history

## Post-Project: Risk Lessons Learned

In retrospective, capture:
- Which risks were accurately assessed?
- Which were missed? What was the signal we overlooked?
- Which mitigations were effective? Ineffective?
- What do we do differently next project?
- Update risk templates and categories for continuous improvement