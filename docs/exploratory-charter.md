# Exploratory Charter - Real-Time Incident Board

**Mission:** Find synchronization and stale-state defects when two clients edit the same incident under unstable connectivity.

## Setup
- Browser A: dispatcher
- Browser B: supervisor
- Mobile emulator/device: field user
- Network throttling available in DevTools

## Explore
- simultaneous status changes;
- disconnect/reconnect during update;
- repeated action while request is pending;
- tab sleeping/backgrounding;
- permission change while session remains active;
- server error after optimistic UI update.

## Evidence to capture
Timeline, account/role, websocket/network frames if applicable, REST requests, UI state on every client, logs and final DB state.
