# BUG-002 - Repeated submit can create duplicate payment

**Type:** Payment / idempotency  
**Severity:** Critical  
**Status:** Simulated portfolio defect

## Steps
1. Open unpaid order.
2. Throttle network to Slow 3G.
3. Click Pay twice before the first request returns.

## Actual
Two payment requests are accepted and two transaction records appear.

## Expected
Only one logical payment is processed. Duplicate client actions must reuse/reject the same idempotent operation.

## Evidence to collect
Both request IDs, idempotency keys, timestamps, gateway transaction IDs, backend logs and DB rows.
