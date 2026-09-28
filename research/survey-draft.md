# CampusFlow - User Research: Survey Draft

Part of issue [#8](../../issues/8) — User Research. Feeds `docs/03-user-research.md`.

**Goal:** quantify what the interviews surface. Run this *after* the 4–6 interviews, so
wording is informed by real language people actually use.

**Distribution:** share in class group chats / student groups each team member has
access to. Target: as many responses as feasible in the time available — more matters
more than a specific number, but note the actual sample size and where it was
distributed when reporting results (this is what makes it usable, honest evidence
rather than an unqualified statistic).

**Tool:** Google Forms — single/multiple choice, 1–5 scale, one optional open-text
question. Anonymous: no name or email collected. Estimated time: 2–3 minutes.
Questions 5 and 10 are conditional (skipped through "Go to section based on answer").

---

1. **What's your role on campus?** *(required)*
    - Student / Teaching staff / Non-teaching staff / Other

2. **How often do you visit a canteen, bar, or library on campus in a typical week?**
    - Rarely / A few times a week / Daily / Multiple times a day

3. **Have you ever avoided or delayed going somewhere (canteen, library, etc.) because
   you expected it to be crowded?**
    - Yes, often / Yes, sometimes / Rarely / Never

4. **How do you currently decide whether a place is likely to be busy?**
   *(multiple choice — pick all that apply)*
    - Past experience / time of day
    - Ask a friend who's already there
    - Look through the window / check in person before committing
    - I don't check, I just go
    - Other: ___

5. **On a typical busy day, roughly how long do you wait?**
    - Under 5 min / 5–10 min / 10–20 min / Over 20 min

6. **What bothers you more?**
    - A long wait I can predict in advance
    - A short wait that's unpredictable — I never know what I'll find

7. **If an app showed live estimated wait times for campus spots, how likely would you
   be to use it before heading there?**
   *(1–5 scale: Very unlikely → Very likely)*

8. **Would you be willing to do a ~3-second check-in (tap "busy"/"not busy") when you
   arrive somewhere, to help keep that information accurate for others?**
    - Yes, without needing anything in return
    - Yes, but only with some kind of incentive
    - No

---

## Mapping to hypotheses

| Hypothesis (`docs/01-problem-opportunity.md`)                                                                                             | Questions | How to read the result                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **H1** — Students regularly avoid or delay visiting a POI because they expect it to be crowded, without knowing the actual current status | 4, 5, 3   | Question 4 for students only (filter question 1 = Student). Supported if many answer "Sometimes"/"Often" **and** question 3 shows no reliable live information ("I don't check", past experience, asking someone) |
| **H2** — Unpredictability, not just average length, causes the most frustration                                                           | 7, 6      | Compare the combined share of "Not knowing how long I will wait" and "The queue varying…" against "The queue being long"                                                                                          |
| **H3** — Users would do a ~3-second check-in without an incentive                                                                         | 9, 10     | "Yes, without needing anything in return" answers it directly; "Maybe" and "Yes, but only with some kind of benefit" indicate an incentive is needed                                                              |
| Value of the product                                                                                                                      | 8         | Distribution of the 1–5 scale                                                                                                                                                                                     |
| Notification design (favourites only)                                                                                                     | 11        | Share choosing "Only when one of my favourite places is unusually crowded"                                                                                                                                        |


## After collecting responses

- Report sample size and where it was distributed alongside every percentage —
  don't present a number without that context.
- H1 is stated for **students**; filter by question 1 before reporting.
- Questions 5 and 10 are conditional, so their base is smaller; report the *n* for each percentage.
- Cross-check questions 3, 4 and 5 against H1, and question 7 against H2, in
  `docs/01-problem-opportunity.md`.
- Cross-check questions 9 and 10 against the cold-start assumption in that same document.
- Stated willingness (question 9) is not observed behaviour; mention this in Limitations.