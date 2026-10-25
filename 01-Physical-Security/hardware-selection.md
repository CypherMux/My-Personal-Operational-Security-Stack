# Hardware Selection

**Threat Mitigated:** Closed-Source firmware backdoors, Intel ME exploitation, and vendor lock-in.

## The "Why" Behind This

You can install all the firewalls and encryption software in the world, but if the hardware beneath it is compromised, none of your troubles mattered in the first place. Most consumer laptops such as Dell, HP, Lenovo, and Apple ship with closed-source UEFI/BIOS firmware and proprietary microcontrollers in which you cannot audit.

I specifically chose a custom laptop built by **NovaCustom** because it allowed me to solve these problems at the hardware level. If you would like to support the amazing people at the company you can also buy a laptop, phone, mini pc, etc yourself they make a ton of privacy focused tech. You can support them and buy your own NovaCustom tech at this link:

https://novacustom.com/

The problems this allowed me to solve are the following:

**1. Coreboot:** NovaCustom ships their tech with Coreboot, which is an open-source bootloader. This means the booting process is transparent and auditable by anyone, including myself which I love.

**2. Intel ME Neutralization:** I will get into this further in the intel-me-hap.md section but this laptop enabled me to build it myself with Intel ME neutered at the firmware level, eliminating or at the least mitigating the out-of-band backdoor entirely on my end.

**3. Linux First Engineering:** The laptop I bought from them is designed to run Linux natively, which means no proprietary driver hell(looking at you **Nvidia**).

## Implementation Details

**Firmware:** Coreboot

**Hardware Kill Switches:** Instead of having kill switches I entirely removed the camera and microphone from my laptop on request, although this is not necessary for your situation if you do need them I just wanted to close as many attack vectors as I could including microphone and camera hijacking.

**Storage:** I put a 4tb NVMe SSD in my system to allow for extensive local virtual machines and AI agents to be used at my disposal. I got the biggest, most cost effective, drive I could get to future proof my hardware.

## Trade-offs

**Cost:** Custom Linux hardware is almost always more expensive than buying a mass market consumer laptop from another brand. You are paying for the engineering and care put into the building of the laptop though as each laptop is made from order. 

**Performance:** You are trading top tier gaming performance for security and a longer battery life, although if you do want to game I would just recommend using a desktop PC so I see this as a plus at the end of the day.

**My Overall Verdict:** For me personally as I am going into the cybersecurity field, hardware sovereignty is a non-negotiable and the premium you have to pay, especially that hefty VAT fee since they are located in the Netherlands, is 100% worth it.
