# The Faraday Bag (RF Shielding)

**Threat Mitigated:** RF (Radio Frequency) side channel exfiltration, out-of-band wake ups, and unauthorized tracking while the device is powered off.

## The "Why" to my methodology

In the cybersecurity community and communities alike, it is a common misconception and dangerous one at that if my laptop is shut down, it is safe. 

This is unequivocally false. A powered off laptop can still communicate via out-of-band management cycles, like Intel AMT for example. Even if these services are disabled let's say, the hardware can still be theoretically manipulated via RF signals. Furthermore, if malware has previously infected your machine, it can use the devices antennas via Wi-Fi or Bluetooth to exfiltrate data even when the OS is not fully booted up.

## What is it?

A Faraday bag is simply a pouch lined with metallic mesh, usually nickel or copper, that blocks all electromagnetic fields. When a device is inside, it is completely invisible to the outside world, or in other words it creates an air gap between your system and the outside world. It cannot send signals, and it cannot receive them.

## Implementation

**The Gear**: I am currently using a high quality Faraday bag with two layers of shielding for my phone and laptop when I am not using them. They also act as a notification silencer for me while I am in class so I don't get yelled at by the professor lol. The one I currently use is from the company **SLNT** and can be bought at the link here:

**https://slnt.com/**

**The Day to Day Protocol:** Whenever the laptop or my phone is not in use, it goes directly into my Faraday bag. This is to ensure that number one I am not distracted by it and number two so it is properly air gapped when not in use.

## The Verification Test

Don't just trust the bag make sure it actually functions as intended. You should only have to do this one time to make sure it functions as intended:

**1.** Turn on your laptop's and/or your phone's Wi-Fi and leave it on.

**2.** Put the laptop and/or your phone inside the Faraday bag and seal it tightly.

**3.** From another device, try to ping the laptop's IP address or send it a file via Bluetooth. You can also try to call it if it has those capabilities such as a phone does.

**4.** If the bag is working correctly, the laptop or your phone will be completely unreachable.

## Some Trade-offs

Of course there is also trade-offs to using such a piece of hardware. These trade-offs include:

**Heat:** Laptops, phones,or any other device dissipate heat through their chassis. If you put your device into the sealed bag while it is still running you run the risk of cooking your hardware as Faraday bags trap heat like an oven. Always allow your tech to cool off before you place them in the bag to reduce such a risk. I had this happen one time to my laptop and I thought I destroyed it thank god I didn't lol.

**Convenience:** This will also add one extra physical step you need to do when you are packing up to leave to go somewhere, but for a tier two threat model the peace of mind it gives me is enough to be okay with the three second delay it takes to throw it in the bag.
