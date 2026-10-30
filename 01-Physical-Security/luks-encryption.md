# LUKS Full Disk Encryption

**Threat Mitigated:** Data theft from a stolen, lost, or seized laptop.

## Why Do I Do This?

If my laptop is stolen out of my bag at a coffee shop for example, I want 100% confidence that the thief cannot access my files, crypto wallets, or my Bitwarden vault.

Even if a thief were to remove the NVMe SSD and insert it into another machine, they will always hit a cryptographic wall which I put in place to ensure they can get to nothing. LUKS, or Linux Unified Key Setup, encrypts the entire block device, rendering the data indistinguishable from random noise without correctly guessing the passphrase to decrypt it.

## Implementation Details

**Encryption:** LUKS2

**Cipher Utilized:** AES-256-XTS (this is the current industry standard for full disk encryption although this may change as quantum computers become more prevalent).

**Passphrase:** A good complex password is essential to be able to properly secure your system. I recommend one at least 24 characters or more personally as anything after that and with enough complexity is infeasible to crack in a conceivable amount of time.

## Why Such A Long Password?

Why do we need to use such a complex and long password? Because brute-forcing attacks become harder and harder the more complex and long your password becomes, and eventually becomes infeasible to use to crack your password the longer it becomes. For example a 36 character random string is mathematically impossible with current technology to brute-force. Even with a super computer, it would take longer than the lifespan of the universe to crack such a string.

**Why memorize it instead of storing it?**

If the passphrase is written on a sticky note on the laptop, the encryption you put in place is entirely useless. By memorizing your passphrase, the key lives only in your head the only place it should be in the first place. It takes about 3-4 seconds to type in at boot which is completely negligible when you compare it to the absolute digital sovereignty you will incur.

## How to Verify It

You can verify your encryption details by running the following command on your system:

```sudo cryptsetup luksDump /dev/nvme0n1p2```

*Look for ```Cipher: aes-xts-plain64``` and ```Key: 512 bits``` in the output.*

## The Trade Offs

**The "Hit By a Bus" Dilemma:** Because the password is only in my head, there is a risk of permanent data loss if I suffer a head injury or forget it as a whole, I've already been working towards steps to mitigate this but it is always on the table.

## The Verdict

The 3 second friction of typing a long password to successfully decrypt my hardware is a small price to pay for absolute data sovereignty.


