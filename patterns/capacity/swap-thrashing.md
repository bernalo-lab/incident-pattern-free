# Pattern: Swap Thrashing

## Summary

Swap Thrashing occurs when systems spend excessive time moving memory pages between RAM and disk swap, causing severe performance degradation and unstable application behaviour.

---

## Description

Swap Thrashing happens when the operating system spends excessive time moving memory pages between RAM and disk swap instead of executing useful work.

This creates severe performance degradation because disk-based memory access is far slower than physical memory access.

---

## Real-World Examples

- **JVM Memory Exhaustion**
  - Heap grows excessively
  - OS begins swapping heavily
  - Application latency becomes unpredictable

- **Container Oversubscription**
  - Too many containers on node
  - Memory pressure triggers swap thrashing

- **Memory Leak Incident**
  - Gradual leak consumes RAM
  - Node performance slowly collapses

- **Virtual Machine Oversubscription**
  - Host memory exhausted
  - Multiple VMs begin swapping simultaneously

---

## Typical Symptoms

extreme latency spikes  
high disk usage with low throughput  
CPU appears busy but work slows down  
application response times become unpredictable  
node performance collapses gradually  

---

## Common Misleading Signals

looks like CPU bottleneck  
appears like disk IOPS issue  
seems like dependency latency  
blamed on traffic spikes  
appears as random node instability  

---

## Likely Root Causes

memory pressure exceeding RAM  
misconfigured JVM heap sizes  
container memory limits too high  
memory leaks  
oversubscribed virtual machines  

---

## First Checks

review swap usage metrics  
inspect memory consumption trends  
check page fault rates  
validate container memory limits  
compare RAM usage against workload patterns  

---

## Useful Signals

swap usage dashboards  
major page fault metrics  
memory pressure alerts  
node performance graphs  
OOM warning logs  

---

## Prevention

proper memory sizing  
swap monitoring alerts  
memory leak detection  
safe container memory limits  
heap tuning and validation  

---

## When to Suspect This Pattern

- Disk activity spikes unexpectedly  
- CPU usage appears high but throughput drops  
- Memory usage steadily increases over time  
- Performance degrades gradually rather than instantly  

---

## Expected Impact

- Severe latency spikes  
- Node instability  
- Application slowdown  
- Potential OOM crashes  

---

<a href="../../categories/capacity/capacity.md" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
