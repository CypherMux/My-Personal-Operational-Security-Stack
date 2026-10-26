# Sysctl Kernel Hardening

**Threat Mitigated:** Information leaks, local privilege escalation, and process snooping.

## Why this is so important

Even with a hardened kernel and MAC via AppArmor, the Linux kernel exposes a massive amount of information to unprivileged users by default. An attacker who lands in a low level shell can use this information such as kernel memory addresses or running processes to build an execute a privilege escalation exploit on your system.

`sysctl` allows us to tune the kernel parameters at runtime and restrict this information to harden the system further.

## Implementation

I applied these configurations by creating a dedicated file at `/etc/sysctl.d/total-hardening.conf`. The file can be named anything you want just make sure it has the `.conf` appended to it so the system knows it is a config file. These are the critical parameters In which I enforced on my system:

*  **`kernel.kptr_restrict = 1`**
*  *Why:* This hides kernel pointers from unprivileged users. If an attacker can't see kernel memory addresses, it is much harder for them to write a reliable exploit for memory corruption vulnerabilities.

*  **`kernel.dmesg_restrict = 1`**
*  *Why:* This prevents unprivileged users from running `dmesg` to read the kernel ring buffer. The `dmesg` output often contains sensitive hardware information, memory addresses, or error messages that can aid the attacker. That is why it is so important to enforce this rule on my system.

*  **`kernel.yama.ptrace_scope = 1`**
*  *Why:* This restricts the `ptrace` system call. `ptrace` allows one process to inspect modify another processes memory. By restricting it, even if an attacker compromises one process, they cannot easily use it to snoop on or inject code into another process running as the same user.

*  **`net.core.bpf_jit_harden = 2`**
*  *Why:* This enables strict hardening for the **BPF** or **Berkeley Packet Filter** JIT compiler, which prevents certain types of kernel exploits that abuse BPF.

## How to Verify it

To verify and apply the changes immediately without rebooting you can use the command:

```sudo sysctl --system```

and to verify that a specified setting was applied correctly you can use the command:

```sysctl <name>```

It should return the name of the config setting and the value which you gave it, for example ```kernel.kptr_restrict = 1``` should show up if you correctly applied it to your config file.

## The Trade Off

**Debugging:** If you are a developer trying to debug an app you created these settings will actively fight against you as they are so strict. You may need to temporarily set them back to `0` while using tools such as `gdb` and `strace` for example.

## The Verdict

Since this is my daily driver workstation and not a development server,the security benefits for me personally far outweigh the debugging friction you must fight through.
