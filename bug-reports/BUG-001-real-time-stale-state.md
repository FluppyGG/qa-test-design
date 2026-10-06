# BUG-001 - Incident card shows stale state after reconnect

**Type:** Real-time synchronization  
**Severity:** High  
**Status:** Simulated portfolio defect

## Preconditions
- Dispatcher A and Supervisor B open incident `INC-42`.
- B loses network connectivity.

## Steps
1. A changes status from `ACKNOWLEDGED` to `IN_PROGRESS`.
2. B remains offline for 30 seconds.
3. Restore B connection.
4. Open incident details in B.

## Actual
List badge refreshes to `IN_PROGRESS`, but details panel remains `ACKNOWLEDGED` until full page refresh.

## Expected
All visible representations use the server-authoritative state after reconnect.

## Evidence to collect
Network timeline, reconnect event, incident GET response, websocket frames if used, client logs and screen recording.
