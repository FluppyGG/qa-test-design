# BUG-003 - Read-only CRM role can modify customer through API

**Type:** Authorization  
**Severity:** High  
**Status:** Simulated portfolio defect

## Steps
1. Authenticate as read-only CRM user.
2. Send PATCH request for a customer entity.
3. Refresh customer data.

## Actual
API returns success and persists the change although the UI hides editing controls.

## Expected
Server-side authorization rejects the operation (for example, 403) and data remains unchanged.

## Key point
UI restrictions are not an authorization boundary; permission checks must be enforced on the backend.
