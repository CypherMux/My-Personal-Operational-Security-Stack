# The Passphrase Strategy

**Threat Mitigated:** Brute force attacks, dictionary attacks, credential stuffing, and memory loss or as I like to call it the "Hit by a bus" risk.

## Why this is so important

The average person uses an 8 character password with a capital letter and a random symbol, such as "Password1!". A modern GPU can crack that password in less than a fraction of a second. This invites huge risk to the user's accounts and overall security online.

To defeat modern day brute forcing, you dont need a *complex* password per se, what you need is **high entropy**. Length is exponentially more important than complexity when it comes to passwords in the modern day. I myself use a tiered password strategy, utilizing fully randomized strings of 32-36 characters for my most critical online accounts.

## Implementation | My Tiered Approach

### Tier 1: The "Master Keys"

These passwords are the only ones I have memorized. They protect the rest of my digital life.

*  **LUKS Disk Encryption:** I use a 32-36 character string for my initial passphrase to decrypt my laptops and other devices storage devices. I type it every time I boot my laptop, my desktop PC, etc so it is pretty much muscle memory at this point.I can type the whole string in under five seconds nowadays.

*  **Offline Bitwarden Vault Master Password:** This unlocks my password vault that provides access to my more complex 48-60 character passwords, again this one is a 32-36 character password. I know having a password that is 48-60 characters completely pointless with today's brute forcing techniques but they protect my most personal accounts so I want to be absolutely sure nobody can get in **no matter what**.

*  **iPhone Passcode:** This password is approx 20-24 characters long, I use a passcode on my phone instead of Face ID or a PIN code as having a complex password provides much higher security than the latter. I also refuse to use biometrics for a plethora of other reasons which are told in the biometrics section.

### Tier 2: The Vault

Every other password such as my banking, Github, forums, or literally anything else is stored in my offline, air gapped bitwarden vault. They are all insanely complex passwords that not even I can remember so I set them in the vault for safe keeping, they are all approx. 48-60 characters in length.

## The Mathematics of Brute Forcing

So why such long, complex passwords you say? If a password is fully randomized meaning it has uppercase letters, lowercase letters, numbers, and symbols, a string such as one that is 36 characters in length yields roughly a keyspace of 82^36 possible combinations, giving it the mathematical equivalent of over **200** bits of entropy.

Even if an attacker had a super computer capable of trying a trillion times per second, it would take longer than the lifespan of the universe in order to crack it. It is genuinely mathematically impossible with current technology to brute force such a password.

### Some Fun Facts About Even LONGER Passwords

For highly sensitive accounts such as the ones in my BitWarden Vault, I often use passwords that are **48-60 characters long**.

Just for fun, here is what the math looks like for the higher tier of my password entourage the **60** character passwords.

*  The key space is approximately **82^60** total combinations.
*  That equates to roughly **380** bits of entropy.
*  There are an estimated **10^80** atoms in the observable universe.
*  A 60 character password has more possible combinations than the **number of atoms in the observable universe**. If every atom in the universe was a super computer trying a billion passwords a second, they would still not crack such a password before the heat death of the universe.

When you have password managers generating the passwords for you, there is zero reason to not use the maximum length you can. 

## How I Memorize Such Complex Passwords

Practice, practice, practice. It's really as easy as that. It is only a matter of **repetition and muscle memory**. Because I type these passwords on the low end at least 5 times a day, my fingers know the pattern even if my brain doesn't recite it. It becomes a physical reflex over time with practice like anything. Even now I can not look at my keyboard at all and put in my encryption passcode flawlessly it's a bit of a skill to be honest lol.

## The Trade Off

*  **The Risk:** Because the master passwords are *only* in my head, if I suffer a head injury or worst comes to worst I pass away suddenly, that data and the accounts holding the data are lost for good and will be permanently encrypted and inaccessible to my family.

*  **The Mitigation:** I maintain a sealed, physical paper copy of the master passwords in a secure offline location. They are never stored digitally, never photographed, and never typed into my computer outside of when they are in use.

## The Verdict

The friction of typing a long password is a small price to pay for absolute and definite cryptographic security. If anybody gets into your account using these strategies, buy a lottery ticket because the odds are heavily, HEAVILY, against that happening. Or don't maybe it's bad luck lol.

