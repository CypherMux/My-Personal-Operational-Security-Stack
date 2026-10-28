# Tor Browser

**Threat Mitigated:** ISP surveillance, IP address logging, network traffic correlation, and browser fingerprinting.

## Disclaimer

This section is provided strictly for educational purposes and to document my personal privacy/security architecture. I do not condone, support, or participate in the use of the Tor Network for illegal activities, accessing illicit materials, or bypassing legal restrictions for your jurisdiction. The Tor Network is a vital tool for journalists, activists, and privacy conscious individuals worldwide, and it should be used responsibly and within the bounds of the law no matter what.

## Support The Tor Project

The Tor network is maintained by a 501(c)(3) non-profit organization. It is funded by donations from individuals and organizations who believe in a free and open internet.

If you value privacy and anonymity online as much as I do, please consider donating to support the ongoing development of the project including relay infrastructure and advocacy work:

**[Donate to the Tor Project]
https://donate.torproject.org**

With that being said, let us begin.

## Why This Is So Important

While I do use a VPN via Mullvad to hide my traffic as good as I can from my ISP, a VPN still requires me to trust the VPN provider, although I trust Mullvad to keep my IP safe, the risk is still on the table as you are depending on a single entity to protect you on the internet.

The Tor Network (or the Onion Router) solves this by routing my traffic through three random encrypted relays, called the Guard Node, Middle Node, and the Exit Node. No single relay knows both who I am and what websites I am visiting.

I use the Tor Browser specifically for high risk compartmentalization. It is not a daily driver nor do I pretend it is one just because, I only use it when I need absolute anonymity. The main reason I use it personally is in conjunction with my Cryptocurrency wallets on my TailsOS USB which we will get into later in this stack in the *Financial Privacy* section. It is the only tool I trust to truly keep my wallets anonymous and truly untraceable for defending against malicious actors on the blockchain.

## Implementation

**The Browser:** The Official Tor Browser

Here is a link to the download page if you are curious about trying it yourself:

https://torproject.org


