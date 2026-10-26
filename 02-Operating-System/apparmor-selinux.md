# Mandatory Access Control (MAC)

**Threat Mitigated:** Zero day application exploits, malicious code execution, and unauthorized file access.

## Why is this so important anyways?

Traditional Linux security relies on a system called **Discretionary Access Control (DAC)**. If you run a program as your main user account, that program has access to all your files. If you open a PDF in a vulnerable PDF reader for example and an attacker exploits said vulnerability, they immediately inherit your user privileges, which could potentially be root privileges if worst comes to worst. They can read your SSH keys, your documents, and other sensitive you wouldn't want prying eyes to see.

**Mandatory Access Control (MAC)** solves this by confining applications to their own sandboxes. Even if an attacker compromises a program, MAC prevents that program from accessing files or making network connections outside of its designated profile. In a sense, each program is separated by a giant wall.

## Implementation

In the Linux ecosystem, the two main MAC frameworks are **AppArmor**, which is used by default in Ubuntu, Debian, and SUSE distributions, and **SELinux**, used by default in RHEL/Fedora distributions.

For my setup personally, I have configured **AppArmor** to run in *enforce* mode.

*  **Profiles:** I use the standard distribution profiles for all the common apps on my hardware.

*  **Enforce vs. Complain:** Many people using AppArmor leave it in *complain* mode meaning it only logs violations but doesn't block them. I made sure to at the very least run it in the strict *enforce* mode. This means that if a program attempts to access a file it shouldn't, the kernel will instantly shoot down and kill the request.

## How to Verify it

To see the status of AppArmor and list all the loaded profiles currently protecting your system, you can use the command:

```sudo aa-status```

This will tell you the number of profiles loaded in *enforce* mode and the number loaded in *complain* mode. A properly hardened setup should have zero complaint profiles. If you ever want to check if a specific program has a profile as well, you can always use the command:

```sudo aa-status | grep <app-name>```

## The Trade Off

* **The "False Positive" Phase:** When you first enforce a new AppArmor profile, the application might break because it was secretly accessing a file it shouldn't have to begin with, an example of this would be a text editor trying to read your network config which is something it would never need to do. Make sure to spend the time checking your ```dmesg``` and ```journalctl``` logs to see what was blocked and tweak the profile accordingly to your liking.

## The Verdict

Once the profiles on your system are dialed in and set to the correct settings, it is completely invisible during daily use. But if a zero day were to ever hit a browser or other application which you use, AppArmor will be the wall that stops the attacker from stealing your sensitive info. Think of it as putting each app on an island and putting a mile high wall between each one of those islands. With that kind of defense, no apps can talk to each other whatsoever.


**Here is the link to the official AppArmor documentation if you are interested in trying it yourself:**
https://www.apparmor.net/
