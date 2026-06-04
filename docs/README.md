# OctoAcme Project Management Process Overview

## Summary

OctoAcme operates on a structured yet iterative project management framework designed to balance customer-first principles with data-driven decision-making and psychological safety. The organization follows a five-phase lifecycle—Initiation, Planning, Execution, Release, and Retrospective—that ensures projects move from validated problem statements through delivery and continuous improvement. At its core, OctoAcme empowers cross-functional teams with clear ownership (Project Managers coordinate delivery while Product Managers define outcomes), lightweight but meaningful artifacts (Project One-pagers, Risk Registers, and backlog templates), and a strong emphasis on early stakeholder alignment. Each phase gates into the next, preventing wasted effort on unvalidated ideas and ensuring the team has proper context before scaling work.

## Key Workflows & Execution Model

The execution phase is powered by a structured daily-to-weekly cadence: daily 15-minute standups focus on progress and blockers, weekly delivery syncs showcase progress and flagged risks, and sprint reviews/demos occur at milestone boundaries. Work flows through a GitHub Projects board with columns spanning Backlog, Ready, In Progress, In Review, QA, and Done. Pull requests are kept small (≤400 lines when possible) and require automated CI checks and at least one approval before merge. Risk and blocker escalation follows a three-level approach—team triage, PM escalation to Product Lead and dependent teams, and finally sponsor-level escalation for business-impacting issues. Release and deployment activities are tightly controlled through pre-release requirements (acceptance criteria met, CI passed, security scans complete, smoke tests prepared) and documented rollback/incident playbooks to minimize production risk.

## Roles & Communication Strategy

OctoAcme defines clear personas that structure accountability and communication: **Developers** implement features while maintaining test coverage and identifying technical risks; **Product Managers** own vision, prioritization, and success metrics; and **Project Managers** coordinate schedules, risks, and stakeholder communication. Communication follows a predictable rhythm: weekly PM-to-PdM alignment, twice-weekly team standups, and monthly stakeholder updates, with ad-hoc escalations as needed. Stakeholder groups receive role-specific updates using a standard Weekly Status Template that covers progress, next steps, risks/blockers, and decisions needed. Security incidents follow a separate runbook with triage summaries, ongoing actions, and post-incident retrospectives. A single source of truth (project README or release documentation) ensures all stakeholders can access consistent status information.

## Quality Assurance & Continuous Improvement

Quality is baked into OctoAcme processes through multiple layers: unit tests for new logic, integration tests where applicable, end-to-end smoke tests for critical flows before release, and security scanning in CI. Manual QA is applied for feature acceptance when needed, and velocity and burndown metrics are tracked to monitor delivery health. Beyond execution, OctoAcme institutionalizes learning through structured retrospectives held after sprints, releases, or important milestones (typically 45–75 minutes, anonymous ideas welcomed). Retrospectives surface what went well, what could improve, and generate 2–3 prioritized action items with clear owners and due dates. These action items feed back into the project backlog and are reviewed in weekly PM syncs, creating a virtuous cycle of measured, iterative improvement that reinforces psychological safety and team ownership.

---

## Document Structure

This `docs/` folder contains detailed guidance for each phase of the OctoAcme lifecycle:

- **[octoacme-project-management-overview.md](./octoacme-project-management-overview.md)** — High-level introduction to OctoAcme principles, roles, and artifacts
- **[octoacme-project-initiation.md](./octoacme-project-initiation.md)** — Steps to validate work, align stakeholders, and create a Project One-pager
- **[octoacme-project-planning.md](./octoacme-project-planning.md)** — Turning an approved initiative into an actionable backlog and release plan
- **[octoacme-execution-and-tracking.md](./octoacme-execution-and-tracking.md)** — Day-to-day execution, quality assurance, and blocker escalation
- **[octoacme-release-and-deployment.md](./octoacme-release-and-deployment.md)** — Release types, pre-release requirements, and deployment checklist
- **[octoacme-risks-and-communication.md](./octoacme-risks-and-communication.md)** — Risk management, stakeholder communication, and escalation paths
- **[octoacme-retrospective-and-continuous-improvement.md](./octoacme-retrospective-and-continuous-improvement.md)** — Capturing learnings and converting them into actionable improvements
- **[octoacme-roles-and-personas.md](./octoacme-roles-and-personas.md)** — Detailed role definitions for Developers, Product Managers, and Project Managers

## Getting Started

New team members should start with the [octoacme-project-management-overview.md](./octoacme-project-management-overview.md) to understand core principles and roles, then reference the phase-specific documents as they work through projects from initiation through retrospective.
