# Pattern: Thundering Herd

## Summary

Thundering Herd occurs when many clients or services simultaneously perform the same operation, causing sudden spikes in load and overwhelming shared resources.

**Keywords**: thundering herd problem, cache stampede, request burst, concurrent load spike, distributed systems overload

---

## Description

The Thundering Herd pattern occurs when a large number of clients or services simultaneously attempt to perform the same operation, overwhelming a system resource.

---

## Real-World Examples

- **Cache Expiry Spike**
  - Cache expires
  - Thousands of requests hit DB simultaneously → overload

- **Service Recovery Event**
  - Service comes back online
  - All clients reconnect instantly → crash

- **Scheduled Job Execution**
  - Jobs triggered at same time → CPU spike

- **Token Expiry**
  - All clients refresh token simultaneously → auth service overload

---

## Typical Symptoms

- Burst of identical requests  
- CPU spike  
- Database query surge  
- Cache miss increase  
- Latency spike  
- Lock contention  

---

## Common Misleading Signals

- Traffic spike  
- Database issue  
- Cache malfunction  
- Infrastructure scaling issue  

---

## Likely Root Causes

- Simultaneous cache expiry  
- Synchronized polling  
- Identical scheduling  
- Lock release  
- Service recovery  

---

## First Checks

- Cache TTL alignment  
- Worker polling intervals  
- Scheduled job timing  
- Request burst patterns  
- Lock metrics  

---

## Useful Signals

- Identical requests within milliseconds  
- Request rate spikes  
- Cache miss rate  
- CPU utilisation  
- DB query spikes  

---

## Prevention

- Add jitter/randomisation  
- Stagger schedules  
- Request coalescing  
- Cache warming  
- Rate limiting  

---

## When to Suspect This Pattern

- Sudden spike after a trigger event  
- Many identical requests at same time  
- Resource overload without traffic growth  
- Cache miss spike  

---

## Expected Impact

- Database overload  
- Service degradation  
- Increased latency  
- System instability  

---

<a href="../../categories/application/application.md" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>