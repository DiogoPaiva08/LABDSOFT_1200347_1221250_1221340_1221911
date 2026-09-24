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
    * [Architecture](#architecture)
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
    * [Problem & Opportunity Report](#problem--opportunity-report)
    * [Market & Competitor Analysis](#market--competitor-analysis)
    * [User Research](#user-research)
    * [Product Vision](#product-vision)
    * [Product Backlog](#product-backlog)
    * [Responsible AI Opportunity Assessment](#responsible-ai-opportunity-assessment)
    * [Technical Design](#technical-design)
    * [Architecture Decision Records](#architecture-decision-records)
    * [Security & Privacy Assessment](#security--privacy-assessment)
    * [Walking Skeleton](#walking-skeleton)
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

### Problem & Opportunity Report

### Market & Competitor Analysis

### User Research

### Product Vision

### Product Backlog

### Responsible AI Opportunity Assessment

### Technical Design

### Architecture Decision Records

### Security & Privacy Assessment

### Walking Skeleton

---

## 4. Repository Structure

Language FrontEnd and BackEnd

TO DO

---

## Code of Conduct

We don't use real personal data when synthetic data is sufficient, we never fabricate user-research evidence, we review all AI-generated content before treating it as authoritative, and we acknowledge third-party code, datasets, and tools.
