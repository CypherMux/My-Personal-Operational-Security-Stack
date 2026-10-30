# Layer 6: Mobile Security (WIP)

**Adversary:** Cellular triangulation, SIM-swapping, malicious applications, and OS level telemetry.

Mobile devices are fundamentally different from laptops. They are always on, constantly connected to cell towers, and run closed source operating systems(such as **IOS** and **Android**) that are heavily integrated with cloud services.

While my laptop is heavily hardened and locked down, my mobile threat model is currently in the transition phase as of *10/30/26*. I am actively planning a compartmentalized mobile architecture that will separate my real world identity and banking from my digital life as much as I physically am able to.

## The Current Roadmap

I am currently researching and preparing to implement the following strategies into my stack:

*  **GrapheneOS:** Migrating to a de-googled, hardened Android OS on a Google Pixel *(or waiting until Motorola comes out with their collaboration with the team over at GrapheneOS in order to get away from Google entirely.)*. This will provide sandboxed Google Play Services *(If I go the Pixel route.)*, hardened memory allocation, and granular network permissions across all apps.

*  **SIM Isolation:** Moving my primary SIM card to a secondary, locked down device used strictly for banking or other practices which need a standard phone number in order to operate such as SMS 2FA and calls I must take with a regular phone number. This will mitigate the risk of SIM swapping and cellular triangulation on my primary daily device.

*  **Eliminating SMS 2FA:** Migrating all critical accounts from SMS based 2FA to TOTP *(via Proton's authenticator app)* or hardware security keys *(such as YubiKey)*. Some legacy financial institutions still force SMS though which is why isolating my SIM is so important for these services.

  *Documentation for this layer will be updated as soon as I acquire the necessary hardware and complete the implementation into my stack, but for now it will remain a WIP.*


