# 03 - Azure Compute (Virtual Machines)

## Lab: VM Disk Management & OS Snapshot Restore

### My Lab Resources (VM-1)
| Resource | Detail |
|---|---|
| VM | VM-1 (West Europe) |
| OS Disk | os-disk-restored — Premium SSD ZRS — 256 GiB |
| Data Disk | data-disk-1 — Premium SSD LRS — 128 GiB |
| Snapshot | vm1-shanpshort-1 — Full — 30 GiB — Zone-redundant |

---

### What I Practiced
- Took OS disk snapshot (vm1-shanpshort-1) as restore point
- Created new managed disk from snapshot
- Swapped OS disk on deallocated VM → booted from restored disk ✅
- Attached data disk and verified with `lsblk` inside Linux VM
- Resized disk from Portal (VM must be deallocated first)
- Detached and deleted data disk

---

### lsblk Output (Inside VM-1)

**Before restore:**

Before: sda=30G (OS) | sdb=16G (temp) | sdc=4G (data, raw)

After:  sdb=256G (OS restored) | sda=128G (data) | sdc=16G (temp
