# Test Strategy - Smart City Operations Platform

## Product model
A fictional platform receives city incidents from operators and sensors. Dispatchers work in a web dashboard; field staff use a mobile client. Some incidents may create paid service requests and CRM follow-up tasks.

## Quality risks
1. Real-time state becomes stale between clients.
2. Duplicate user actions create duplicate payments or incidents.
3. Permissions expose restricted data.
4. Mobile reconnect produces an incorrect local state.
5. Background processing fails while UI still shows success.
6. CRM workflow loses links between customer, request and incident.

## Test levels
- smoke on each deploy;
- focused functional testing per story;
- API checks for high-risk flows;
- regression before release;
- exploratory sessions around changed/high-risk areas.

## Prioritization
**P0:** login, incident creation, incident status change, payment submit, role access.  
**P1:** filters, CRM workflow, reconnect, audit trail.  
**P2:** cosmetic and low-frequency edge cases.

## Environments / evidence
For every defect capture build, account/role, timestamp, request/response, correlation ID when available, logs and screenshots/video when UI timing matters.
