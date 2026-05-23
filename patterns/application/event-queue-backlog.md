# Pattern: Event Queue Backlog

## Summary

Event Queue Backlog occurs when event producers generate messages faster than consumers can process them, causing queue growth, processing delays, and eventual system overload.

**Keywords**: event queue backlog, consumer lag, message queue overload, Kafka lag, queue depth issue, async processing delay

---

## Description

Event Queue Backlog occurs when events are produced faster than they can be consumed, causing queues to grow uncontrollably.

This is common in systems using message brokers or asynchronous processing pipelines.

As backlog grows, event processing delays increase and downstream services become overwhelmed.

---

## Real-World Examples

- **Kafka Consumer Lag in Microservices**
  - Producer spikes traffic
  - Consumers cannot keep up → lag increases → delayed processing

- **Order Processing System**
  - Orders placed rapidly during sale
  - Queue builds up → fulfilment delayed by hours

- **Email Notification System**
  - Event backlog delays email sending → users receive notifications late

- **Payment Event Pipeline**
  - Payment events queued
  - Downstream reconciliation delayed → inconsistent financial reporting

---

## Typical Symptoms

- Growing message queue depth  
- Delayed event processing  
- Consumer lag  
- Increased system latency  
- Worker saturation  

---

## Common Misleading Signals

- Slow consumers  
- Broker instability  
- Application performance issues  

---

## Likely Root Causes

- Slow event consumers  
- Consumer crashes  
- Downstream dependency delays  
- Insufficient worker scaling  
- Event burst spikes  

---

## First Checks

- Queue depth metrics  
- Consumer processing rate  
- Event production rate  
- Worker health  
- Broker performance  

---

## Useful Signals

- Increasing consumer lag  
- Worker saturation metrics  
- Event processing latency  

---

## Prevention

- Consumer autoscaling  
- Rate limiting on producers  
- Dead letter queues  
- Backpressure mechanisms  

---

## Searchable Structure

**Category**: Application Failure Patterns  

**Tags**:
- queue-backlog
- consumer-lag
- async-processing
- kafka-issue
- message-queue

**Aliases**:
- kafka lag increasing
- queue growing uncontrollably
- events not being processed
- delayed message processing
- consumer cannot keep up

---

## When to Suspect This Pattern

- Queue depth continuously increasing  
- Consumers appear healthy but lag persists  
- Event delays increase over time  
- System slows gradually rather than suddenly  

---

## Expected Impact

- Delayed workflows  
- Data processing lag  
- Customer-facing delays  
- Downstream service overload  

---

<a href="../../README.md#applications-patterns" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
