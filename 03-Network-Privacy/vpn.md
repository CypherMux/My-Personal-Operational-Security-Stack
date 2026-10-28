# Mullvad VPN

**Threat Mitigated:** ISP traffic analysis, IP logging, and advanced AI driven website fingerprinting.

## Why is this so important?

A VPN is one of the first lines of defense when it comes to hiding your activity from your ISP. Without it, your ISP has the ability to log every website you visit, every server you connect to, and how you stay on each service while on the internet. This is a huge attack vector as you are putting your trust in your ISP to not sell said data to a data broker or make sure your data is safe and encrypted.

I chose **Mullvad** for this exact reason. I gave my ISPs control over my data to Mullvad as they have a long track record of doing the right thing with your data when it comes to being a VPN company. They have a strict no logs policy, anonymous account generation with no email requirement, and they have a strong commitment to pushing the boundaries of network privacy. However sometimes just the VPN is not enough. The way packets are sized and timed can still allow an adversary to guess what you are doing based off packet size. In the implementation section I will explain the ways we can prevent such things using Mullvad's settings.

## The Implementation

*  **DAITA (Defense Against AI Guided Traffic Analysis)**
*  *What it is:* DAITA intentionally modifies your network traffic by injecting something known as *"dummy packets"* into the mix which normalizes the packet sizes across all your data. This makes every piece of data you transfer over your network look indistinguishable from the others.
*  *Why it matters:* AI can analyze the size and timing of encrypted packets to guess what websites you are visiting even if your traffic is encrypted. DAITA breaks that analysis and makes it as hard as it can for the AI to decipher what you are doing online by making the traffic appear as random noise.

*  **Multihop Routing**
*  *What it is:* Instead of routing through one VPN server Mullvad routes your traffic through two servers, called a entry server and an exit server.
*  *Why it matters:* Using this setting in your VPN settings makes it so no individual server knows both your IP address and your final destination. In turn it makes traffic correlation attacks significantly harder to pull off.

*  **DNS Blocking**
*  *What is it:* Mullvad's DNS servers resolve your queries and will actively block known malware, trackers, and ad domains before they even have the chance to leave the VPN tunnel.
*  *Why it matters:* Without this, your device will send a DNS request to your ISP to ask what the IP address is for a particular site lets say for instance Github.com. The ISP will log this info. But by using Mullvad's internal DNS blockers the ISP now can only see an encrypted VPN tunnel and nothing more. The DNS request is resolved securely inside the tunnel and known malicious domains are dropped long before your browser ever connects to them increasing your security on the web massively.

## The Reality Of No Logs

Mullvad doesn't ask for an email nor does it have a subscription service model which could potentially link back to you based off your payment method. If you were to pay with a cryptocurrency such as **Monero**, nobody not even law enforcement can get anything even with a warrant as you have no paper trail and no logs on your activity, all they have is an account number and nothing more.

*Disclaimer: I am not advocating for illegal or criminal activities regarding this section, I am simply illustrating just how secure and private Mullvad VPN can become if you use it the right way.*

## Some Trade Offs

*  **Speed:** Running DAITA and Multihop together will slow down your connection a fair bit. This is an unavoidable reality as adding dummy packets and multiple encryption layers to your traffic will tend to do such a thing. Also make sure to not use DAITA while using your phone's mobile data as it will eat through your data usage on limited plans, even though it is more secure with it on if you want a much lighter phone bill I would recommend turning it off while only on data.

*  **Battery Life:** Constantly encrypting and routing traffic takes a bunch of CPU power and in turn will drain your laptop's battery a lot faster than you are used to, for example I lose about an hour and a half of battery life when I turn on my VPN with all its settings enabled. Just be wary of that fact for the future.

## The Verdict

I personally accept a latency and battery hit for my situation. Ensuring that my ISP sees nothing but encrypted noise is worth the performance cost for my particular threat model.

## Get Mullvad VPN Yourself

In an industry full of "no log" VPNs that are secretly owned by data brokers themselves or require an email or credit card, Mullvad stands out as a genuine privacy advocate among the rest.

*  **No Emails:** You get a random 16 digit account number and you never provide any personal info while creating your account.

*  **Audited:** They regularly hire third party security firms like **Cure53** for example to audit their apps and overall infrastructure.

*  **Ownership:** They have never taken venture capital money in their companies lifetime, meaning they do not have investors pushing them to monetize user data including yours.

  If you would like to try it out yourself you can try it out by clicking the link below. I heavily recommend them as they are the only VPN provider I wholeheartedly trust will protect my data.

  https://mullvad.net/en
