# Pattern: Payment State Inconsistency

## Summary

Payment State Inconsistency occurs when payment status differs across systems, such as gateways, internal ledgers, and order systems, leading to financial and operational confusion.

**Keywords**: payment inconsistency, payment mismatch, reconciliation issue, payment gateway mismatch, transaction state error

---

## Description

Payment State Inconsistency happens when payment status differs across systems such as payment gateways, internal ledgers, order systems, and customer records.

---

## Real-World Examples

- **E-commerce Payment Mismatch**
  - Payment gateway shows success
  - Order system shows unpaid → order not fulfilled

- **Refund Discrepancy**
  - Refund processed externally
  - Internal system still shows pending

- **Bank Transfer Issue**
  - Funds debited
  - Credit fails → inconsistent state

- **Subscription Billing**
  - Payment marked failed internally
  - Customer still charged

---

## Typical Symptoms

customer charged but order shows unpaid  
refund completed but account still shows pending  
payment marked failed but funds captured  
reconciliation mismatches  
support tickets increasing  

---

## Common Misleading Signals

looks like gateway outage  
appears like frontend issue  
seems like accounting bug  
blamed on customer payment method  
appears isolated  

---

## Likely Root Causes

missed payment callbacks  
partial transaction commits  
async delivery delays  
retry without reconciliation  
provider timeout ambiguity  

---

## First Checks

compare gateway vs internal state  
review callback logs  
inspect timestamps  
validate reconciliation jobs  
check webhook failures  

---

## Useful Signals

payment gateway callbacks  
ledger logs  
webhook failure events  
reconciliation reports  
support ticket trends  

---

## Prevention

reconciliation jobs  
webhook retry safety  
transaction auditing  
idempotent updates  
callback monitoring  

---

## When to Suspect This Pattern

- Conflicting payment states across systems  
- Reconciliation reports show mismatches  
- Customer complaints about charges  
- Payment callbacks missing or delayed  

---

## Expected Impact

- Financial discrepancies  
- Customer trust loss  
- Manual reconciliation effort  
- Regulatory/compliance risk  

---

<a href="../../categories/business-logic/business-logic.md" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
