# Pattern: Disk IOPS Saturation

## Summary

Disk IOPS Saturation occurs when storage systems reach their read/write operation limits, causing severe latency spikes and degraded application performance.

**Keywords**: disk IOPS saturation, storage bottleneck, database latency, disk queue depth, cloud storage performance issue

---

## Description

Disk IOPS Saturation happens when storage systems reach their input/output operation limits, causing read and write operations to slow dramatically.

Applications may appear healthy at first, but latency grows quickly as requests wait for blocked storage operations.

---

## Real-World Examples

- **Database Write Saturation**
  - Traffic surge increases writes
  - Storage IOPS exhausted
  - API latency spikes across platform

- **Backup Job Interference**
  - Overnight backups consume IOPS
  - Production database performance collapses

- **Index Rebuild Incident**
  - Reindex operation overwhelms storage
  - Customer transactions delayed

- **Cloud Storage Under-Provisioning**
  - New workload exceeds provisioned IOPS
  - Gradual application slowdown occurs

---

## Typical Symptoms

database latency spikes  
slow application response times  
write operations timing out  
high disk wait times  
queue depth growth on storage volumes  

---

## Common Misleading Signals

looks like database bug  
appears like network latency  
seems like CPU bottleneck  
blamed on bad deployment  
appears as dependency slowdown  

---

## Likely Root Causes

unexpected write amplification  
backup jobs competing for IOPS  
index rebuild operations  
high retry write storms  
storage class under-provisioning  

---

## First Checks

review disk IOPS metrics  
check disk queue depth  
inspect backup or batch jobs  
validate database write volume  
compare provisioned vs consumed IOPS  

---

## Useful Signals

disk latency dashboards  
IOPS usage metrics  
storage queue depth  
database write wait events  
backup job execution logs  

---

## Prevention

storage capacity planning  
IOPS monitoring  
workload isolation  
scheduled heavy batch operations  
storage performance testing  

---

## When to Suspect This Pattern

- Latency increases under write-heavy workloads  
- Database wait times increase rapidly  
- CPU remains relatively normal while latency grows  
- Backup or maintenance jobs recently started  

---

## Expected Impact

- Application slowdown  
- Database instability  
- Request timeouts  
- Customer-facing latency spikes  

---

<a href="../../README.md#capacity-patterns" style="min-width:260px; border:1px solid #e5e7eb; border-radius:8px; padding:12px; text-decoration:none;">**<<Back**</a>
