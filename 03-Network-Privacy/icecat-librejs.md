# GNU IceCat

**Threat Mitigation:** Non-free Javascript execution, browser fingerprinting, proprietary tracking scripts, and supply chain attacks via browser code.

## Why Is This So Important?

When you visit a modern website such as Chrome or standard Firefox, you are executing hundreds of pieces of proprietary JavaScript blindly. Most of these scripts are harmless, but a select few are used to aggressively track your activity, fingerprint your device, or even *cryptojack* you in some scenarios.

I use **GNU IceCat**, which is the GNU project's fork of Firefox, with **LibreJS** enabled. IceCat by default strips out all non-free binaries and telemetry. LibreJS takes it even a step further than that, as it blocks **ALL** non-trivial JavaScript unless the script has a free software license embedded inside of it, or unless I explicitly whitelist the code and give it the go ahead to execute.

## Implementation

*   **The Browser:** GNU IceCat

*   **The Extension:** LibreJS (which comes bundled with IceCat by default)

*   **The Philosophy:** "Trust by explicit permission." If a website needs to run proprietary JavaScript to function, much like *GitHub*, I have to manually whitelist that specific domain so it can function.

## The Phishing Trap For Malicious Actors

Although not my intention when downloading this browser, this setup also has an unexpected security benefit that comes along with it, **it breaks phishing sites**.

Phishing sites are usually just cheap clones of the real websites they are trying to imitate to trick you. When an attacker clones GitHub for example, they often use the site's real proprietary JavaScript to make it look as authentic as possible.When I visit a site in the IceCat browser, the JavaScript is automatically blocked because it is not whitelisted. This makes the page look scattered and broken revealing its malicious nature the minute you enter it.

If I were to ever click a link claiming to be GitHub and the layout is obliterated, I instantly know it is a fake site off the get go before I even have the chance to type my password in.

## The Trade Offs

*  **What I like to call "The Bajillion Scripts Conundrum":** Modern web apps like GitHub, YouTube, or banking sites load scripts from multiple CDNs. You will spend a lot of time clicking the LibreJS icon in the toolbar to whitelist the domains before the site works good enough to be usable.

*  **Broken Functionality:** Some websites simply will not work without proprietary JavaScript whether you like it or not. For those specific websites, I switch to the **Mullvad Browser**.

## The Verdict

It is extremely high friction, but for daily clear net browsing, the piece of mind of knowing exactly what code my browser is executing is worth the additional setup time. In fact I am using the browser right now as I write this documentation!
