# ChromeOS Verified Boot Study

This file documents my hands-on observations and study of **Verified Boot** on ChromeOS using hardware I own. The focus is on understanding **how the system ensures integrity from firmware to OS partitions**.

## Overview

Verified Boot is a key security feature of ChromeOS designed to:

- Ensure the device starts in a trusted state
- Prevent persistent tampering with system-critical files
- Detect and recover from unauthorized modifications

## Observations

- **Boot Verification**
  - The firmware checks the bootloader signature.
  - The bootloader verifies the kernel and OS partitions.
  
- **Integrity Enforcement**
  - Any modifications to system-critical partitions trigger automatic recovery.
  - Even in Developer Mode, Verified Boot maintains protections for read-only partitions.

- **Recovery Mechanisms**
  - When verification fails, the system initiates recovery without user intervention.
  - This enforces integrity while allowing safe experimentation in Developer Mode.

- **Partition Behavior**
  - Read-only partitions remain protected at all times.
  - Writable partitions are limited to non-critical areas, supporting safe testing.

## Lessons Learned

- Verified Boot enforces a **chain of trust from firmware to OS**, preventing unnoticed tampering.
- Observing its behavior clarified why ChromeOS remains secure even with Developer Mode enabled.
- The study highlighted trade-offs between **system flexibility and security guarantees**.
- Understanding Verified Boot reinforced concepts about OS hardening, secure boot chains, and system recovery processes.
