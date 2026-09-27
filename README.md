# CampusFlow

> **LABDSOFT 2026/27 — Community Resilience and Everyday Services Platform**
>
> A community-driven, event-oriented platform that helps a university campus manage and optimize the flow of people, providing real-time estimated waiting times for high-traffic places and smart alerts when your usual spots get unexpectedly crowded.

|                        |                                                                                                                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Target community**   | University campus — students, teaching staff and non-teaching staff                                                                                                                                  |
| **Problem**            | Time lost and frustration caused by unpredictable queues and overcrowded spaces (canteens, bars, libraries, academic services, vending areas), due to the lack of centralized, real-time information |
| **Primary users**      | Students (primary), teaching and non-teaching staff                                                                                                                                                  |
| **Measurable outcome** | _<e.g. reduction in average waiting time for users who follow a suggested alternative>_                                                                                                              |

---

## Team Members

| Student Number | Name               |  
|----------------|--------------------|
| _<1200347>_    | _<Beatriz Silva>_  | 
| _<1221250>_    | _<Carlos Pereira>_ | 
| _<1221911>_    | _<Bruno Lourenço>_ |
| _<1221340>_    | _<Diogo Paiva>_    |

---

## Table of Contents

<!-- TOC -->
* [CampusFlow](#campusflow)
  * [Team Members](#team-members)
  * [Table of Contents](#table-of-contents)
  * [Product Overview](#product-overview)
    * [The Problem](#the-problem)
    * [The Solution](#the-solution)
  * [1. Sprint Plan](#1-sprint-plan)
  * [2. Phase 1 — Team Setup](#2-phase-1--team-setup)
    * [Checklist](#checklist)
    * [2.1 Git Repository](#21-git-repository)
    * [2.2 Issue Tracking](#22-issue-tracking)
    * [2.3 Methodology](#23-methodology)
    * [2.4 Definition of Ready (DoR)](#24-definition-of-ready-dor)
    * [2.5 Definition of Done (DoD)](#25-definition-of-done-dod)
    * [2.6 Team Roles](#26-team-roles)
  * [3. Sprint 1 Deliverables](#3-sprint-1-deliverables)
  * [4. Repository Structure](#4-repository-structure)
  * [Code of Conduct](#code-of-conduct)
<!-- TOC -->

---

## Product Overview

### The Problem

In university communities, students, teaching staff and employees lose time every day to unpredictable queues and overcrowded spaces. High-traffic places such as canteens, bars, libraries, academic services and vending areas experience large swings in occupancy, and there is no centralized, transparent, real-time information about waiting times.

### The Solution

*CampusFlow* provides an *interactive campus map* (with building navigation and per-floor plans) where users can:

- *Check estimated waiting times* for each point of interest (POI)
- *Submit quick check-ins (~3 seconds)* reporting the current queue status, optionally with a free-text note or photo
- *Favourite their usual places* and only get *notifications and faster alternatives* when an anomalous peak is detected there, avoiding information overload
- *Computer vision* to automatically detect whether a queue is crowded

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

- **Platform:** GitHub
- **URL:** _<https://github.com/DiogoPaiva08/LABDSOFT_1200347_1221250_1221340_1221911>_

**Branching strategy** (proposed: simplified GitHub Flow)

| Branch | Purpose |
|---|---|
| `main` | Stable, always deployable code. Protected — changes only via PR. |
| `develop` | Sprint integration branch (optional). |
| `feature/<ISSUE-ID>-description` | New feature |
| `fix/<ISSUE-ID>-description` | Bug fix |
| `docs/<ISSUE-ID>-description` | Documentation |

**Rules**

- `main` is protected: no direct pushes, PR required, CI pipeline must pass before merge.
- Every PR requires **at least 1 approval** from another team member (code review).
- Commits follow conventional commits and reference the GitHub issue they close or relate to:
  ```
  feat: add duplicate detection endpoint #22
  fix: handle expired token #21
  docs: add initial README with project overview and sprint plan #1
  ```
- PRs should stay small and scoped to one issue where possible — easier to review,
  easier to trace as individual contribution evidence.

### 2.2 Issue Tracking

- **Tool:** GitHub Issues (this repository) — see the `Issues` tab.
- Issue types in use: setup tasks (Phase 1, #1–#5), Sprint 1 deliverables (#6–#15).

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

Each deliverable below is its own document under `docs/`, tracked by its own GitHub issue.
Open a PR per document, referencing its issue (see [`CONTRIBUTING.md`](CONTRIBUTING.md) for
branch naming and PR rules).

| # | Deliverable | Doc | Issue |
|---|---|---|---|
| 1 | Problem & Opportunity Report | [`docs/01-problem-opportunity.md`](docs/01-problem-opportunity.md) | [#6](../../issues/6) |
| 2 | Market & Competitor Analysis | [`docs/02-market-competitor-analysis.md`](docs/02-market-competitor-analysis.md) | [#7](../../issues/7) |
| 3 | User Research | [`docs/03-user-research.md`](docs/03-user-research.md) | [#8](../../issues/8) |
| 4 | Product Vision | [`docs/04-product-vision.md`](docs/04-product-vision.md) | [#9](../../issues/9) |
| 5 | Product Backlog | [`docs/05-product-backlog.md`](docs/05-product-backlog.md) | [#10](../../issues/10) |
| 6 | Responsible AI Opportunity Assessment | [`docs/06-responsible-ai.md`](docs/06-responsible-ai.md) | [#11](../../issues/11) |
| 7 | Technical Design | [`docs/07-technical-design.md`](docs/07-technical-design.md) | [#12](../../issues/12) |
| 8 | Architecture Decision Records | [`docs/adr/`](docs/adr/README.md) | [#13](../../issues/13) |
| 9 | Security & Privacy Assessment | [`docs/08-security-privacy.md`](docs/08-security-privacy.md) | [#14](../../issues/14) |
| 10 | Walking Skeleton | [`docs/09-walking-skeleton.md`](docs/09-walking-skeleton.md) | [#15](../../issues/15) |

---

## 4. Repository Structure

Language FrontEnd and BackEnd

TO DO

---

## Code of Conduct

We don't use real personal data when synthetic data is sufficient, we never fabricate user-research evidence, we review all AI-generated content before treating it as authoritative, and we acknowledge third-party code, datasets, and tools.
