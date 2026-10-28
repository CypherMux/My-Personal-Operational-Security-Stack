# Browser Extensions

**Threat Mitigated:** Cross-site tracking, malicious ads or *malvertising*, fingerprinting, and script based exploitation techniques.

## Why This Is So Important

Even when using a privacy focused browser like Mullvad Browser or IceCat for instance the average modern day website is hostile. Websites try to load trackers from dozens of different domains, they try to serve you malicious ads that can compromise your machine, and they even use scripts in order to fingerprint your device.

For my setup I use a strict, minimal set of extensions that act as a secondary "firewall" inside my browser in a sense. I do not install extensions unless they are a widely audited and serve a specific purpose whether that be for security or privacy or anything else that enhances the web experience.

## Implementation (The Extensions I Use)

*  **uBlock Origin**
*  *What it does:* This is considered the gold standard for content blocking in my opinion. It blocks ads, trackers, malicious domains, and other malicious scripts from running at the network level. Because of this it is amazing for the security and privacy of the user.

*  *Why it matters:* Blocking ads is not just about making the site look prettier. Malvertising or malicious ads is a massive attack vector this prevents. uBlock Origin stops the malicious code from ever reaching your browser to begin with.

*  **LibreJS (Specifically for IceCat)**
*  *What it does:* It's main purpose is to block non-free or proprietary JavaScript from running on your browser unless specifically whitelisted by the user.
*  *Why it matters:* As mentioned in the IceCat section prior, this acts as an accidental phishing trap so I know a phishing site immediately when it loads and it acts as a great way to not allow unknown or malicious scripts from running on my machine.

*  **ClearURLs**
*  *What it does:* This extension automatically strips tracking parameters like `utm_source` or `fbclid` for instance from URLs.
*  *Why it matters:* When you click a link you are often broadcasting who sent you that link and what platform you came from. This is extremely important as it cleans the URLs before you even leave the browser and are redirected, giving much more privacy to your experience.

*  **JShelter**
*  *What it does:* This is an anti-malware extension that creates essentially a "JavaScript Shield" around your browser. It intercepts and modifies the APIs that websites use to fingerprint your hardware or track your behavior across the web.
*  *Why it matters:* I use this to prevent websites from reading my exact screen resolution, battery status, or hardware concurrency. It essentially makes you look like thousands of other users similar to Mullvad Browser. I only use this extension on IceCat for that exact reason.

*  **Decentraleyes**
*  *What it does:* This tool manipulates Content Delivery Networks or CDNs locally on your machine.
*  *Why it matters:* This tool is so important because instead of fetching common libraries used such as **jQuery** or **Bootstrap** from Google's servers, it instead serves a local copy straight to you. This benefits the end user as it speeds up loading times for pages and prevents centralized tracking as a whole since you never interact with Google's 3rd party servers to begin with.

*  **Privacy Redirect**
*  *What it does:* This extension automatically redirects popular services such as Youtube, Twitter, Reddit, or Instagram to more privacy friendly alternative front ends such as Invidious, NItter, or Libreddit.
*  *Why it matters:* This tool helps prevent those platforms from setting tracking cookies or logging your IP address when you click a link. Also another huge plus is in my personal opinion the user experience of these alternative front ends are much smoother and user friendly than their counterparts.

*  **Total Privacy and Security (TPRB)**
*  *What it does:* It enhances browser tracking protections and hardens the default privacy settings against known data brokers.
*  *Why it matters:* It matters because it adds an extra layer of filtering for domains that may slip by uBlock Origin's default block list. Think of it almost as a fail safe.

*  **Privacy Badger**
*  *What it does:* Unlike uBlock origin which uses static lists to block domains, Privacy Badger, a tool made by the EFF, uses a method known as *heuristic blocking*. What that essentially means is that it watches domains and automatically blocks any that may appear to be tracking you across multiple sites, even if those trackers aren't on a traditional block list.
*  *Why it matters:* It has the capability of catching zero day trackers and domains that uBlock Origin simply cannot grasp because they have not yet been added to it's filter list yet which makes it extremely valuable as a second line of defense just in case uBlock Origin cannot detect a malicious domain or tracker.

*  **Port Authority**
*  *What it does:* This tool is a highly aggressive port and connection monitoring tool. It logs every single outbound connection your browser attempts to make whether that be a port connection, an IP connection, or a domain connection. It does this in real time and allows you to black list them or allow certain connections depending on your preference for a particular site.
*  *Why it matters:* If a website ever secretly attempts to connect to an obscure port or a known malicious IP, Port Authority will catch it and alert you to the intrusion. It gives you ultimate control and visibility into your browser's network traffic and I like using it as a IDS system for my browser in a sense.

## Some Trade Offs

**Breakage:** With JShelter, LibreJS, and uBlock Origin and many of the other extensions running simultaneously, many modern web apps like banking portals or apps that run heavily on a SaaS model will completely break and be unusable. You will be required to white list these sites or use a separate less restricted browser profile in order to access them.

**Fingerprint Entropy:** Installing too many extensions can make your browser actually *more* unique which is extremely bad for anti-fingerprinting techniques. I try to mitigate this risk by only keeping the list down to just these tools rather than installing every single privacy extension on the Firefox extensions site (addons.mozilla.org) although I still stand out heavily with the extensions I do have which is a hit I just take as I can't avoid it and also keep my extensions at the same time.

## The Verdict

Maximum protection comes with heavy friction no matter what you do. I'm willing to accept the periodically broken site in exchange for knowing exactly what scripts are running on said site and what is tracking me across the web. 
