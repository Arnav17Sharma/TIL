---

---
 --- 
 ## **Introduction**

- **Problem Statement**: The goal is to create a purely peer-to-peer version of electronic cash, enabling online payments to be sent directly from one party to another without needing a financial institution or trusted third party.

- **Purpose**: Introduces a decentralized digital currency system, eliminating the need for intermediaries like banks.

- **Problem Crux**: Double spending in digital currencies, where a single digital token could be spent more than once.

## 

[](https://app.100xdevs.com/courses/13/408/464#5b9ee0ebcaf14f2d888236a488a3600f "Defining Electronic Coins in Bitcoin")**Defining Electronic Coins in Bitcoin**

![notion image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Feb4566ea-3499-40d2-868e-56036b453147%2F4cb423d8-db8c-4e12-995f-c2993ab99466%2Fimage.png?table=block&id=8136969c-ff4b-4b94-94f5-0455f9a987bc&cache=v2)

#### 

[](https://app.100xdevs.com/courses/13/408/464#393006be029d4e56a3dca2b735aa8194 "Concept of an Electronic Coin")**Concept of an Electronic Coin**

- **Definition**: An electronic coin in Bitcoin is defined as a chain of digital signatures. This chain represents the ownership history of the coin, tracking each time it changes hands.

#### 

[](https://app.100xdevs.com/courses/13/408/464#ff19a74ef9c8433db50bf8995dd17408 "How Ownership is Transferred")**How Ownership is Transferred**

- **Transaction Structure**:

- Each time a coin is transferred, the current owner signs a digital hash of the previous transaction.
- The hash includes:

1. **The Previous Transaction**: Proof of how the current owner acquired the coin.

2. **The Public Key of the Next Owner**: Designates the new owner of the coin.

- **Digital Signatures**:

- The current owner uses their private key to create a digital signature, adding it to the end of the coin’s chain and effectively transferring ownership.
- **Hash of the Transaction**: A unique string generated from the transaction data, ensuring even a small change produces a completely different hash.
- **Public Key of the Next Owner**: Serves as the address to which the coin is sent; only the holder of the corresponding private key can access and spend the coin.

#### 

[](https://app.100xdevs.com/courses/13/408/464#918ba7687ad144158c3b59557dd6ce93 "Verification of Ownership")**Verification of Ownership**

- **Verification Process**:

- The payee can verify the transaction’s authenticity by checking the chain of digital signatures.
- This involves:

1. **Verifying the Signatures**: Ensuring each signature in the chain is legitimate by checking against the corresponding public key.

2. **Verifying the Chain of Ownership**: Tracing back the chain of transactions to confirm that the coin’s ownership has been validly transferred.

#### 

[](https://app.100xdevs.com/courses/13/408/464#98369a66829a4dbbacca0b914336fd55 "Chain of Ownership")**Chain of Ownership**

- **Purpose**: The chain of digital signatures serves as a record of ownership, proving that the current owner has legitimately acquired the coin.

- **Security**: Ensures that the ownership of the coin is secure and can be verified without relying on a central authority.

## 

[](https://app.100xdevs.com/courses/13/408/464#a74f098947584f1eaaa753c22b991aa2 "Digital Signatures")**Digital Signatures**

- **Partial Solution**: Digital signatures ensure the authenticity and integrity of a transaction. While crucial for securing transactions, they do not fully solve the double-spending problem.

- **Double-Spending Problem**: Refers to the risk of a single digital token being spent more than once, an issue arising from the ease of copying digital information.

- Transactions are secured with digital signatures.

- Each Bitcoin user has a pair of cryptographic keys: a public key and a private key.

- The private key signs transactions, ensuring only the owner can spend their Bitcoins.

## 

[](https://app.100xdevs.com/courses/13/408/464#fcd59d6283f144adb6e2b7fc167f6c3c "Peer-to-Peer Network and Proof-of-Work (PoW)")**Peer-to-Peer Network and Proof-of-Work (PoW)**

![notion image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Feb4566ea-3499-40d2-868e-56036b453147%2F7d5f1c85-5d40-4a40-9b5b-aa0216190a98%2Fimage.png?table=block&id=be7d24f8-dcba-477f-8ae2-f4e6b4fe3d47&cache=v2)

- **Proposed Solution**: Solving the double-spending problem using a peer-to-peer (P2P) network. The network’s key innovation is the proof-of-work mechanism.

- **Network Operation**: Nodes in the network validate and relay transactions.

- **Timestamps and Hashing**:

- Each transaction is timestamped and hashed into a chain (the blockchain).
- The chain is secured through proof-of-work, where nodes (miners) expend computational power to solve cryptographic puzzles.

![notion image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Feb4566ea-3499-40d2-868e-56036b453147%2F2b4534cf-668b-4d29-992f-4cc18a1dca3d%2Fimage.png?table=block&id=7db1b1ef-2d0d-4fdc-9994-c7c96472c3ac&cache=v2)

- **Immutable Record**:

- The blockchain forms an ongoing, immutable record of transactions.
- Once a block is added to the chain, it cannot be altered without redoing the proof-of-work for that block and all subsequent blocks.

- **Mining Process**: Nodes (miners) solve complex mathematical problems to validate transactions and add them to the blockchain.

- **Rewards**: The first miner to solve the problem gets to add a new block and is rewarded with newly minted Bitcoins.

### 

[](https://app.100xdevs.com/courses/13/408/464#09ae0c01ee1d454cb47f41e6987fa845 "What is Proof-of-Work?")**What is Proof-of-Work?**

- **Concept**: Proof-of-work is a cryptographic mechanism where participants (miners) must perform computational work to solve a problem. In Bitcoin, this problem involves finding a value that, when hashed using a cryptographic hash function like SHA-256, produces a hash with a certain number of leading zero bits.

- **Origin**: The PoW system used in Bitcoin is similar to the one proposed by Adam Back in [Hashcash](https://en.wikipedia.org/wiki/Hashcash), originally designed to combat email spam by requiring senders to perform a small amount of computational work.

### 

[](https://app.100xdevs.com/courses/13/408/464#fe0efbdb0a004072acd066227d31d12e "How Proof-of-Work Works")**How Proof-of-Work Works**

- **Hash Function**: Bitcoin uses the SHA-256 hash function, which takes an input and produces a fixed-size output (the hash). The goal is to find an input (a block of transactions) that produces a hash beginning with a specific number of zero bits.

- **Difficulty**: The number of leading zero bits required in the hash determines the difficulty of the proof-of-work. The more zero bits required, the harder it is to find such a hash. The difficulty is set to maintain a consistent average time to find a solution across the network.

## 

[](https://app.100xdevs.com/courses/13/408/464#b011dd2416eb410fbfb3c01f2e605797 "Longest Chain Rule")**Longest Chain Rule**

- **Chain Validity**:

- The longest chain in the blockchain is considered valid because it represents the most computational work (CPU power) invested.
- This chain serves as proof of the sequence of events (transactions) and indicates that it was generated by the majority of the network’s computing power.

- **Security Assumption**:

- The network's security relies on the assumption that a majority of CPU power is controlled by honest nodes.
- As long as this is true, the honest nodes will always generate the longest chain, outpacing any attackers.

- Once a transaction is confirmed and added to the blockchain, it cannot be altered.

## 

[](https://app.100xdevs.com/courses/13/408/464#bb8e6c20dac84aa2a3af86f4e3a058ff "Network Structure and Operation")**Network Structure and Operation**

- **Minimal Structure**:

- The network is designed to operate with minimal structure.
- Nodes do not need to follow strict protocols or maintain constant connectivity.

- **Broadcasting and Rejoining**:

- Transactions and blocks are broadcasted to the network on a best-effort basis.
- Nodes can leave and rejoin the network at will. When they rejoin, they accept the longest proof-of-work chain as the authoritative record of transactions.

- **Resilience and Flexibility**: This decentralized approach ensures the network’s resilience and flexibility, allowing it to continue operating even if some nodes go offline or the network is under attack.

- **Incentives and Mining**:

- Miners are incentivized to secure the network through block rewards and transaction fees.
- As more miners join, the difficulty of the mathematical problems increases, maintaining a steady block generation rate.

- **Limited Supply**:

- Bitcoin has a fixed supply of 21 million coins, designed to create scarcity and mimic precious metals like gold.
- The block reward halves approximately every four years in an event known as "halving."

- **Decentralized Ledger (Blockchain)**:

- Transactions are grouped into blocks and linked together to form a blockchain.
- The blockchain is a public ledger, visible to all participants in the network.
- Each block contains a list of validated transactions and a reference (hash) to the previous block, ensuring immutability.

- **Security and Attacks**:

- The network is secure as long as honest nodes control more CPU power than any attacking group.
- Discusses the "51% attack" scenario, where a malicious actor with more than 50% of the network's hashing power could potentially alter the blockchain.

## 

[](https://app.100xdevs.com/courses/13/408/464#073758f8bcf24809b139b07b6ff27173 "Applications and Implications")**Applications and Implications**

- **Decentralization**: Bitcoin’s model removes the need for centralized financial institutions.

- **Trust**: Users do not need to trust a third party; trust is placed in cryptography and the network itself.

- **Global Currency**: Bitcoin can be used globally without restrictions, offering an alternative to traditional currencies.

- **Future of Finance**: Paved the way for the development of other cryptocurrencies and the broader decentralized finance (DeFi) ecosystem.

💡

Additional - [The Bitcoin Whitepaper | Fully Explained (With Animations!) (youtube.com)](https://www.youtube.com/watch?v=NoqNhWnjE1Q&t=379s)