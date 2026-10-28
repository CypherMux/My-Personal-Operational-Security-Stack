# The BitWarden Setup

**Threat Mitigated:** Cloud provider data breaches, vendor lock-in, API vulnerabilities, and unauthorized cloud syncing.

## Why this is so important

Most people will use **1Password**,**LastPass**, or the official **BitWarden Cloud**. While these ways of storing your passwords are mighty convenient, they rely on a **Trusted Third Party** model to function. You are trusting that the company's servers won't be breached, that their encryption is flawless, and that their APIs won't be exploited.

I personally do not trust third parties with something so private such as the keys to my identity.

Instead, I took the time to self host my password manager using **VaultWarden**, which is a lightweight, unofficial BitWarden server written in Rust. This server I have is running on a machine that is fully air gapped and offline at all times. It does not have an internet connection and being so my vault is completely isolated from the outside world.

## Implementation

*  **The Server:** VaultWarden running locally.

*  **The Master Password:** A 32-36 character string which is fully randomized and extremely complex that unlocks the vault.

*  **Encryption:** Zero-Knowledge Architecture. Even if someone were to steal the physical hard drive which is running the server, the vault data is encrypted with AES-256. Without my complex master password, the data they will acquire is useless.

## How It Works In Practice

Because the server is offline, I can only sync my vault when I am in my house and connected to my local network. If I am traveling and need a password, I can rely on the local encrypted cache on my laptop which I can read as far away from my vault as can be.

This does remove the convenience of instantly syncing everywhere yes but it also removes the risk of breaches to the companies cloud which I appreciate much more than that singular downside.

## The Trade Offs

*  **No Automatic Cloud Sync:** Again as stated prior, if I manually enter a password on my laptop I have to double check if it properly synced to my other devices as well, leading to some friction.

*  **Maintenance:** I am solely responsible for backing up the VaultWarden database. I do this currently through encrypted Btrfs snapshots but eventually I want to transition to a setup with an offline NAS.

## The Verdict

Cloud breaches are one of the most common ways people lose their entire digital lives to criminals on the internet. By air gapping my vault, I ensure that the only way an attacker gets my passwords is if they physically break into my house and somehow brute force my 32-36 character master password which I deem pretty unlikely.
