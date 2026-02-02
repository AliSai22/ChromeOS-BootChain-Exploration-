# Developer Mode Observations

This file documents my study and hands-on observations of **ChromeOS Developer Mode** on hardware I own. The purpose is to understand how enabling Developer Mode changes system behavior and security characteristics.

## Overview

Developer Mode is a ChromeOS feature that allows **advanced users to access deeper system functionality**. While it exposes additional flexibility, it also introduces certain security trade-offs.

## Observations

- **Boot Verification Changes**
  - Verified Boot behavior changes slightly in Developer Mode.
  - Some partitions become writable for testing, but critical system partitions remain protected.
  
- **Recovery Prompts**
  - Enabling Developer Mode triggers warnings at boot and requires user consent.
  - Any unintended modifications outside the allowed scope trigger the recovery process.

- **System Access**
  - Developer Mode allows exploration of system logs and files that are otherwise restricted.
  - Does not remove integrity checks on the core OS or critical partitions.

- **Persistence Limits**
  - Changes made in Developer Mode are generally **non-persistent across verified boot failures**.
  - Attempting to tamper with read-only partitions triggers automatic recovery.

## Lessons Learned

- Developer Mode is a **controlled environment for learning and testing**, but ChromeOS maintains critical protections.
- Observing Developer Mode behavior helped me understand **how ChromeOS balances flexibility for developers with system integrity**.
- This study provided insights into **OS hardening, partition management, and verified boot policies**.
