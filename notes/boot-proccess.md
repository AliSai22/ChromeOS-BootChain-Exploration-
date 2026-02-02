# ChromeOS Boot Chain Overview

This file documents my observations and studies of the ChromeOS boot procces based on my experiments with hardware I own. My focus is on understanding **system integrity and verification mechanisms**.


## Boot Flow

1. **Firmware**
   - Initializes the hardware
   - Verifies the bootloader signature
   - Ensures the device is not tampered with

2. **Bootloader**
   - Loads and verifies the kernel
   - Checks for developer mode status
   - Enforces verified boot policies

3. **Kernel**
   - Verifies the OS partitions
   - Mounts read-only and writable partitions according to security rules

4. **OS / User Space**
   - Runs the ChromeOS system services
   - Maintains verified partitions
   - Provides recovery mechanisms if integrity checks fail

## Observations

- Enabling **Developer Mode** changes some verification behavior but read-only partitions remain protected.
- Verified Boot prevents long-term unauthorized modifications to system-critical files.
- Any attempt to modify partitions outside the expected flow triggers a recovery process.
- ChromeOS balances security and usability by allowing temporary testing (Developer Mode) while protecting critical system integrity.

## Lessons Learned

- The boot chain is designed to **ensure the device starts in a trusted state** every time.
- Security relies on multiple layers: firmware, bootloader, kernel, and OS.
- Observing the boot process helped me understand why ChromeOS is resistant to persistent tampering.
