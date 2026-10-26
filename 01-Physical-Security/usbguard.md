# USBGuard

**Threat mitigated:** BadUSB attacks, malicious hardware injection, and unauthorized data exfiltration.

## Why is this so important?

By default, Linux/Windows/MacOS all trust any USB device you plug into your machine. A malicious actor with just 5 seconds or less of physical access to an unlocked or locked device can plug in a device disguised as a mini keyboard or more widely known as a BadUSB. The device instantly can type a script to open a terminal, download malware, and execute it at superhuman speeds. This is known as a **BadUSB** attack.

USBGuard solves this by implementing a kernel level authorization framework. The software intercepts any and all USB devices before their drivers even load. If the device's vendor ID, product ID, and serial number are not explicitly in the allow list set by the USBGuard config file, the kernel blocks it from interacting with the system as a hard coded safety measure.

## Implementation

**Policy:** Default of the software is to deny all connections,everything is blocked unless allowed via your config file tied to USBGuard which is only allowed to be accessed by a root user stopping any need be intruders from getting in if your root user is locked down enough.

**The Allow List:** I generated an allow list that is a base line rule set in which the software goes by while activated. It explicitly ONLY only allows my built-in keyboard, touchpad, my mouse, and my hardware security key to access the machine.

**Permissions:** The rules file, which is stored in ```/etc/usbguard/rules.conf``` by default is strictly locked down with the permission ID of 600, meaning it is only read/write to the root user. This is again as explained prior to prevent tampering if an intruder does know where the file to change access resides and is another blockade for them to pass.

## Disclaimer

If you install USBGuard without generating a baseline rule set first, it will block **ALL** devices including your mouse and keyboard, leaving you locked out of your machine at the login screen. 

**The Recovery Procedure:**

If this does happen to you, you can follow the steps below to fix it:

**1.** Boot a live USB OS, like Arch or Ubuntu for example.

**2.** Mount the root partition in the set up.

**3.** Edit ```/etc/usbguard/rules.conf``` and add a broad HID, or Human Interface Device rule. This is the broad category in which your keyboard or mouse reside in. An example of this would be:

`allow with-interface one-of
{ 03:00:01 03:01:01 03:00:02 03:01:02 }' <--- These are the IDs for such devices.

**4.** Reboot back into your system and the mouse and keyboard should now be operational again.

## Daily Usage

When I need to plug in a new USB device, like a Tails live USB or an external SSD for example, it is silently blocked by default. To authorize it temporarily for my current session I will use the command:

```sudo usbguard allow-device <device_id>```

This will enable me to use the device for the rest of my current session until I shut off the machine. If you need to plug in a device temporarily as well you can use the same method listed above.

*To permanently authorize a trusted device, you can also append the -p flag to the command.*

## The Trade Offs

**Friction:** If a friend were to hand me a USB drive to transfer a file over to my system, it won't work automatically. I have to first open a terminal, find the device ID, and authorize the drive. This is no hassle for me since I don't regularly take unknown USBs and plug them into my system but if you do this may be on the table.

## The Verdict

The 10 second friction of authorizing a new device is infinitely better than having the risk of a malicious actor plugging a BadUSB into my system and injecting a payload that may cause permanent damage. The compromises I'm willing to take are completely fine for the off chance that that may happen although very rare.
