# Layer 3: Network & Privacy

**Adversary:** Internet Service Providers (ISPs), traffic analysis, DNS snooping, and browser fingerprinting.

The network is the perimeter of our modern digital world. If my traffic leaves my laptop unencrypted, or if my DNS requests are handled by my ISP, I am essentially broadcasting my digital life to corporations and potential eavesdroppers to my network traffic.

This layer is all about **Traffic Obfuscation and Network Sovereignty**. The goal is to ensure my ISP knows as little as possible about what I do online, and that websites I visit can't easily track me across the internet.

## Documentation in this Section

*  **[Mullvad VPN](./vpn.md/)**
*  *Routing all my internet traffic through a privacy first VPN with AI-resistant traffic shaping (DAITA) and double hop routing (MultiHop)*

*  **[Tor Browser](./tor-browser.d/)**
*  *Compartmentalizing high risk or highly private browsing from my clear net activity. (Only if absolutely necessary)*

*  **[GNU IceCat](./icecat-librejs.md/)**
*  *Using a hardened, libre software focused browser for daily clear net browsing to block malicious non-free JS on sketchy sites.*

*  **[Mullvad Browser](./mullvad-browser.md/)**
*  *Using a fingerprint-resistant and privacy focused browser when IceCat is inoperable due to excessive JS usage on a site. Also works extremely well in conjunction with Mullvad VPN*

*  **[Privacy Extensions](./privacy-extensions.md/)**
*  *The specific privacy and security focused extensions I use in my browsers to block trackers and overall harden my browser.*
