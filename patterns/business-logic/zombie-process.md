# Pattern: Zombie Process / Orphaned Workflow

## Summary

Zombie Process / Orphaned Workflow occurs when background jobs or workflows continue running without ownership or completion, consuming resources and blocking system operations.

**Keywords**: zombie process, orphaned workflow, stuck jobs, background job failure, workflow timeout issue

---

## Description

Zombie Process / Orphaned Workflow happens when background jobs, transactions, or workflows continue running without ownership, visibility, or proper completion paths.

---

## Real-World Examples

- **Order Processing Workflow**
  - Order stuck in “processing”
  - Never completes → blocks fulfilment

- **Batch Job Failure**
  - Worker crashes mid-process
  - Job continues in limbo → consumes resources

- **Cloud Resource Lock**
  - Resource reserved but never released
  - Prevents new allocations

- **Workflow Engine Failure**
  - Orchestrator loses state
  - Workflow continues without tracking

---

## Typical Symptoms

long-running stuck jobs  
orders stuck in processing  
resources not released  
unexpected capacity usage  
manual cleanup required  

---

## Common Misleading Signals

looks like workflow delay  
appears like queue backlog  
seems like DB lock  
blamed on slow dependency  
appears as noise  

---

## Likely Root Causes

missing timeouts  
worker crashes  
lost ownership tracking  
failed cleanup handlers  
incomplete recovery paths  

---

## First Checks

identify stale workflows  
check worker crash logs  
validate timeout configs  
review ownership tracking  
compare expected vs active processes  

---

## Useful Signals

workflow age metrics  
worker failure logs  
orphaned resource dashboards  
cleanup failures  
stale transaction monitoring  

---

## Prevention

explicit timeouts  
ownership tracking  
auto cleanup  
recovery testing  
orphan detection alerts  

---

## When to Suspect This Pattern

- Long-running processes with no progress  
- Resource usage without visible activity  
- Jobs stuck indefinitely  
- Manual cleanup required repeatedly  

---

## Expected Impact

- Resource exhaustion  
- Workflow blockage  
- Operational overhead  
- Delayed business processes  

---

<a href="../../README.md#business-logic-patterns" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
