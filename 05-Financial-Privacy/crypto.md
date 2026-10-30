# Cryptographic Assets & Privacy Using *Monero*

**Threat Mitigated:** Blockchain analysis, transaction graph tracing, address linking to real identity, and network level surveillance.

## Why This Is So Important Especially

Bitcoin is often mistaken for an anonymous and fully private cryptocurrency, but it is actually a *psuedonymous* transparent ledger. Every transaction ever made on the Bitcoin ledger ever made is made public. If your wallet address is ever linked to your real identity, like for example through a KYC crypto exchange, anyone can trace your entire financial history backward and forward using a method called *chain analysis heuristics*. 

Firms such as Chainalysis use algorithms to analyze the public ledger. A common example of this is the *Common-Input-Ownership* heuristic. This is where if a transaction has multiple inputs, the algorithm will automatically assume that they all belong to the same wallet. By clustering these addresses together, they can build a massive graph of the wallet's spending habits, the wallet's associates, and the wallet's net worth, and in the worst case scenario, back to your real identity.

For true financial privacy, I personally use **Monero(XMR)**. Unlike Bitcoin, Monero is *private by default*. It uses advanced cryptography to obscure the sender, the receiver, and the amount of every transaction, while still allowing the network to verify the transaction is valid.

## Implementation *(The Underlying Technology)*

Monero achieves its privacy through four core technological innovations *(As of 10/30/26 the day I am writing this documentation)*:

### 1. Stealth Addresses *(Hiding the Receiver)*

On Bitcoin's blockchain, you can send funds to a static address, for example *bc1q...*. On Monero's blockchain you do the same thing as you also are able to send your funds to a static address, although you never receive your funds there.

*  **The Math:** When someone sends you XMR, their wallet generates a random secret number, multiplies it by your public view key using *ECDH(Elliptic Curve Diffie-Hellman)*, and then combines it with your public spend key.

*  **The Result Of This:** This will generate a unique, one time public address for just that specific transaction. The sender will send the funds there, and only you can derive the private key from that transaction to spend the sent cryptocurrency. This makes address reuse impossible and also prevents outside observers from linking multiple transactions to the same recipient.

### 2. Ring Signatures *(Hiding The Sender)*

When you spend Monero, you don't just sign a transaction with your key. You create a "ring" of possible signers to further obfuscate your identity.

*  **The Math:**  The protocol pulls 16 decoy outputs from the blockchain to get this obfuscation done. This means your real output will be mixed up with 15 other decoys, making your transaction much more private.

*  **The Result:** A cryptographic ring signature is created, proving that one of the 16 keys did indeed sign the transaction, but it is mathematically impossible to tell which one did from an outside observer.

### 2.1 The Future of Ring Signatures *FCMP++(Full Chain Membership Proofs)*

While the current ring size of 16 provides extremely strong privacy, it is still a bounded anonymity set. Statistical analysis overtime can potentially narrow down the real output to just you. To solve this problem permanently, the Monero developers are currently working to deploy something known as **FCMP++**.

*  **The Shift:** FCMP++ replaces fixed size ring signatures entirely. Instead of proving you own 1 out of 16 outputs, you generate a *zero knowledge proof* that your output exists somewhere within the **entire set of all historical Monero outputs**(which currently as of 10/30/26 is well over 150 million).

*  **The Impact:** The anonymity set jumps from 16 all the way to the entire blockchain. An outside observer cannot even begin to guess which output is the real one because every single transaction in the blockchain's history is a potential decoy.

*  **Status of Development:** As of late 2026,FCMP++ is in an active beta stressnet testing phase alongside the CARROT address upgrade. A mainnet hard fork is targeted for the near future once testing and audits are officially completed and successful.

### 3. RingCT *(Hiding The Amount)*

Historically, ring signatures hid the sender yes, but the amount was still visible. **RingCT(Ring Confidential Transactions)** was introduced to solve this exact conundrum and hide the amount.

*  **The Math:** It uses a strategy to do this called **Pedersen Commitments**, which allow a user to commit to a value(the amount) without revealing it to any outside observers, while still allowing the network to verify that the inputs sum to the outputs, enabling the transaction to be verifiable still.

*  **Bulletproofs:** To prevent the transaction from bloating due to this obfuscation, Monero uses Bulletproofs(a type of zero knowledge proofs) to prove that the hidden amounts are valid without revealing the actual numbers for the transaction.

### 4. Dandelion++ *(Hiding The Source IP)*

Most cryptocurrencies use a *gossip protocol* where nodes will broadcast transactions to all other peers. This makes it trivial for an adversary to trace the transaction back to the originating IP address in turn. Monero stops such a practice by using a protocol called **Dandelion++**.

*  **The Math:** Dandelion++ changes the propagation of such info. The transaction enters the "stem" phase, where it is passed in a straight line from node to node with a small probability of "fluffing"(broadcasting the transaction to the wider network) on each consecutive hop.

*  **The Result:** By the time the transaction reaches the public mempool the "fluff phase" occurs, meaning the original IP address for the transaction has been completely obscured through multiple hops. It is extremely similar to how the Tor Network functions except instead of giving you browsing privacy this function enables the user to receive financial privacy.

## The Concept of Fungibility

Fungibility means that one unit of a specified currency is indistinguishable another *(1XMR=1XMR for example)*. Because Bitcoin is a transparent blockchain, if a specific Bitcoin was used in a hack 5 years ago for example an exchange may blacklist that Bitcoin, making Bitcoin fundamentally not a fungible currency which is one of the most important aspects of a currency as a whole. 

Because Monero is private, every XMR in turn is completely identical and has no traceable history. This makes it the only true *digital cash* as of present day.

## The Trade Off

*  **Size:** Because of the complex cryptography such as **RingCT** for example, Monero transactions are significantly larger than Bitcoin Transactions, which makes the blockchain in turn much larger and heavier to sync.

## The Verdict

For my specified threat model, cryptographically sound privacy is absolutely worth the trouble to maintain such as the additional storage requirements I need to store my wallet.
