# OctoAcme — Definition of Done (DoD)

## Purpose
Establish clear, team-agreed criteria that work items must meet before being marked complete and released to production.

## Why Definition of Done Matters
- Prevents incomplete work from entering production
- Reduces rework and technical debt
- Creates shared expectations across developers, QA, and product
- Enables consistent velocity measurement

## Core Definition of Done Checklist

### Code Quality
- [ ] Code follows team style guide and linting standards pass
- [ ] Unit tests written for new logic (minimum 80% coverage)
- [ ] Code reviewed and approved by at least one peer
- [ ] No console errors, warnings, or debug statements left in code
- [ ] Comments added for complex logic or business rules

### Testing
- [ ] Unit tests pass locally and in CI
- [ ] Integration tests pass (if applicable)
- [ ] Manual QA performed and acceptance criteria verified
- [ ] Edge cases and error scenarios tested
- [ ] Regression testing completed

### Documentation
- [ ] Code comments explain "why," not just "what"
- [ ] README or docs updated if behavior or APIs changed
- [ ] Acceptance criteria linked in PR description
- [ ] Test cases documented or linked

### Security & Performance
- [ ] Security scanning (SAST) passed with no critical issues
- [ ] Dependency vulnerabilities checked and addressed
- [ ] Performance impact assessed (load time, memory, queries)
- [ ] Sensitive data handled securely (no hardcoded secrets, proper encryption)

### DevOps & Deployment
- [ ] Deployment instructions documented or automated
- [ ] Database migrations (if any) tested and reversible
- [ ] Monitoring and alerting configured for new features
- [ ] Rollback plan documented
- [ ] Environment variables or configs externalized

### Process Compliance
- [ ] Issue/ticket linked in PR and branch name
- [ ] PR description includes changes, testing approach, and known limitations
- [ ] Related documentation updated or flagged for update
- [ ] Sign-off from Product Manager (for feature work)
- [ ] No unresolved merge conflicts

## Definition of Done Verification Workflow

### Developer Checklist (Before PR)
1. Run linter and fix any issues
2. Run full test suite locally
3. Build and test in development environment
4. Self-review PR against DoD checklist
5. Request review from assigned reviewer

### Reviewer Checklist (During Code Review)
1. Verify code quality and style compliance
2. Check test coverage and quality
3. Review for security vulnerabilities
4. Assess performance impact
5. Validate PR description completeness
6. Approve only when all DoD items verified

### QA/Tester Checklist (Before Merge)
1. Verify acceptance criteria against live code
2. Test normal and edge case scenarios
3. Perform regression testing
4. Check for new bugs or regressions
5. Sign off in PR or create issues for gaps

### Merge Gate Automation
- All CI checks must pass
- At least one approval required
- No merge conflicts
- Branch protection rules enforced

## Role-Specific DoD Extensions

### Frontend Features
- [ ] Responsive design tested (mobile, tablet, desktop)
- [ ] Accessibility (a11y) standards verified (WCAG 2.1 AA minimum)
- [ ] Cross-browser testing completed
- [ ] User experience reviewed by design team
- [ ] Analytics events instrumented

### Backend/API Features
- [ ] API contract documented (OpenAPI/Swagger if applicable)
- [ ] Rate limiting and throttling configured
- [ ] Logging and error handling comprehensive
- [ ] Database query performance reviewed
- [ ] Backward compatibility maintained or migration planned

### DevOps/Infrastructure
- [ ] Infrastructure-as-Code (IaC) syntax validated
- [ ] Disaster recovery tested
- [ ] Capacity planning updated
- [ ] Change management approval obtained
- [ ] Runbooks or playbooks documented

## When DoD Is NOT Met
- Work cannot be merged to main branch
- PM is notified if acceptance criteria not met
- Issue remains in "In Progress" or moves back to "Ready"
- Root cause of DoD gap captured in retrospective

## DoD Review & Updates
- Review DoD quarterly or after major incidents
- Gather team feedback on what's working and what's slowing us down
- Update template based on lessons learned
- Announce changes in team standup and document rationale

## Example: Marking Work as Done
✅ **Item is ready to ship when:**
- All tests pass
- Code reviewed and approved
- Acceptance criteria verified by QA
- Documentation complete
- No open merge conflicts or CI failures
- Product Manager sign-off received

❌ **Item is NOT done when:**
- Tests are skipped or failing
- Code review requested but reviewer hasn't signed off
- QA tests incomplete
- Known bugs documented but not fixed
- Documentation outdated or missing
