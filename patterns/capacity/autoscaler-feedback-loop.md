# Pattern: Autoscaler Feedback Loop Failure

## Summary

Autoscaler Feedback Loop Failure occurs when scaling systems react too slowly, too aggressively, or based on misleading signals, causing instability instead of recovery.

**Keywords**: autoscaler failure, scaling instability, Kubernetes autoscaling issue, HPA oscillation, cloud scaling problem

---

## Description

Autoscaler Feedback Loop Failure happens when scaling systems respond too slowly, too aggressively, or based on misleading signals, causing instability instead of recovery.

Instead of stabilising the platform, scaling actions amplify the incident through oscillation, delayed recovery, or resource waste.

---

## Real-World Examples

- **Kubernetes HPA Oscillation**
  - CPU spikes trigger scale-up
  - New pods start too slowly
  - Existing pods overloaded before recovery

- **Flash Sale Scaling Failure**
  - Traffic surges rapidly
  - Autoscaler reacts late
  - Service collapses before capacity catches up

- **Cold Start Amplification**
  - Serverless platform scales aggressively
  - Cold starts increase latency
  - More scaling triggered unnecessarily

- **Misleading CPU Metrics**
  - Dependency latency causes request backlog
  - CPU remains low
  - Autoscaler never reacts appropriately

---

## Typical Symptoms

services repeatedly scale up and down  
latency remains high despite scaling  
new instances fail to reduce pressure  
cost spikes during incidents  
resource exhaustion despite autoscaler activity  

---

## Common Misleading Signals

looks like autoscaler is working correctly  
appears like traffic unpredictability  
seems like dependency bottleneck  
blamed on deployment quality  
appears as random capacity failure  

---

## Likely Root Causes

slow scaling thresholds  
incorrect target metrics  
cold start delays  
scaling based on lagging indicators  
insufficient maximum capacity settings  

---

## First Checks

review autoscaler event history  
validate scaling trigger metrics  
check instance startup times  
inspect maximum scaling limits  
compare scaling activity with traffic spikes  

---

## Useful Signals

autoscaler event logs  
CPU and latency scaling graphs  
instance startup duration metrics  
resource saturation dashboards  
traffic versus capacity comparisons  

---

## Prevention

better autoscaler tuning  
faster startup paths  
predictive scaling for known events  
safe scaling limits  
autoscaler simulation testing  

---

## When to Suspect This Pattern

- Scaling events happen repeatedly  
- Capacity increases but performance does not improve  
- Costs spike during incidents  
- Traffic patterns do not match scaling behaviour  

---

## Expected Impact

- Resource waste  
- Increased cloud costs  
- System instability  
- Delayed incident recovery  

---

<a href="../../README.md#capacity-patterns" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
