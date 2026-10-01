# 2. Market & Competitor Analysis

> Closes issue [#7](../../issues/7) — Market and Competitor Analysis

## Scope & Method

This analysis maps the alternatives a campus user has **today** when deciding whether to
walk to a canteen, bar, library, academic service or vending area — and what each of
those alternatives does well and badly. It covers the seven axes required by the project
brief (§5.2): target users, principal features, strengths, weaknesses, business or
sustainability model, user experience, and privacy and trust.

Alternatives are deliberately **not restricted to digital products**. The brief treats
non-digital alternatives as legitimate competitors, and in this problem space the real
incumbent is not an app — it is walking over to look, or asking in a group chat.

**Method:** desk research over public product documentation, vendor sites, university
announcements of deployments, and press coverage (sources listed at the end). No vendor
was contacted and no product was trialled on the ISEP campus; the limitations this
imposes are stated in [Limitations](#limitations-of-this-analysis).

> **⚠ To confirm with the team before the Sprint 1 review:** the ISEP-specific claims in
> [C. Institutional channels](#c-institutional-channels-portal-isep-moodle-website-notices)
> are based on public pages plus team members' own experience as ISEP students. One team
> member should verify first-hand what the current Portal ISEP app does and does not
> show, and whether any canteen/occupancy feature exists. Do not present unverified
> claims about ISEP to the investors.

---

## Landscape Overview

The alternatives fall into five categories, which compete with CampusFlow in very
different ways:

| Category | Examples | How it competes |
|---|---|---|
| **Passive crowd-sensing at scale** | Google Maps Popular times / Live busyness | Already on every phone, zero effort, but coarse |
| **Sensor-based campus occupancy** | Waitz (Occuspace) | Solves exactly this problem, with hardware and an institutional contract |
| **Institutional channels** | Portal ISEP, Moodle, website notices, campus signage | Authoritative but static; owns the audience |
| **Queue & order-ahead systems** | Qminder, TablesReady, ticket dispensers, canteen order-ahead apps | Removes the queue instead of reporting it |
| **Community & status-quo behaviour** | WhatsApp/Discord course groups, walking over to look | Free, instant, and what people actually do today |

---

## Detailed Analysis

### A. Google Maps — Popular times & Live busyness

The strongest competitor, because it is already installed, already trusted, and costs
the user nothing.

| Axis | Assessment |
|---|---|
| **Target users** | The general public; any visitor to any mapped business |
| **Principal features** | Historical "Popular times" bar chart per hour; "Live busyness" overlay (quiet / moderately busy / very busy); estimated wait time and typical visit duration for some venues; area busyness |
| **Strengths** | Enormous passive data volume; **zero user effort**; no cold-start problem; refreshed every few minutes; already a habit |
| **Weaknesses** | Granularity is the **business entity**, not a point of interest inside a building — no per-floor, per-counter or per-service breakdown. Non-commercial POIs (academic services desks, vending areas, individual library floors) are typically not mapped as businesses at all. Reports **occupancy, not queue length** — a full library with no queue and a half-empty canteen with a 20-minute line look similar. No personalized anomaly alerts: it answers "how busy is it?" only when the user thinks to ask. No campus semantics (opening hours of a specific service, closures, exam periods) |
| **Business model** | Free to users; funded by advertising and the wider Maps/Search ecosystem |
| **UX** | Excellent and familiar, but **pull-only** — the user must already have decided to look up a place |
| **Privacy & trust** | Derived from aggregated, anonymized Location History, which is **off by default** and requires continuous background location tracking to contribute. Trusted as a brand, but the data depends on users accepting broad location surveillance, and coverage silently degrades where too few users opted in |

**Implication for CampusFlow:** do not compete on breadth or on passive convenience —
compete on **granularity inside buildings, queue semantics, and push-on-anomaly**.

### B. Waitz (Occuspace) — sensor-based campus occupancy

The closest existing product to CampusFlow's problem statement, and the most important
one to address honestly in front of the investors.

| Axis | Assessment |
|---|---|
| **Target users** | Students and staff at contracted universities; facilities and space-planning teams as the paying side |
| **Principal features** | Real-time busyness per space and **per library floor**; comparison against the previous week; free web, iOS and Android app for students; occupancy analytics for facilities teams |
| **Strengths** | **Per-floor granularity** — the thing Google Maps cannot do; vendor reports ~90% accuracy with de-duplication of multi-device users; **no user effort at all**; adopted at Purdue, Columbia, UCLA and UC San Diego (70+ monitored spaces at UCSD), so the concept is institutionally validated |
| **Weaknesses** | Requires **physical sensor hardware** in every monitored space, so coverage is a capital-expenditure decision, not something the community can extend; measures **device density, not queue state** — a counter with 8 people waiting is invisible if the room is otherwise empty; no community input, so **no free-text context** ("only one till open", "card machine down") and no photos; no user-level personalization or favourite-based anomaly alerts; closed vendor platform — the institution cannot adapt it |
| **Business model** | B2B SaaS plus hardware, sold to the institution; free to end users because the university pays |
| **UX** | Clean and effortless, but strictly read-only: users consume, never contribute or correct |
| **Privacy & trust** | Strong posture — passive Bluetooth/Wi-Fi density scanning with the explicit claim that individuals are not tracked. However it is **non-consensual by design** for passers-by, who cannot opt out of being counted, and trust rests entirely on the vendor's assurances rather than on anything the community can inspect |

**Implication for CampusFlow:** Waitz proves the demand but leaves two real gaps.
First, it needs institutional budget and installed hardware — CampusFlow needs neither,
so it can cover POIs nobody would ever buy a sensor for. Second, sensors cannot
express *why* a queue is slow; people can. This is the strongest argument for a
community-sourced approach, and it should be made explicitly rather than pretending no
competitor exists.

### C. Institutional channels (Portal ISEP, Moodle, website notices)

| Axis | Assessment |
|---|---|
| **Target users** | Enrolled students, teaching and non-teaching staff |
| **Principal features** | Academic information, timetables, announcements, administrative services; the Portal ISEP app gives mobile access to the main portal features |
| **Strengths** | **Authoritative** — the source of truth for closures, schedule changes and official notices; already reaches the entire community; identity is already established |
| **Weaknesses** | **Static and asynchronous** — publishes notices, not live state; nothing about current occupancy or queues; information is pull-based and often not read in time; no map or per-floor view |
| **Business model** | Institutionally funded infrastructure; not a market product |
| **UX** | Functional and administrative rather than designed for a 10-second "should I go now?" decision |
| **Privacy & trust** | High trust as an official channel; operates on already-held institutional data under the institution's own policies |

**Implication for CampusFlow:** this is a **complementor, not a competitor**. Official
announcements are exactly the kind of verified external data the product should ingest
and display alongside community reports, with clear provenance. It is also the natural
candidate for the mandatory external-system integration (brief §6.5).

### D. Queue management & order-ahead systems

Covers ticket dispensers and digital queue platforms (Qminder, TablesReady, virtual
waiting rooms) and canteen order-ahead apps (CampusBite, Smart College Canteen,
Queuetie, CampusQueue).

| Axis | Assessment |
|---|---|
| **Target users** | The service operator first (canteen, academic services desk); students as a secondary audience |
| **Principal features** | Join a queue remotely and hold a place; service-aware wait estimates based on what the people ahead actually requested; order and pay ahead to skip the line; operator dashboards and analytics |
| **Strengths** | **Attacks the queue itself rather than reporting it** — strictly more valuable when adopted; estimates can be genuinely accurate because they are computed from real service records, not inferred |
| **Weaknesses** | Requires **operator adoption and process change** per service point — outside the team's control and far beyond an MVP's reach; each deployment covers one service, giving no cross-campus view; order-ahead only works where there is something to order, so it does nothing for libraries, study rooms or academic services; useless to a user before they have committed to that specific service |
| **Business model** | B2B SaaS per site or per service point, sometimes with transaction fees |
| **UX** | Good within one service; fragmented across campus — a different app or flow per location |
| **Privacy & trust** | Handles identity, order history and sometimes payment data, so a materially larger personal-data footprint than occupancy reporting |

**Implication for CampusFlow:** a real long-term threat, but one that cannot be deployed
unilaterally. It belongs in the roadmap discussion (a POI operator could eventually
publish authoritative queue data into CampusFlow), not in the MVP.

### E. Community chats (WhatsApp / Discord course groups)

| Axis | Assessment |
|---|---|
| **Target users** | Students, within their own course or year group |
| **Principal features** | Ask "is the canteen full?" and get an answer from whoever is there; photos; free-text context |
| **Strengths** | **Zero friction and already universal**; answers carry nuance a sensor never will; the responder is socially accountable, so trust is high; completely free |
| **Weaknesses** | **Does not scale or aggregate** — the answer helps one asker at one moment and is then lost; depends on someone being both present and willing to reply; no history, no trend, no coverage guarantee; excludes anyone outside the group (staff, first-year students, other courses); noisy and easily buried |
| **Business model** | None — free consumer messaging |
| **UX** | Instant and conversational, but **synchronous**: a question with no answer is a dead end |
| **Privacy & trust** | Data sits in commercial messaging platforms; socially high trust inside the group, no verifiability outside it |

**Implication for CampusFlow:** this is the behaviour the product should **formalize and
make persistent**, not replace. It is also direct evidence that the willingness to share
status already exists — which de-risks the voluntary check-in assumption recorded in
[`01-problem-opportunity.md`](01-problem-opportunity.md).

### F. Status quo — walking over to look

| Axis | Assessment |
|---|---|
| **Target users** | Everyone, by default |
| **Principal features** | Direct observation |
| **Strengths** | **100% accurate and instantly trusted**; needs no technology, no account and no network |
| **Weaknesses** | The cost *is* the problem — the wasted walk, and the decision cannot be made in advance. Scales badly when the break is 15 minutes; no way to compare two options without visiting both |
| **Business model** | Free |
| **UX** | No interface, no learning curve, no failure mode |
| **Privacy & trust** | Perfect on both counts |

**Implication for CampusFlow:** this is the **baseline to beat**, and the reference point
for the measurable outcome. Any estimate the product shows must be trustworthy enough
that a user is willing to act on it *instead of* going to look — which sets the bar for
freshness, confidence indicators and honest handling of stale data.

---

## Feature Comparison Matrix

| Capability | Google Maps | Waitz | Portal ISEP | Queue/order-ahead | Group chats | Walk over | **CampusFlow** |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Real-time state | ● | ● | ○ | ● | ◐ | ● | ● |
| Per-floor / per-POI inside a building | ○ | ● | ○ | ◐ | ◐ | ● | ● |
| Queue length, not just occupancy | ◐ | ○ | ● | ◐ | ● | ● | ● |
| Covers non-commercial POIs (services, vending) | ○ | ◐ | ○ | ◐ | ● | ● | ● |
| Free-text / photo context | ○ | ○ | ○ | ○ | ● | ● | ● |
| Push alerts only on *anomalies* at favourites | ○ | ○ | ◐ | ○ | ○ | ○ | ● |
| No hardware or operator adoption required | ● | ○ | ● | ○ | ● | ● | ● |
| Works without tracking the user continuously | ○ | ● | ● | ◐ | ● | ● | ● |
| Aggregates and persists for trend analysis | ● | ● | ○ | ● | ○ | ○ | ● |
| Zero effort from the user | ● | ● | ● | ○ | ◐ | ○ | ○ |

● full · ◐ partial · ○ absent

The matrix makes the trade-off explicit: **CampusFlow's one structural disadvantage is
that it asks users for effort.** Every competitor that matches it on granularity either
buys hardware (Waitz) or requires operator adoption (queue systems). That is the bet the
product is making, and the cold-start risk already logged in
[`01-problem-opportunity.md`](01-problem-opportunity.md) is its direct consequence.

---

## Strengths & Weaknesses — Synthesis

**What the incumbents collectively do well, and CampusFlow must at least match:**

1. **Effortlessness.** Google Maps and Waitz ask nothing of the user. Any check-in flow
   that takes more than a few seconds loses to them outright.
2. **Trustworthiness.** Walking over is perfectly accurate. A visibly stale or wrong
   estimate is worse than no estimate, because it costs the user a wasted trip *and*
   their confidence.
3. **Authority.** Institutional channels are believed. Community reports must never be
   presented with the same confidence as a verified official notice.

**Where all of them leave a gap:**

1. **No one reports the queue.** Sensors and passive location data measure *how many
   devices are present*. Nobody measures *how long you will wait* at the granularity of
   a counter or a service desk.
2. **No one pushes on anomalies.** Every alternative is pull-based. The daily-routine
   user — who already knows the canteen is busy at 12:30 — gains nothing from being told
   so; they only need to be told when **today is unusual**.
3. **No one carries context.** "Two tills closed", "machine out of order", "event in the
   atrium" is exactly the information that explains an anomaly, and only people can
   supply it.
4. **Coverage is decided top-down.** Sensor and queue deployments cover what the
   institution paid for. A community-sourced POI list can grow wherever users care.

---

## Opportunity for Differentiation

Four defensible differentiators, in order of strength:

1. **Queue semantics at intra-building granularity.** Report and estimate the *wait*,
   per POI and per floor, including POIs no vendor would instrument — vending areas,
   individual academic-services desks, specific library floors. Neither Google Maps
   (wrong granularity) nor Waitz (wrong measurement) does this.
2. **Anomaly-triggered notifications on favourites.** Deliberately **not** a live feed.
   The product learns a user's usual places and stays silent until the current state
   departs from the normal pattern for that place and time — then it alerts and proposes
   a faster alternative. This is the clearest product-level differentiator and the one
   that avoids notification fatigue.
3. **Human context, not just numbers.** A short note or photo attached to a check-in
   explains the anomaly. This is structurally impossible for sensor-based competitors
   and is where the AI opportunity sits — reconciling, de-duplicating and summarizing
   multiple concurrent reports into one trustworthy statement with a visible confidence
   level (feeds [#11](../../issues/11)).
4. **No infrastructure, no operator dependency.** Deployable by the community itself,
   with zero capital cost and no process change at any service point — the reason this
   is achievable as a student MVP where Waitz is not.

**Where CampusFlow should not try to compete:** breadth of coverage beyond one campus,
effortless passive sensing, and transactional flows (ordering, payment, holding a place
in a queue). Those are the incumbents' home ground.

---

## Resulting Value Proposition

> For students and staff on a university campus, **CampusFlow** turns the question
> "is it worth walking over?" into a 10-second, trustworthy answer — down to the floor
> and the counter, including the places no sensor will ever cover — and stays quiet
> until one of *your* usual spots is unusually busy, at which point it tells you and
> offers a faster alternative.
>
> Unlike passive crowd data, it reports **waiting**, not just presence, and carries the
> human context that explains it. Unlike sensor platforms, it needs no hardware and no
> institutional budget. Unlike a group chat, every report helps everyone and builds a
> picture that lasts.

**The competitive bet in one sentence:** that a community will contribute a few seconds
of effort in exchange for information that no amount of passive sensing can produce —
and that honest confidence indicators will make that information trusted enough to act
on.

---

## Decisions This Analysis Feeds

| Finding | Feeds into |
|---|---|
| Effortlessness is the incumbents' main advantage → check-in must stay ~3s, and contribution must never be a precondition for reading | Product Vision [#9](../../issues/9), Backlog [#10](../../issues/10) |
| Stale or over-confident estimates are worse than none → freshness, confidence and provenance must be first-class in the UI | Vision [#9](../../issues/9), Responsible AI [#11](../../issues/11) |
| Waitz already proves demand but cannot express *why* a queue is slow → the AI opportunity is reconciling and summarizing concurrent human reports, not counting people | Responsible AI [#11](../../issues/11) |
| Institutional channels are complementors → ingest official notices as verified external data | Technical Design [#12](../../issues/12), external integration (§6.5) |
| Anomaly detection, not a live feed, is the differentiator → it must be a core MVP capability, not a later nice-to-have | Vision [#9](../../issues/9), Backlog [#10](../../issues/10) |
| Community-sourced data invites manipulation, and photos carry third-party faces → trust and privacy controls are product features, not hardening | Security & Privacy [#14](../../issues/14) |

---

## Limitations of This Analysis

- **Desk research only.** No competitor was trialled on the ISEP campus, no vendor was
  contacted, and no pricing was obtained. Vendor-published accuracy figures (such as
  Occuspace's ~90% claim) are **vendor claims**, reported as such and not independently
  verified.
- **No confirmed Waitz/Occuspace deployment in Portugal** was found; the adoption
  evidence is from US institutions. Whether a Portuguese institution would buy such a
  system is unknown and affects how threatening this competitor really is here.
- **ISEP-specific claims are unverified** — see the warning at the top. The Portal ISEP
  Android listing found during research dates from 2015, so current app capabilities may
  differ substantially from what public pages suggest.
- **No user-side evidence yet.** This analysis establishes what alternatives *exist*, not
  which ones campus users actually use or would switch from. That is the job of
  [`03-user-research.md`](03-user-research.md) ([#8](../../issues/8)), and the
  differentiators above should be treated as **hypotheses until it lands**.
- **Queue/order-ahead products are a fast-moving category** and the examples cited range
  from commercial platforms to student projects of varying maturity; they are treated
  here as a category, not as individually benchmarked products.

---

## Sources

Accessed 2026-10-01.

- Google Maps Help — *Get information about busy areas from Google Maps*:
  <https://support.google.com/maps/answer/11323117>
- CNBC — *Google Maps popular times shows you wait times*:
  <https://www.cnbc.com/2018/08/04/google-maps-popular-times-shows-you-wait-times.html>
- Engadget — *How Google Maps knows when a business is packed*:
  <https://www.engadget.com/2252763/how-google-maps-knows-businesses-packed/>
- Campus Technology — *Occuspace Expands Occupancy Monitoring to More Colleges and
  Universities*:
  <https://campustechnology.com/articles/2022/11/17/occuspace-expands-occupancy-monitoring-to-more-colleges-and-universities.aspx>
- Columbia University (Teachers College Library) — *The Wait is Over: Waitz is Here*:
  <https://library.tc.columbia.edu/blog/content/2023/december/the-wait-is-over-waitz-is-here.php>
- UC San Diego Library — *Creating Smarter Spaces with Smart Technology*:
  <https://library.ucsd.edu/news-events/creating-smarter-spaces-with-smart-technology/>
- Occuspace — product and case-study pages: <https://www.occuspace.com/>
- Portal ISEP (Microsoft Store listing):
  <https://apps.microsoft.com/detail/9WZDNCRDJLPZ>
- ISEP — Campus pages: <https://www.ipp.pt/colleges/isep/campus>
- Qminder — *Student Queue Management System for Schools & Universities*:
  <https://www.qminder.com/education/>
- CrowdHandler — *Smoothing the Queue: How Universities Can Improve Student Experience
  with Virtual Waiting Rooms*:
  <https://www.crowdhandler.com/blog/smoothing-the-queue-how-universities-can-improve-student-experience-with-virtual-waiting-rooms>
- Queuetie (Medium) — *Revolutionizing Canteen Crowd Management with the Queuetie App*:
  <https://medium.com/@mengyi233/revolutionizing-canteen-crowd-management-with-the-queuetie-app-c4f20afe202b>
- QueueWise (GitHub) — crowdsourced waiting-time platform:
  <https://github.com/kogleshofficial-hub/queuewise>
- CampusBite (GitHub) — canteen management platform:
  <https://github.com/Jaswant-Karun/CampusBite>
- CampusQueue (GitHub) — campus queue management system:
  <https://github.com/rajaditya954/CampusQueue>

*AI assistance (Claude) was used to support the research and drafting of this document;
all content was reviewed by the author, and unverified claims are flagged as such, in
line with the project's code of conduct.*
