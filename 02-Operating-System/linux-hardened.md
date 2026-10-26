# The *linux-hardened* Kernel

**Threat Mitigated:** Kernel-level exploits, memory corruption attacks, and information leaks.

## The Why Behind This

The standard Linux kernel is designed for maximum compatibility and performance, this is good for user experience but in some areas it is horrible for security purposes and privacy. Some security features are disabled by default to avoid breaking older software or specific hardware configurations in the base OS.

To close these gaps, I took the time to setup the **linux-hardened** kernel. This kernel upgrade is available in the *AUR* and offers a huge list of security upgrades. It is essentially a custom kernel patch that applies aggressive security mitigations directly into the kernel's source code.

## The Key Security Features

By switching to this kernel instead of using the default Linux kernel you obtain a multitude of security upgrades, these protections include:

*  **Stricter Memory Protections:** It enables advanced **Address Space Layout Randomization** or **ASLR** and memory corruption mitigations to make buffer overflow exploits much harder to execute on your system.

*  **Restricted `dmesg` Access:** By default, it restricts unprivileged users from reading the kernel ring buffer, also called `dmesg`, which prevents attackers from leaking kernel memory addresses.

*  **`kptr_restrict`:** It hides the kernel pointers from unprivileged processes, making it harder to build reliable privilege escalation exploits on your machine.

## Some Trade Offs

**Hardware Compatibility:** Because the kernel is so strict in this state, some proprietary drivers (looking at you **NVIDIA** *cough* *cough*) or some *out-of-tree* Wi-Fi adapters may fail to compile or load.

**Mitigation:** If you rely on these drivers, you must use the **DKMS** version and ensure your system can rebuild the kernel modules on every update.

## The Verdict

For my hardware setup with Intel integrated graphics the linux-hardened kernel runs flawlessly. The peace of mind knowing that the standard kernel exploits are significantly harder to execute is worth the extremely minor maintenance overhead.

## How to Verify it

You can verify if you have it properly installed by checking the running kernel's version via the command:

```uname -r```
