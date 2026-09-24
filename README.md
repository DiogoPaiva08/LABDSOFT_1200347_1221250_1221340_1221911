# LABDSOFT 2026/27 — Community Resilience and Everyday Services Platform

> A digital product that helps a community **anticipate, manage, or recover from disruptions** affecting everyday life, combining trustworthy information, coordinated action, responsible AI, and a secure, observable, continuously delivered architecture.

| | |
|---|---|
| **Team** | _<team name>_ |
| **Target community** | _<e.g. ISEP campus, neighbourhood X, ...>_ |
| **Problem** | _<specific problem being addressed>_ |
| **Primary users** | _<primary user group>_ |
| **Measurable outcome** | _<metric the product aims to improve>_ |

---

## Table of Contents

1. [Sprint Plan](#1-sprint-plan)
2. [Phase 1 — Team Setup](#2-phase-1--team-setup)
   - [Git Repository](#21-git-repository)
   - [Issue Tracking](#22-issue-tracking)
   - [Methodology](#23-methodology)
   - [Definition of Ready](#24-definition-of-ready-dor)
   - [Definition of Done](#25-definition-of-done-dod)
   - [Team Roles](#26-team-roles)
3. [Sprint 1 Deliverables](#3-sprint-1-deliverables)
4. [Repository Structure](#4-repository-structure)

---

## 1. Sprint Plan

| Sprint | Objective | Investor Question |
|---|---|---|
| **Sprint 1** — Discover, Validate & Design | Problem, competitors, product vision, technical design and walking skeleton | *Is this a valuable problem, and is the proposed MVP the smallest credible product experiment?* |
| **Sprint 2** — Build & Operate | End-to-end vertical slice of the most important user journey | *Does the product already deliver observable user value, and can the team deploy, monitor, and operate it?* |
| **Sprint 3** — Evaluate, Harden & Present | Refine the MVP, evaluate AI, security, performance, resilience, and final pitch | *Is this a credible product and a maintainable software system worth further investment?* |

---

## 2. Phase 1 — Team Setup

### Checklist

- [ ] Git repository created and configured
- [ ] Issue tracking system set up
- [ ] Team methodology agreed
- [ ] Definition of Ready elaborated
- [ ] Definition of Done elaborated
- [ ] Roles identified and assigned

### 2.1 Git Repository

- **Platform:** _<GitHub / Bitbucket / GitLab>_
- **URL:** _<repository link>_

**Branching strategy** (proposed: simplified GitHub Flow)

| Branch | Purpose |
|---|---|
| `main` | Stable, always deployable code. Protected — changes only via PR. |
| `develop` | Sprint integration branch (optional). |
| `feature/<ISSUE-ID>-description` | New feature |
| `fix/<ISSUE-ID>-description` | Bug fix |
| `docs/<ISSUE-ID>-description` | Documentation |

**Rules**

- `main` protection: no direct pushes, PR required, CI pipeline must pass.
- Every PR requires **at least 1 approval** from another team member (code review).
- Commits follow [Conventional Commits](https://www.conventionalcommits.org/) and reference the issue:
  ```
  feat(reports): add duplicate detection endpoint [LAB-42]
  fix(auth): handle expired token [LAB-57]
  ```
- PR template including: description, related issue, how to test, DoD checklist.

### 2.2 Issue Tracking

- **Tool:** _<Jira / GitHub Projects>_
- **Board URL:** _<link>_

Used to:

- Manage the **product backlog** (epics → user stories → tasks)
- Plan sprints and define **sprint goals**
- Assign and track work
- Record **decisions** and **investor/stakeholder feedback**
- Monitor progress (burndown, velocity)

**Issue types:** `Epic`, `Story`, `Task`, `Bug`, `Spike` (research).
**Workflow:** `Backlog → Ready → In Progress → In Review → Done`
**Integration:** link Jira/Projects to the repository so commits and PRs reference issues automatically.

### 2.3 Methodology

The team follows **Scrum**, adapted to the project length (3 sprints).

| Ceremony | Frequency | Duration | Purpose |
|---|---|---|---|
| Sprint Planning | Start of each sprint | ~1h | Define the sprint goal and select backlog items |
| Daily / Sync | _<e.g. 2–3x per week>_ | 15 min | What I did, what I'll do, blockers |
| Backlog Refinement | Weekly | ~30 min | Detail and estimate stories, apply DoR |
| Sprint Review | End of each sprint | — | Demo to investors (teaching staff) and gather feedback |
| Retrospective | End of each sprint | ~30 min | Improve the team's process |

- **Estimation:** Story Points (Fibonacci: 1, 2, 3, 5, 8, 13)
- **Communication:** _<Discord / Teams / Slack>_
- **Investor feedback:** recorded in Jira; at least **one product or technical decision must be revised** based on that feedback and documented (ADR or decision note).

### 2.4 Definition of Ready (DoR)

A user story can only enter a sprint when:

- [ ] It is written as *"As a `<persona>`, I want `<goal>`, so that `<benefit>`"*
- [ ] It has clear, testable **acceptance criteria** (e.g. Given/When/Then)
- [ ] The value to the user/community is explicit
- [ ] It has been **estimated** by the team
- [ ] It follows INVEST (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- [ ] It fits within one sprint (otherwise it is split)
- [ ] Dependencies (external APIs, other stories, data) are identified and resolved or planned
- [ ] UI mockups/sketches are attached, where applicable
- [ ] **Security, privacy, and AI** implications are identified, where applicable
- [ ] The team understands the story and has no blocking questions

### 2.5 Definition of Done (DoD)

An item is only considered done when:

**Code**
- [ ] Implemented according to all acceptance criteria
- [ ] Follows the team's coding conventions and passes static analysis
- [ ] PR reviewed and approved by at least 1 team member
- [ ] Merged into `main` without conflicts

**Quality**
- [ ] Unit tests written and passing
- [ ] Integration/contract/E2E tests where relevant
- [ ] CI/CD pipeline green (build, tests, static analysis, dependency checks)
- [ ] No known critical vulnerabilities introduced

**Operations**
- [ ] Container image built and deployed to the test environment
- [ ] Structured logs, health checks, and relevant metrics added
- [ ] Failures handled (retries, fallback, degraded mode) where applicable

**Security, Privacy & AI**
- [ ] Access control enforced
- [ ] No unnecessary personal data; no secrets in code
- [ ] AI features have a fallback/baseline and never present uncertain content as verified fact

**Documentation**
- [ ] API documented (e.g. OpenAPI)
- [ ] ADR created if a relevant architectural decision was made
- [ ] README/docs updated
- [ ] Issue closed in the tracker and demonstrable to the PO

### 2.6 Team Roles

| Role | Responsibilities | Member(s) |
|---|---|---|
| **Product Manager / Product Owner** | Product vision, backlog prioritization, investor liaison | _<name>_ |
| **Scrum Master** | Facilitate ceremonies, remove blockers, safeguard the process | _<name>_ |
| **Business Analyst** | User research, competitor analysis, user stories and acceptance criteria | _<name>_ |
| **Tech Lead / Architect** | Architecture, ADRs, technical decisions, cross-service consistency | _<name>_ |
| **Developers** | Frontend, backend, data, and AI component | _<names>_ |
| **QA** | Test strategy, automation, AI evaluation, accessibility | _<name>_ |
| **DevOps** | CI/CD, containers, deployment, observability and operational dashboard | _<name>_ |

> Roles may overlap. All members write code, and everyone must be able to explain the product vision, architecture, technical decisions, security risks, AI evaluation, and operational model — **assessment is individual**.

---

## 3. Sprint 1 Deliverables

| # | Deliverable | Status | Document |
|---|---|---|---|
| 1 | Problem & Opportunity Report | ⬜ | `docs/product/problem-opportunity.md` |
| 2 | Market & Competitor Analysis | ⬜ | `docs/product/competitor-analysis.md` |
| 3 | User Research | ⬜ | `docs/product/user-research.md` |
| 4 | Product Vision (personas, value proposition, journeys, MVP) | ⬜ | `docs/product/vision.md` |
| 5 | Product Backlog | ⬜ | _<Jira link>_ |
| 6 | Responsible AI Opportunity Assessment | ⬜ | `docs/ai/ai-assessment.md` |
| 7 | Technical Design (C4, data model, APIs, async, deployment) | ⬜ | `docs/architecture/` |
| 8 | Architecture Decision Records | ⬜ | `docs/adr/` |
| 9 | Security & Privacy Assessment | ⬜ | `docs/security/threat-model.md` |
| 10 | Walking Skeleton (repo, build, test, container) | ⬜ | `services/`, `client/` |

---

## 4. Repository Structure

```
.
├── docs/
│   ├── product/        # problem, competitors, research, vision
│   ├── architecture/   # C4 views, data model, deployment
│   ├── adr/            # Architecture Decision Records
│   ├── ai/             # AI evaluation and risks
│   ├── security/       # threat model, privacy
│   └── process/        # DoR, DoD, meeting notes, investor feedback
├── services/           # backend components (≥ 2 independently deployable)
├── client/             # web/mobile application
├── infra/              # docker-compose, k8s, configs
├── .github/            # CI/CD workflows, PR/issue templates
└── README.md
```

---

## Code of Conduct

We don't use real personal data when synthetic data is sufficient, we never fabricate user-research evidence, we review all AI-generated content before treating it as authoritative, and we acknowledge third-party code, datasets, and tools.
