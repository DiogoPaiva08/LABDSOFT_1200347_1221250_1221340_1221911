# 1. Problem & Opportunity Report

> Closes issue [#6](../../issues/6) — Problem & Opportunity Report

## Target Community

CampusFlow targets a university campus in general - students, teaching staff, and
non-teaching staff - as defined in the README's product overview table:

- **Students (primary)** - the group most affected by queue time between classes, since
  their schedule windows are short and fixed.
- **Teaching staff** - affected mainly during short breaks between lectures.
- **Non-teaching staff** - administrative/academic-services and facilities staff who run
  the high-traffic points of interest (canteen, bar, library, academic services, vending
  areas) and currently have no tool to communicate real-time occupancy to users.

## Problem Statement

Students, teaching staff, and non-teaching staff at ISEP lose time every day to
unpredictable queues and overcrowded spaces - canteens, bars, libraries, academic
services, and vending areas - because there is no centralized, real-time source of
information about how busy these places currently are. 
<br>This matters most for students
and staff with short, fixed windows between classes: a 15-minute break spent queueing
is a break lost, and repeated bad experiences (arriving to find a space already full)
erode trust in campus services more broadly.

## Stakeholder Map

| Stakeholder                                                       | Relationship to the problem                                                                                                                                                                        |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Students**                                                      | Most affected - short breaks, high queue sensitivity. Primary users and primary source of check-in data.                                                                                           |
| **Teaching staff**                                                | Affected during breaks between lectures; secondary users.                                                                                                                                          |
| **Non-teaching staff** (canteen, bar, library, academic services) | Operate the physical spaces; benefit from reduced overcrowding complaints but are not expected to actively use the app themselves in the MVP.                                                      |
| **Campus administration**                                         | Owns the physical spaces and campus data (floor plans, opening hours); potential long-term stakeholder for adoption beyond the course project, not a decision-maker for this academic deliverable. |
| **LABDSOFT teaching staff**                                       | Acting as "investors" for this project - decide whether the problem and MVP are credible (Sprint 1 review).                                                                                        |
| **Project team**                                                  | Builds and operates the system; owns technical and product decisions.                                                                                                                              |

## Problem Evidence

No formal evidence has been collected yet. The problem statement above is currently
based on the team's own lived experience as university students, which is a reasonable
starting hypothesis but **not validated evidence**.

**Validation plan** (results will land in [`docs/03-user-research.md`](03-user-research.md)
once collected):
- 4–6 short interviews with students and POI staff (canteen, bar, library) — see
  [`docs/research/interview-guide.md`](research/interview-guide.md)
- A short student survey (~8 questions) — see
  [`docs/research/survey-draft.md`](research/survey-draft.md)

**Hypotheses to validate:**
- H1: Students regularly avoid or delay visiting a POI (canteen, library) because they
  expect it to be crowded, without knowing the actual current status.
- H2: The unpredictability of queues — not just their average length — is what causes
  the most frustration.
- H3: Users would be willing to do a ~3-second check-in if it improves the information
  available to others (reciprocity), without needing an incentive.

## Assumptions & Risks

| Assumption                                                                                | Risk if false                                                                                                              |
|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| Enough users will check in voluntarily to keep wait estimates fresh (cold-start problem). | Without a critical mass of check-ins, estimates stay stale and the app loses trust quickly — potentially fatal to the MVP. |
| Campus floor plans (SVG, per building/floor) can be obtained or produced.                 | Without them, the map falls back to a flat POI list — weaker UX, but not fatal.                                            |