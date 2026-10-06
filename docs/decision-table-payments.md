# Decision Table - Payment Submission

| Card valid | Funds available | Gateway reachable | Same idempotency key seen | Expected result |
|---|---|---|---|---|
| Yes | Yes | Yes | No | Payment approved, one transaction created |
| Yes | No | Yes | No | Declined, order remains unpaid |
| No | Any | Yes | No | Validation/decline, no payment created |
| Yes | Yes | No | No | Retryable technical failure, no duplicate transaction |
| Yes | Yes | Yes | Yes | Original result returned, no second charge |

## Derived checks
- state in UI matches backend and DB;
- repeated click does not bypass idempotency;
- timeout can be retried safely;
- error text does not expose sensitive gateway details.
