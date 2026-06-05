# OctoAcme — Capacity Planning & Resource Allocation

## Purpose
Ensure realistic project timelines by understanding team capacity, allocating resources fairly, and identifying resource conflicts early.

## Capacity Planning Overview

### Key Principles
- Capacity is not 100% utilization — account for:
  - Meetings (standups, syncs, planning)
  - Support and on-call duties
  - Administrative tasks and context switching
  - Vacation and planned time off
- Visibility into resource allocation across projects prevents burnout and bottlenecks
- Regular re-planning adapts to changing priorities

## Team Capacity Assessment

### Calculate Available Capacity
```
Weekly Hours Available = (Standard Hours) - (Meetings) - (On-call/Support) - (Admin)

Example:
40 hrs/week - 5 hrs (meetings) - 4 hrs (support) - 1 hr (admin) = 30 hrs available for delivery
```

### Capacity Template by Role

| Role | Weekly Hours | Meetings | Support | Available | Allocation |
|------|-------------|----------|---------|-----------|------------|
| Developer 1 | 40 | 4 | 2 | 34 | Project A: 20, Project B: 14 |
| Developer 2 | 40 | 3 | 4 | 33 | Project A: 33 |
| QA/Tester | 40 | 3 | 2 | 35 | Project A: 25, Project B: 10 |
| Product Manager | 40 | 8 | 2 | 30 | Project A: 20, Project B: 10 |
| Project Manager | 40 | 10 | 1 | 29 | Project A: 15, Project B: 14 |

### Accounting for Uncertainty
- Add a 15–20% buffer for:
  - Unexpected bugs or rework
  - Knowledge gaps requiring research
  - Ad-hoc support requests
  - Technical debt paydown

**Formula:** `Realistic Capacity = Available Hours × 0.80 to 0.85`

## Resource Allocation Process

### Step 1: Identify Resource Needs (During Planning)
For each project, estimate:
- Developer hours (by domain: frontend, backend, DevOps, etc.)
- QA/Testing hours
- Product and Project Manager hours
- Specialist hours (security, performance, etc.)

### Step 2: Map Against Available Capacity
- List all active projects
- Map required resources to available capacity
- Identify gaps, conflicts, or over-allocation
- Escalate to leadership if capacity is insufficient

### Step 3: Make Trade-off Decisions
Options when capacity is constrained:
- Reduce scope of lower-priority project
- Extend timeline for lower-priority project
- Hire or move resources from other areas
- Request temporary contractor support
- Descope non-critical features

### Step 4: Document Allocation
- Update project plans with named resources and hours
- Communicate allocation changes in weekly PM sync
- Flag any single-person dependencies

## Capacity Allocation Template

```
Project: [Name]
Timeline: [Start] to [End]

Resource Allocation:
| Role | Name | Hours/Week | Duration | Total Hours |
|------|------|-----------|----------|-------------|
| Lead Dev | Alice | 30 | 8 weeks | 240 |
| Backend Dev | Bob | 25 | 6 weeks | 150 |
| QA | Carol | 20 | 8 weeks | 160 |
| PM | Dave | 15 | 8 weeks | 120 |

Total Project Cost (effort): 670 hours
```

## Monitoring & Re-planning

### Weekly Capacity Review
- Velocity vs. estimate: are tasks completing on time?
- Capacity utilization: is the team over/under allocated?
- Risk flags: identify emerging bottlenecks

### Monthly Resource Sync
- Review allocation across all active projects
- Update capacity for vacations, leaves, new hires
- Adjust project timelines if needed
- Identify skill gaps and training opportunities

### Red Flags
- ⚠️ Any single person over 100% allocated
- ⚠️ QA or testing consistently late (bottleneck)
- ⚠️ Velocity declining week-over-week
- ⚠️ Team expressing burnout or missed deadlines
- ⚠️ No buffer for emergencies or support work

## Capacity Planning Checklist

- [ ] Team availability and time off documented
- [ ] Baseline capacity calculated for each team member
- [ ] Resource needs estimated for each active project
- [ ] Allocation map created and reviewed
- [ ] Conflicts or over-allocation identified and escalated
- [ ] Allocation plan shared with stakeholders
- [ ] Weekly monitoring process in place
- [ ] Contingency plan if key person becomes unavailable

## Best Practices

1. **Be conservative** — underpromise and overdeliver on capacity estimates
2. **Track reality** — compare planned vs. actual hours to improve estimates
3. **Communicate early** — flag capacity issues before they impact delivery
4. **Cross-train** — reduce single-person dependencies
5. **Protect focus time** — minimize interruptions during peak delivery periods
6. **Plan for chaos** — always reserve buffer for unplanned work
