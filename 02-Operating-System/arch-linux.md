# Arch Linux

**Threat Mitigated:** Bloatware, hidden telemetry, unnecessary background services, and vendor lock-in.

## Why is this so important?

Most Linux distributions like Ubuntu or Fedora come with hundreds of pre-installed packages, background services, and configurations that you may never use. Every single one of those packages useful or not is a potential attack vector. If a vulnerability is found in a background service you didn't even know was running in the first place, you may be at risk and not even know it.

I chose **Arch Linux** because it adheres the principle of simplicity. Arch does not install anything you do not explicitly tell it to install, and as a result you are required to build the system from the ground up.

This *minimalism by default* approach means:

**1. Reduced Attack Surface:** If I don't need a Bluetooth daemon, a printing service, or a web browser in the background, then why ever install them in the first place? With Arch I have the power to say no to said services and many more never being on my system to begin with.

**2. Absolute Control:** I know exactly what is running on my system at all times as I was the one to put it on there.

**3. No Telemetry:** Arch has zero telemetry,zero data collection, and zero corporate bloatware because it is built that way from the start.

## Implementation

**Rolling Release:** Arch is what is called a *Rolling Release Distribution*. I get the latest security patches and kernel updates within days, or sometimes even hours, of them being released, rather than waiting months for a major OS upgrade.

**The AUR:** The Arch User Repository, or more commonly known as *The AUR* allows me to install niche security tools I use in my schooling and work directly from source, which I can then audit before compiling.

## The Trade Off of Arch

**Maintenance:** Arch requires attention. You have to read the Arch news before doing a system upgrade via ```sudo pacman -Syu``` occasionally to make sure a package update does not brick your system or if it may require manual intervention on your part.

**The Breaking Phase:** Because you have root access to everything, it is incredibly easy to break your system if you type the wrong command with root privileges.For example my first time setting up Arch I messed up the partition tables and only had 64GB of space on my system out of the 4TB I had on my SSD(oops). You are a bound to make mistakes your first time setting it up as it is an extremely advanced Linux distro and requires prior Linux knowledge to set up properly your first time. Consider it a learning experience it will make you better in the long run.
