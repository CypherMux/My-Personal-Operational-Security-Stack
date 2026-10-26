# Mullvad Browser

**Threat Mitigated:** Browser fingerprinting, canvas tracking, and cross site correlation.

## Why This Is So Important

Using a VPN hides your IP address, but it does *not* stop websites from tracking your data via your browser's fingerprint. Things such as your screen resolution, fonts, time zone, user agent, and hardware concurrency combine to create an unique profile of your device, or what is also known as its **fingerprint**.

The **Mullvad Browser**, which is a joint project between the people at Mullvad VPN and the Tor Project, is designed to fix these issues. It takes the privacy hardened engine of the Tor Browser and strips out the Tor network's routing capabilities. This allows you to use it with your regular VPN and also makes the browsing experience much faster, although it is a tad bit less private than Tor.

## Implementation

**Anti-Fingerprinting:** The browser intentionally makes all users look identical. It spoofs your screen resolution, blocks canvas readouts, and standardizes fonts.

**Zero Telemetry:** There is no analytics, no crash reports, and no pings home. It just works.

**Isolation:** I use Mullvad Browseer specifically for general clear net browsing where I want anti-fingerprinting but do not want the latency of the Tor network. I will also use it on occasion to replace IceCat for some heavily restrictive sites when it comes to LibreJS.

## Why Use This AND IceCat?

You may ask, "Why use both Mullvad Browser and IceCat?" Well each one has its one purpose pertaining to how I am browsing of course:

*  **IceCat:** This is for when I want absolute control over what scripts are running on the websites I visit, such as GitHub for example.

*  **Mullvad Browser:** This is for when I want to blend into the crowd and/or IceCat is being funky with the way it is displaying a certain site. When I use Mullvad Browser I do not want to be uniquely identifiable nor do I want to spend time whitelisting scripts, I simply just want to look like a generic user.

## How To Test The Browser's Fingerprinting Resistance

You can test the browser's fingerprint resistance by visiting the **EFF's** Cover Your Tracks Tool or checking the Tor Project's fingerprinting site at the links below:

**EFF's Official Tool:** https://coveryourtracks.eff.org/

**A General Guide to Fingerprinting Protections By Tor (these are also applicable here as this browser is a fork of tor):**  https://support.torproject.org/tor-browser/features/fingerprinting-protections/

If you are using Mullvad with the default settings, your fingerprint should appear identical to thousands of other users when you try the test.

## The Trade Off

*  **Friction With Logging Into Sites:** Because the browser aggressively clears cookies and site data to prevent tracking, you may have to log in to sites more frequently then you may be used to.

*  **Performance:** Anti-fingerprinting and strict blocking can slightly slow down some web apps you come across.

## The Verdict

This browser is the closest you can get to Tor's anonymity without actually using the Tor Browser itself. It also perfectly complements a Mullvad VPN geared setup which I adore. Overall it is an amazing choice for a privacy focused browser.
