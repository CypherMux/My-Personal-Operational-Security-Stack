# Intel ME (HAP Mode)

**Threat Mitigated:** Out-of-band remote management, firmware level backdoors, and AMT exploitation.

## Why I Enforce This On My Hardware

Intel Management Engine, or Intel ME for short, is a separate, closed-source microcontroller which is built into each and every modern Intel CPU. It runs its own operating system called MINIX and has direct access to your system's memory, network interface, and disk.

Because it operates independently of the main CPU, it can be accessed out-of-band. What this means is that even if your OS is fully encrypted and offline, a remote attacker or an intelligence agency if you're a big scary hacker man 😲 could theoretically use Intel AMT, or Intel Active Management Technology, to wake, control, or exfiltrate data from your machine.

## Implementation Details

There are two main ways in which you can deal with the Intel ME problem:

**1. Hardware Removal (me_cleaner):** This is not what I did but based off my research into this topic one way to do this is used a tool called **me_cleaner**. What this tool does is it physically flashes the BIOS chip to strip out 99% of the ME firmware on your system. This is extremely risky as it requires external hardware and can brick your motherboard but it does work. 

**2. HAP Mode (High Assurance Platform):** This is the method that I currently use as it is the safer option. HAP mode is a built in Intel feature which was originally designed for the US government. What it does is that it forces the Intel ME into a sort of "soft-disabled" state shortly after booting up.

**How it Works:**

I enabled the HAP bit via my custom firmware config in Coreboot. This tells the ME to kill its network access, AMT capabilities, and out-of-band management systems while leaving ONLY the bare minimum code running so the machine doesn't get bricked. (Modern systems with Intel CPUs cannot run with no Intel ME at all since it is so heavily baked into the CPU, in fact if you know about Kernel levels it is Kernel Level -3, it literally has more power than the root user on Linux systems).

## How to Verify It

You can check the status of the ME on your system as well. If it is successfully "disabled" or in HAP mode for instance, the PCI device for the MEI, or Management Engine Interface, should be missing entirely or shown as '0'. You can check this with the command:


```lspci | grep -i "communication controller"```

*If this returns nothing or if the MEI device shows up but the driver fails to load in ```dmesg```, HAP mode is still active.*

## The Trade Off

**Not a Full Removal:** The ME firmware is still physically present on the chip no matter what you do. If a nation-state actor has physical access to the SPI flash chip, they could theoretically re-enable it, although for my scenario this is not applicable as I am not gearing this towards nation-state actors but the point still stands. If they can do it a malicious actor could to given enough motivation.

## The Verdict

Personally for my Tier 2 threat model which is ISPs, malicious actors, and physical theft, HAP mode is more than sufficient. It neutralizes the remote out-of-band attack vector while keeping the system as stable as can be.
