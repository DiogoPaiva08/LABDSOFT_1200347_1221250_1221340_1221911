# CampusFlow Product Vision

## Vision Statement

CampusFlow helps university communities make better decisions about where and when to go by providing trustworthy, real-time information about queues, occupancy, and unexpected crowding across campus.

Our vision is to reduce wasted time and improve the distribution of people across campus facilities, while giving students and staff a simple way to contribute observations and receive only relevant notifications.

## Target Users

### Student Persona

A student who regularly uses the canteen, library, bars, vending areas, and academic services. They want to know whether a place is crowded before walking there or waiting in line.

### Staff Persona

Teaching and non-teaching staff who use campus services and may need to plan visits around busy periods.

### Campus Service Manager Persona

People responsible for facilities and services who need visibility into demand patterns, abnormal crowding, and possible service disruptions.

## Value Proposition

CampusFlow provides:

- Estimated waiting times for important campus locations.
- A map showing the current status of campus points of interest.
- Quick user check-ins that take only a few seconds.
- Queue and crowd-level estimates generated using Computer Vision models from cameras installed at strategic campus locations.
- Alerts when a favourite location becomes unusually crowded.
- Suggestions for less crowded alternative locations.
- Transparent confidence and freshness indicators for reported information.
- AI-assisted analysis of reports or images, always clearly marked as estimated and subject to limitations.

Computer Vision estimates will focus on queue length, crowd level, and occupancy. The system will not use facial recognition or identify individual people.

Unlike static campus maps or isolated service announcements, CampusFlow combines community observations, camera-based estimates, historical data, and external information into one operational view.

## Principal User Journeys

### 1. Check a Location Before Travelling

1. The user opens the campus map through the responsive web application or mobile application.
2. The user selects a location, such as a canteen or library.
3. CampusFlow displays its estimated waiting time, crowd level, last update, and confidence level.
4. The user decides whether to visit the location or choose an alternative.

### 2. Submit a Quick Check-In

1. The user selects a campus location.
2. The user reports the current crowd level or estimated waiting time.
3. The user may optionally add a note or image.
4. The report is validated and processed asynchronously.
5. AI may assist with the classification of the submitted text or image.
6. The location status is updated if the report is considered sufficiently reliable.
7. If the AI service is unavailable, the system uses predefined crowd-level categories and recent reports as a fallback.

### 3. Detect and Estimate Queues Using Campus Cameras

1. Cameras installed at strategic campus locations capture the relevant queue or occupancy area.
2. Computer Vision models analyse the camera input.
3. The models estimate the number of people, queue length, crowd level, and approximate waiting time.
4. The system associates each estimate with a timestamp, freshness indicator, and confidence level.
5. The camera-based estimate is combined with recent user reports and historical data.
6. CampusFlow updates the location status when the result meets the required confidence threshold.
7. The estimate is clearly presented as AI-generated and not as a verified fact.
8. The system does not use facial recognition or identify individual people.
9. When the camera or Computer Vision service is unavailable, CampusFlow continues using recent reports and predefined crowd-level categories.

### 4. Receive a Relevant Alert

1. The user marks a location as a favourite.
2. CampusFlow monitors reports, camera-based estimates, and occupancy patterns.
3. If an unusual crowding event is detected, the user receives a notification.
4. The notification may include a suggested alternative location.
5. The user can dismiss, disable, or configure these notifications.

### 5. Monitor Campus Demand

1. A campus service manager opens the operational dashboard.
2. The dashboard shows crowding trends, recent reports, camera-based estimates, and abnormal situations.
3. The manager identifies locations requiring attention.
4. The manager can publish a verified update or service announcement.
5. AI-generated estimates remain clearly distinguished from manually verified information.

## MVP Definition

The MVP will focus on the most important user journey:

> A student checks the current crowd level of a campus location, submits a report, and receives an updated estimate through the web or mobile application.

The MVP will include:

- A responsive web application.
- A mobile application package based on the same product experience.
- An interactive campus map with a limited set of predefined locations.
- Location detail pages with crowd level, estimated waiting time, timestamp, confidence, and information source.
- Authenticated or mocked-authenticated users.
- Quick crowd-status check-ins.
- Persistent storage for locations, reports, camera estimates, and user favourites.
- At least two backend components:
  - Campus Information Service
  - Report Processing and Notification Service
- An asynchronous workflow for processing submitted reports.
- AI-assisted classification of optional text or image reports.
- Computer Vision models for queue and occupancy estimation at selected strategic locations.
- A non-AI fallback based on predefined crowd-level categories and recent reports.
- Basic alerts for unusual crowding at favourite locations.
- Privacy controls that prevent facial recognition and unnecessary image storage.
- Structured logs, health checks, metrics, and a degraded-mode demonstration.

## Out of Scope for the MVP

The MVP will not initially include:

- Complete indoor navigation for every campus building.
- Facial recognition or identification of individuals.
- Continuous personal tracking.
- Guaranteed accurate waiting-time predictions.
- Integration with all university systems.
- Camera coverage of every campus location.
- Fully automated operational decisions.
- Public leaderboards based on user contributions.

These features may be considered for future releases after validating the core user journey.

## Success Criteria

The MVP will be considered successful if:

- At least 80% of test users can find the status of a selected location without assistance.
- A user can submit a check-in in less than 10 seconds.
- At least 80% of submitted reports are processed and reflected in the system within 30 seconds.
- Computer Vision estimates achieve an agreed classification quality on a documented evaluation dataset.
- The system clearly shows when information is old, uncertain, AI-generated, or unavailable.
- Users who follow an alternative-location suggestion experience a lower reported crowd level than users who remain at the original location.
- The AI-assisted workflow achieves an agreed classification quality on a documented evaluation dataset.
- The main workflow remains usable when the AI service, Computer Vision service, camera, or an external data provider is unavailable.
- No report or camera-based estimate is presented as verified solely because it was generated by AI.

## Product Risks

- Users may not submit enough reports to keep information up to date.
- Reports may be inaccurate, duplicated, malicious, or biased towards certain locations.
- Camera-based estimates may be inaccurate because of poor lighting, occlusion, camera position, or technical failures.
- Waiting-time estimates may create false confidence.
- Notifications may become intrusive or expose a user's routines.
- Image and text reports may contain personal or sensitive information.
- Camera input may accidentally capture identifiable information.
- AI and Computer Vision models may produce incorrect or unfair results.
- External data sources may be delayed or unavailable.
- Users may misunderstand an AI-generated estimate as a verified measurement.

## Ethical Engagement Mechanism

CampusFlow will encourage useful participation through a contribution history showing how many reports a user has submitted and how recently they were confirmed useful.

This mechanism is intended to encourage accurate, timely observations that benefit the entire campus. It will not create a public ranking by default. Users can opt out, and the system will avoid exposing exact movement patterns or personal routines. Suspicious or duplicated submissions will be rate-limited and reviewed through validation rules.

Camera-based processing will focus only on queues and occupancy. CampusFlow will not use facial recognition, identify individuals, or expose personal movement patterns. Images should be processed securely and discarded when they are no longer required.

## Product Vision Summary

CampusFlow aims to become the trusted information layer for everyday movement across university campuses. The first product experiment is intentionally narrow: determine whether timely, community-generated crowd information, combined with privacy-conscious Computer Vision estimates, can help students avoid unnecessary waiting and help campus services react to abnormal demand.