# Layer 2: Operating System

**Adversary:** Local privilege escalation, malware execution, kernel level exploits, and system tampering overall.

The operating system in which you use is the foundation of everything you do on your system. If the OS you use is bloated, unpatched, or too trusting by default, every application running on top of it is at risk for exploitation by a malicious actor.

My goal for this layer is kernel level hardening and system immutability. I want to shrink the attack surface as much as I possibly can to ensure the system is resilient to tampering and guarantee that I can recover from a catastrophic failure or compromise while still maintaining my system's usability.

# Documentation in this Section

*  **[Arch Linux](./arch-linux.md/)**
*  *Why I chose a rolling release, minimal install distribution as my daily driver.*

*  **[The "linux-hardened" kernel](./linux-hardened.md/)**
*  *Trading out of the box driver compatibility for stricter memory protections and security patches to ensure my system is as safe as can be.*

*  **[Mandatory Acces Control(MAC)](./apparmor-selinux.md/)**
*  *Confining my system's applications to the absolute minimum privileges they need to operate and function correctly.*

*  **[Sysctl Kernel Hardening](./sysctl-hardening.md/)**
*  *Using kernel parameters to restrict information leaks.*

*  **[Btrfs Snapshots & Recovery](./btrfs-snapshots.md/)**
*  *Ensuring system availability and rollbacks after a bad update or compromise.*
