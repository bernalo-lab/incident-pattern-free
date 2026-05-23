# Pattern: Retry Storm

## Summary

A Retry Storm occurs when services aggressively retry failed requests, amplifying traffic and overwhelming dependencies, often turning small failures into system-wide outages.

**Keywords**: retry storm, retry amplification, microservices failure, exponential backoff issue, cascading failure, retry overload

---

## Description

A Retry Storm occurs when multiple services repeatedly retry failed requests in a short time window, unintentionally overwhelming the system they depend on.

---

## Real-World Examples

- **API Dependency Failure**
  - Downstream API slows
  - All upstream services retry → API collapses

- **Payment Gateway Timeout**
  - Timeouts trigger retries across services → duplicate transactions + overload

- **Microservices Fan-Out**
  - One failing service → 10 services retry → exponential traffic spike

- **Cloud Outage Scenario**
  - Regional issue triggers retries from thousands of clients simultaneously

---

## Typical Symptoms

- Sudden spike in request volume  
- Rapid increase in error rates  
- Queue depth growth  
- Timeouts between services  
- High CPU usage  
- Duplicate requests  
- Latency spikes  

---

## Common Misleading Signals

- Looks like traffic surge  
- Appears as database failure  
- Autoscaling triggers unexpectedly  
- Dependency appears as root cause  

---

## Likely Root Causes

- Aggressive retry policies  
- No exponential backoff  
- Missing jitter  
- Multiple retry layers  
- Dependency slowdown  
- No circuit breakers  

---

## First Checks

- Retry configuration  
- Downstream error rate  
- Duplicate requests  
- Queue growth  
- Dependency health  

---

## Useful Signals

- Retry logs (`retry attempt=1,2,3`)  
- Request rate spikes  
- Error rate vs success rate divergence  
- Distributed trace duplication  

---

## Prevention

- Exponential backoff  
- Jitter  
- Circuit breakers  
- Retry budgets  
- Observability of retry metrics  

---

## When to Suspect This Pattern

- Traffic spikes without user increase  
- Errors increase alongside traffic  
- Same requests repeated rapidly  
- Downstream service degrades rapidly  

---

## Expected Impact

- System-wide outages  
- Dependency collapse  
- Increased latency  
- Duplicate operations  

---

<a href="../../README.md" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
