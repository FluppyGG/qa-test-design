# Incident State Model

`NEW -> ACKNOWLEDGED -> IN_PROGRESS -> RESOLVED -> CLOSED`

Allowed exceptional transitions:
- `NEW -> CANCELLED`
- `ACKNOWLEDGED -> CANCELLED`
- `RESOLVED -> IN_PROGRESS` only for reopen-capable role

## Negative checks
- `CLOSED -> IN_PROGRESS` should be rejected;
- field user cannot close an incident if role policy forbids it;
- two simultaneous state changes must resolve deterministically;
- reconnecting mobile client must receive the server-authoritative state.
