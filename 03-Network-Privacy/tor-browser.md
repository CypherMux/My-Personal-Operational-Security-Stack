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

*  **The Browser:** The Official Tor Browser

Here is a link to the download page if you are curious about trying it yourself:

https://torproject.org

*  **The Network:** With Tor I often use a bridge in conjunction with it such as **obs4** or **snowflake**,especially if I am on a network which heavily restricts or outright bans access to the Tor Network. What a bridge does is make your traffic look like random noise like a video call for instance to slip by these network wide Tor filters. If you would like to know more about bridges and how they work/function, you can click the link below that I have provided from the official Tor documentation:

  https://support.torproject.org/tor-browser/circumvention/using-bridges/

*  **Security Level:** The majority of the time I will run the browser on the safest level as it offers the most protection overall, but if anything breaks on a site I may go down a level or two just so it can function accordingly. The safest setting for Tor does block JavaScript by default so this can happen occasionally.

## Operational Security Rules

Using Tor correctly is imperative to make your browsing experience on it is truly *private*. These are the rules I follow to make sure my browsing experience stays as private as can be:

*  **Never log in to personal accounts:** If you were to log into a personal email or social media account on Tor, it will instantly de-anonymize you for the rest of the session you are in and link your identity straight back to your activity. Always make sure that the browsing you do does not link back to you whatsoever.

*   **Never Maximize The Browser Window:** This is a much less known vulnerability with Tor and Tor will warn you about it from time to time. Maximizing the browser window leaks your exact screen resolution, which is a massive way that fingerprinting can occur for the session you are currently in.

*   **No Extra Extensions:** Tor is intended to be used with close to no extensions minus the few the developers throw in there for extra anonymity. Tor Browser is carefully tuned in this way to make everyone look identical which means adding additional extensions will do nothing but ruin your anonymity while browsing.

## Some Trade Offs

*  **Speed:** Because your traffic is going across three different encrypted relays across the world, the Tor network is and will ever be slower than any standard web browser.

*  **Captchas:** Because so many bots and malicious actors use the Tor Browser for illicit activities, companies like Google or Cloudflare will often bombard you with captchas or straight up just not allow you into a site to begin with.

## The Verdict

Tor is not for convenience in the slightest, it is for maximum anonymity and only maximum anonymity. When I need it, I am willing to accept the friction and latency that come with it for that exact reason.




