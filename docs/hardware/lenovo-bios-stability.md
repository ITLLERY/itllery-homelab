# Lenovo BIOS and CPU stability notes

**Checked:** 2026-10-21  
**Documented:** 2026-11-22  
**Scope:** My two Lenovo-based Proxmox hosts. These are historical observations from my own terminal checks, not new tests on the documentation date.

I checked the BIOS versions, active Intel microcode and system logs because both servers use 13th-generation Intel Core processors. I also wanted to see whether the machines would remain stable during a short workload test.

## BIOS and running microcode

| System | CPU | BIOS version | BIOS release date | Running Linux microcode |
| --- | --- | --- | --- | --- |
| SOC Core — Lenovo ThinkStation P3 Tower | Intel Core i9-13900K | **S0IKT78A** | 2025-07-30 | **0x132** |
| Service Proxmox — Lenovo platform | Intel Core i7-13700K | **S0IKT72A** | 2024-12-24 | **0x132** |

These are the values I saw on **21 October 2026**. The active microcode was reported after Linux booted. It can be loaded by the operating system, so **0x132 does not by itself tell me which microcode is embedded in the BIOS firmware**. I haven't rechecked the versions for this November documentation update.

For the SOC Core, the system reported an early update from **0x12F** to **0x132**. The Service Proxmox host reported an update from **0x12B** to **0x132**.

## What I tested

### SOC Core — i9-13900K

I checked the kernel logs for MCE, hardware, cache, parity and thermal errors. There were no matching entries in the checks I ran. The EDAC counters showed **CE=0 and UE=0** for the reported memory controllers.

I then ran a **five-minute CPU stress test**, which completed successfully. The CPU package temperature was about **41°C after the test**. I checked the logs again over the next ten minutes and didn't find new hardware errors.

### Service Proxmox — i7-13700K

I ran a CPU test with **8 workers at 70% load for 120 seconds**. It completed with **8 passes and 0 failures**, and the observed temperature during the test was around **45°C**.

I also ran a verified RAM workload using **2 workers for 180 seconds**. Both passed, with **0 failures**. Afterwards, my checks found no matching kernel MCE, EDAC, hardware, lockup or thermal errors, and no failed systemd services.

## What I can conclude

**During my October 2026 checks, neither Lenovo system showed signs of CPU instability or hardware errors.** Both completed the workloads I tested, and I didn't find relevant errors in the logs I reviewed.

That is **not the same as proving that the CPUs have never degraded**. A short stress test, clean logs and a current running microcode value cannot rule out every kind of physical degradation or predict future stability. I would need repeated, longer tests and additional diagnostics to make a stronger claim.

I keep real host identifiers, internal management addresses and raw device logs private. This page records only the versions and test results needed to explain what I checked.
