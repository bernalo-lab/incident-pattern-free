# Pattern: Idempotency Failure

## Summary

Idempotency Failure occurs when repeated execution of the same operation produces duplicate or inconsistent results instead of safely returning the same outcome.

**Keywords**: idempotency failure, duplicate transactions, retry duplication, distributed systems bug, payment duplication, event replay issue

---

## Description

Idempotency Failure happens when the same operation is processed multiple times and produces different or duplicate outcomes instead of safely returning the same result.

This creates financial errors, duplicate records, repeated notifications, and inconsistent workflow behaviour, especially in distributed systems with retries and async processing.

---

## Real-World Examples

- **Payment API Duplication**
  - Client retries payment request
  - No idempotency key → customer charged twice

- **Order Creation Issue**
  - Network timeout triggers retry
  - System creates two orders instead of one

- **Notification System**
  - Event replay triggers multiple emails → customer receives duplicates

- **Inventory Management**
  - Same purchase processed twice → stock reduced incorrectly

---

## Typical Symptoms

duplicate payments created  
multiple orders for one request  
repeated customer notifications  
unexpected inventory reduction  
inconsistent transaction history  

---

## Common Misleading Signals

looks like user submitted twice  
appears like frontend bug  
seems like payment gateway issue  
blamed on retry infrastructure  
appears as random business error  

---

## Likely Root Causes

missing idempotency keys  
retry logic without deduplication  
race conditions during writes  
partial transaction commits  
event replay without safeguards  

---

## First Checks

verify duplicate request identifiers  
check retry history  
inspect transaction boundaries  
review event replay logs  
compare request timestamps  

---

## Useful Signals

duplicate transaction logs  
request correlation IDs  
retry event history  
payment processing traces  
database write timestamps  

---

## Prevention

idempotency keys  
deduplication layers  
safe retry design  
transaction boundary validation  
event replay controls  

---

## Searchable Structure

**Category**: Business Logic & Workflow Failure Patterns  

**Tags**:
- idempotency-failure
- duplicate-transactions
- retry-duplication
- event-replay
- distributed-systems

**Aliases**:
- duplicate payment issue
- same request processed twice
- retry caused duplicate transaction
- idempotency key missing
- duplicate order created

---

## When to Suspect This Pattern

- Duplicate operations observed  
- Retries correlate with duplicates  
- Same request ID appears multiple times  
- Financial or inventory inconsistencies  

---

## Expected Impact

- Financial loss (double charges/refunds)  
- Data inconsistency  
- Customer trust issues  
- Reconciliation complexity  

---

<a href="../../categories/business-logic/business-logic.md" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
