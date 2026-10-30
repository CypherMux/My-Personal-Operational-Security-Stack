Layer 1: Physical Security
--------------------------

The main adversary for this layer is thieves, malicious actors with brief physical access, and visual eavesdroppers, or what I like to call shoulder surfers.

In cybersecurity we tend to focus almost entirely on remote network attacks. However if an adversary has physical access to your hardware, almost all your software defenses can be bypassed and mean nothing. This layer is about making sure that even if my laptop is stolen, lost, or even briefly handled by someone else, my personal data remains secure.

This layer operates on the principle of **Hardware Sovereignty**. It stands for trusting nothing by default and securing the physical endpoint to the best of your ability.

## Documentation in this Section

*  **[Intel ME (HAP Mode)](./intel-me-hap.md/)**
*  *How I neutralized the Intel Management Engine to prevent out of band firmware exploitation on my end.*

*  **[LUKS Full Disk Encryption](./luks-encryption.md/)**
*  *Data at rest protection using a secure and complex master passphrase.*

*  **[USBGuard](./usbguard.md/)**
*  *Kernel level defense against BadUSB and malicious hardware injection.*

*  **[Faraday Bag](./faraday-bag.md/)**
*  *RF shielding to ensure the machine is truly air-gapped when powered off.*

*  **[Privacy Screen](./privacy-screen.md/)**
*  *Defeating visual eavesdropping and shoulder surfing in public spaces.*

*  **[Hardware Selection](./hardware-selection.md/)**
*  *The reason I chose open source firmware and hardware from a reputable, privacy focused company.*
