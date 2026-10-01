# CampusFlow - User Research: Survey Draft

Part of issue [#8](../../issues/8) — User Research. Feeds `docs/03-user-research.md`.

**Goal:** quantify what the interviews surface. Run this *after* the 4–6 interviews, so
wording is informed by real language people actually use.

**Distribution:** share in class group chats / student groups each team member has
access to. Target: as many responses as feasible in the time available — more matters
more than a specific number, but note the actual sample size and where it was
distributed when reporting results (this is what makes it usable, honest evidence
rather than an unqualified statistic).

**Tool:** Google Forms — single/multiple choice, one 1–5 scale, "Other" free-text
options on some questions. Anonymous: no name or email collected. Screen-reader
compatibility enabled. Estimated time: 2–3 minutes. All questions are required.
The form has 5 sections:

| Section | Content | Questions |
|---------|---------|-----------|
| 1 | Context and current behaviour | 1–4 |
| 2 | Avoidance behaviour | 5 |
| 3 | Queues, frustration and the value of the solution | 6–9 |
| 4 | Check-in motivation | 10 |
| 5 | Notifications | 11 |

Questions 5 and 10 are conditional (skipped through "Go to section based on answer"):
section 2 is only shown to people who avoided or delayed a visit (question 4), and
section 4 is only shown to people who are willing to do the check-in (question 9).

**Introduction shown at the top of the form:** this questionnaire is part of the
CampusFlow project, developed as part of LABDSOFT. It aims to understand how students
and members of the ISEP community deal with queues and overcrowded spaces on campus,
and to assess interest in a solution that provides up-to-date occupancy and waiting-time
information. Takes about 2–3 minutes. Responses are used exclusively for academic
purposes and analysed in aggregate.

---

## Section 1 — Context and current behaviour

1. **What's your role on campus?**
   - Student / Teaching staff / Non-teaching staff / Other: ___

2. **How often do you visit a canteen, bar, library or academic services on campus in a
   typical week?**
   - Rarely / A few times a week / Daily / Multiple times a day

3. **How do you currently decide whether a place is likely to be busy?**
   *(multiple choice — pick all that apply)*
   - Past experience / time of day
   - Ask a friend who's already there
   - Look through the window / check in person before committing
   - I don't check, I just go
   - Other: ___

4. **Have you ever avoided or delayed going somewhere (canteen, library, etc.) because
   you expected it to be crowded?**
   - Yes, often / Yes, sometimes / Rarely / Never
   - *Never* skips section 2.

5. **When you avoid or delay a visit, what do you usually do instead?**
   - *(options to be confirmed from the form)*

6. **On a typical busy day, roughly how long do you wait in the place where you wait
   most?**
   - Under 5 min / 5–10 min / 10–20 min / Over 20 min / Other: ___

7. **What frustrates you most about queues on campus?**
   - Not knowing how long I will wait
   - The queue varying unpredictably from day to day
   - The queue being long
   - Other: ___
   - *(confirm exact wording against the form)*

8. **If you could check a location's current occupancy and estimated wait time before
   heading there, how useful would that information be?**
   *(1–5 scale: Not useful → Very useful)*

9. **Would you be willing to do a ~3-second check-in when you arrive somewhere, to help
   keep that information accurate for others?**
   - Yes, without needing anything in return
   - Yes, but only with some kind of benefit
   - Maybe
   - No
   - *No* skips section 4.

10. **What would motivate you to do that check-in?**
   - *(options to be confirmed from the form)*
   - Other: ___

11. **Which notifications would you want?**
   - Only when one of my favourite places is unusually crowded
   - *(remaining options to be confirmed from the form)*

---

## Mapping to hypotheses

| Hypothesis (`docs/01-problem-opportunity.md`)                                                                                             | Questions   | How to read the result                                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **H1** — Students regularly avoid or delay visiting a POI because they expect it to be crowded, without knowing the actual current status | 4, 3, 5, 6  | Filter question 1 = Student. Supported if many answer "Yes, often"/"Yes, sometimes" in question 4 **and** question 3 shows no reliable live information ("I don't check", past experience, asking someone). Question 5 shows what they do instead; question 6 gives the size of the wait. |
| **H2** — Unpredictability, not just average length, causes the most frustration                                                           | 7           | Compare the combined share of "Not knowing how long I will wait" and "The queue varying…" against "The queue being long"                                                                                                                                                                  |
| **H3** — Users would do a ~3-second check-in without an incentive                                                                         | 9, 10       | "Yes, without needing anything in return" answers it directly; "Maybe" and "Yes, but only with some kind of benefit" indicate an incentive is needed. Question 10 shows which incentive.                                                                                                  |
| Value of the product                                                                                                                      | 8           | Distribution of the 1–5 scale                                                                                                                                                                                                                                                             |
| Notification design (favourites only)                                                                                                     | 11          | Share choosing "Only when one of my favourite places is unusually crowded"                                                                                                                                                                                                                |

## After collecting responses

- Report sample size and where it was distributed alongside every percentage —
  don't present a number without that context.
- H1 is stated for **students**; filter by question 1 before reporting.
- Questions 5 and 10 are conditional, so their base is smaller; report the *n* for each percentage.
- Cross-check questions 3, 4 and 6 against H1, and question 7 against H2, in
  `docs/01-problem-opportunity.md`.
- Cross-check questions 9 and 10 against the cold-start assumption in that same document.
- Stated willingness (question 9) is not observed behaviour; mention this in Limitations.
- The sample is ISEP-specific and self-selected (distributed through class groups);
  mention this in Limitations too.