# Btrfs Snapshots & System Recovery

**Threat mitigated:** Ransomware, catastrophic system failures that would otherwise be permanent, bad updates, and accidental user error.

## The Why Behind This

In cybersecurity, we tend to talk a lot about preventing attackers from getting in especially on the SOC side of things, but what happens if they *do* get in? Or what happens if a kernel update completely breaks the graphics drivers on the system or something adjacent?

If your system is compromised by ransomware or a bad update, you need to have a way to instantly roll back to a known, good save of the system just in case.

I use **Btrfs** for this exact purpose. It is a modern "copy-to-write" filesystem which is combined with a tool called **Snapper**. This allows me to take instant, zero cost snapshots of my entire system before I make any major changes so If the update does break the system I have a backup.

## Implementation

**Filesystem:** Btrfs with a root and home sub volume. This is to mitigate risk by separating the higher tiered user (root) from the standard users. This is also known as **Principle of Least Privilege** and is extremely prevalent when it comes to cybersecurity on the job and out of it.

**The Strategy:** I do my best to always take a snapshot of my system before every major update I commit to and I also put snapshots on a daily timer just in case something breaks while I am on my system and not currently committing to an update.

**Boot Integration:** My bootloader (GRUB) is configured to read the Btrfs snapshots. If I were to break my system, I can literally boot directly from the previous snapshot I had taken via the GRUB boot menu.

## Why this is an amazing tool in my arsenal

If an adversary were to somehow gain root access to my system and start deleting files left and right or install a rootkit, I have no need to panic. I can just reboot into an earlier snapshot where they never had access to begin with and call it a day. It also gives me the freedom to experiment with my system and break things without fear of a bricked system.

## How to Verify you have Btrfs

To see the list of your current Btrfs subvolumes you can use the command:

```sudo btrfs subvolume list /```

and to manually take a snapshot of your root directory you can use the command:

```sudo btrfs subvolume```
```snapshot / / .snapshots/manual_backup```

Do the first command and then the second right after and you are all set!

## The Trade Offs

**Snapshots are *NOT* Backups:** A snapshot lives on the same physical drive as your personal data. If the SSD in which you are using physically dies or becomes corrupted, both your data and the snapshots are gone. Snapshots are more to protect against *logical* errors such as ransomware and bad updates and do not protect against total hardware failure. (This is part of the reason I personally want to implement an air-gapped NAS into my setup in the future to mitigate such a possibility.)

**Disk Space:** If you don't configure Snapper to automatically delete old snapshots that are no longer of use to you, they will slowly consume your hard drive/SSD. It is always good practice to give backups a TTL. Personally I have mine set to a 7 day window but whatever works best for you is applicable to this as well.
