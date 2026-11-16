# Unit III – Blockchain Platforms and Consensus in Blockchain

**Subject:** Blockchain Technology (410243)  
**Programme:** Fourth Year Computer Engineering (2019 Pattern), SPPU  
**Unit:** III – Blockchain Platforms and Consensus in Blockchain

> **Answer-writing note:** These answers are prepared in simple technical English for SPPU end-semester writing. Diagrams are kept compact and reproducible. Mathematical notation is written in plain text.

---

## Q1. Explain consensus in blockchain and discuss different consensus algorithms. [7 Marks]

### 1. Meaning of Consensus in Blockchain

- Consensus is the process by which the participating nodes in a blockchain network agree on the validity and order of transactions.
- Since a blockchain is decentralized, there is no central authority to approve every transaction.
- A consensus mechanism ensures that all honest nodes maintain a consistent copy of the distributed ledger.
- It helps prevent invalid transactions, double-spending and unauthorized changes to blockchain records.

### 2. Need for Consensus

1. **Agreement:** Ensures that network participants agree on the current state of the blockchain.
2. **Security:** Makes it difficult for malicious users to add invalid blocks.
3. **Decentralization:** Allows the network to operate without a central authority.
4. **Double-spending prevention:** Helps prevent the same digital asset from being spent more than once.
5. **Data consistency:** Maintains a common and reliable transaction history across participating nodes.

### 3. General Working of Consensus

1. A user initiates a transaction.
2. The transaction is broadcast to the blockchain network.
3. Participating nodes verify the transaction according to protocol rules.
4. A consensus mechanism is used to select or approve the next block.
5. The valid block is added to the blockchain.
6. The updated ledger is shared with the network.

**Diagram:**

```text
       User Initiates Transaction
                  |
                  v
       Transaction Broadcast
                  |
                  v
        Verification by Nodes
                  |
                  v
       Consensus Mechanism
                  |
                  v
          Block Approved
                  |
                  v
       Block Added to Blockchain
                  |
                  v
        Ledger Updated in Nodes
```

### 4. Elements of a Consensus Mechanism

- **Agreement:** Nodes reach a common decision about valid transactions.
- **Validity:** Only transactions satisfying the blockchain rules are accepted.
- **Fault tolerance:** The network continues to operate even if some nodes fail or behave maliciously.
- **Participation:** Defines which nodes can take part in the consensus process.
- **Incentives:** Some mechanisms reward participants for contributing to network security.

### 5. Different Consensus Algorithms

#### A. Proof of Work (PoW)

- Proof of Work is a consensus mechanism in which miners compete to solve a computational puzzle.
- Miners repeatedly calculate cryptographic hashes by changing a nonce.
- The miner who finds a hash satisfying the network difficulty target can propose the next block.
- Other nodes verify the block before accepting it.
- It requires significant computational power and electricity.

**Example:** Bitcoin.

#### B. Proof of Stake (PoS)

- Proof of Stake selects validators based on the cryptocurrency they lock or stake in the network.
- Validators are responsible for proposing and validating blocks.
- Honest validators may receive rewards, while dishonest behaviour can lead to penalties or loss of stake.
- It generally consumes less energy than Proof of Work.

**Example:** Ethereum.

#### C. Proof of Elapsed Time (PoET)

- Proof of Elapsed Time is designed to select a block creator using a randomly assigned waiting time.
- Each participating node receives a wait time.
- The node whose waiting time expires first gets the opportunity to create the next block, subject to protocol checks.
- It is commonly associated with trusted execution environments that help ensure the waiting-time process is fair.

**Example:** Hyperledger Sawtooth (historically supported PoET).

#### D. Proof of Activity

- Proof of Activity is a hybrid consensus approach combining Proof of Work and Proof of Stake.
- Miners first perform a Proof of Work process to create a block candidate.
- Stakeholders or validators then participate in approving or signing the block.
- The combination aims to use computational work and stakeholder participation for network security.
- Its exact operation depends on the protocol implementation.

#### E. Proof of Burn

- In Proof of Burn, participants permanently destroy or “burn” a certain amount of cryptocurrency by sending it to an unspendable address.
- The burn acts as evidence of commitment to the network.
- The protocol uses this commitment to determine participation or block-creation rights.
- It avoids the continuous energy-intensive computation used by Proof of Work, although the burned coins are permanently lost.

### 6. Comparison of Consensus Algorithms

| Algorithm | Basic principle | Main resource / basis | Example or use |
|---|---|---|---|
| Proof of Work | Solve a cryptographic puzzle | Computing power | Bitcoin |
| Proof of Stake | Validators lock cryptocurrency | Staked assets | Ethereum |
| Proof of Elapsed Time | Random waiting-time selection | Trusted execution / wait time | Hyperledger Sawtooth |
| Proof of Activity | Combines PoW and PoS stages | Computing power and stake | Hybrid approach |
| Proof of Burn | Permanently destroy coins | Burned cryptocurrency | Protocol-dependent |

### Conclusion

Consensus is essential for maintaining agreement, security and trust in a decentralized blockchain. Different algorithms such as PoW, PoS, PoET, Proof of Activity and Proof of Burn use different methods to validate transactions and add blocks.

---

## Q2. Explain the Byzantine Generals Problem, its scenario, significance and consequences in blockchain consensus.

### 1. Introduction

- The Byzantine Generals Problem is a classical problem in distributed computing.
- It explains how multiple participants can reach a common decision when some participants may fail or send false or conflicting information.
- In a blockchain network, nodes must agree on the validity and order of transactions even when some nodes are faulty or malicious.
- The problem is therefore important for understanding fault-tolerant consensus mechanisms.

### 2. Scenario of the Byzantine Generals Problem

Imagine several Byzantine army generals surrounding a city. They must decide whether to **Attack** or **Retreat**.

- The generals communicate with each other through messengers.
- They must reach a common decision.
- Some generals may be traitors.
- A traitor may send one message to some generals and a different message to others.
- If honest generals make different decisions, the army may fail.

**Diagram:**

```text
                 General A
                /         \
          Attack             Retreat
             /                 \
       General B             General C
          |                     |
       Honest                Traitor
```

The diagram illustrates how conflicting messages from a dishonest participant can create disagreement.

### 3. Significance in Blockchain

1. **Decentralized agreement:** Blockchain nodes must agree without depending on a central authority.
2. **Malicious nodes:** Some participants may deliberately send false information or attempt to disrupt consensus.
3. **Transaction consistency:** Honest nodes should maintain a consistent view of accepted transactions.
4. **Double-spending prevention:** Consensus must prevent conflicting spends from being accepted as valid.
5. **Network reliability:** The system should continue functioning even when a limited number of nodes behave incorrectly.

### 4. Consequences if the Problem Is Not Handled

- **Conflicting transaction records:** Different nodes may accept different transaction histories.
- **Double spending:** A user may attempt to spend the same digital asset in conflicting transactions.
- **Blockchain forks:** The network may temporarily or persistently split into competing histories.
- **Invalid block acceptance:** Malicious participants may try to introduce invalid data.
- **Loss of trust:** Users may lose confidence in the correctness of the ledger.
- **Network disruption:** Consensus may become delayed or fail.

### 5. How Blockchain Consensus Addresses the Problem

- **Proof of Work (PoW):** Requires computational work to propose blocks and makes rewriting confirmed history costly.
- **Proof of Stake (PoS):** Uses validators who lock stake; protocol rules can penalize dishonest behaviour.
- **Practical Byzantine Fault Tolerance (PBFT):** Uses message exchanges among known replicas to reach agreement despite a limited number of Byzantine faults. In the classical model, a system with 3f + 1 replicas can tolerate up to f Byzantine faulty replicas, subject to the protocol assumptions.

### Conclusion

The Byzantine Generals Problem demonstrates the difficulty of achieving agreement in a distributed network containing dishonest participants. Blockchain consensus mechanisms address this challenge by helping honest nodes agree on a valid transaction history and maintain network security.

---

## Q3. Explain different types of blockchain: Public, Private and Consortium, with advantages and disadvantages. [4 Marks]

Blockchain networks are commonly classified according to who can access the network and participate in transaction validation.

### 1. Public Blockchain

- A public blockchain is an open and decentralized network.
- Anyone can join the network, read permitted ledger data and participate according to its protocol.
- It generally does not require prior permission to participate.
- Transactions are validated using a consensus mechanism.

**Examples:** Bitcoin and Ethereum public networks.

**Advantages:**
- High degree of decentralization.
- Transparent and independently verifiable transactions.
- Open participation.
- No single organization controls the network.

**Disadvantages:**
- Public transaction data may create privacy concerns.
- Some consensus mechanisms can consume significant energy.
- Performance and transaction throughput may be limited.

### 2. Private Blockchain

- A private blockchain is controlled by a single organization.
- Only authorized users or nodes can join and perform permitted operations.
- The organization manages access rights and network rules.
- It is commonly used for internal business processes.

**Example:** A private Hyperledger Fabric network operated by one organization.

**Advantages:**
- Controlled access and improved data privacy.
- Generally higher transaction throughput.
- Easier administration and governance.
- Suitable for confidential business information.

**Disadvantages:**
- More centralized than a public blockchain.
- Trust is placed in the controlling organization.
- Restricted participation.

### 3. Consortium Blockchain

- A consortium blockchain is governed by a group of selected organizations rather than one organization or the general public.
- Only approved members can participate in the network.
- Multiple organizations share responsibility for maintaining the ledger and validating transactions.
- It is useful when several organizations need to collaborate.

**Example:** A permissioned blockchain network shared by a group of banks.

**Advantages:**
- Shared control among participating organizations.
- Better privacy than a fully public network.
- More efficient decision-making than many open networks.
- Useful for inter-organizational collaboration.

**Disadvantages:**
- Governance can become complex.
- Requires agreement among consortium members.
- Less open and decentralized than a public blockchain.

### 4. Comparison

| Parameter | Public Blockchain | Private Blockchain | Consortium Blockchain |
|---|---|---|---|
| Control | Decentralized | Single organization | Group of organizations |
| Access | Open | Restricted | Restricted to approved members |
| Participation | Anyone | Authorized users | Selected organizations / users |
| Transparency | Generally high | Controlled | Shared among members |
| Performance | Depends on protocol; often lower throughput | Generally high | Generally high |
| Example | Bitcoin, Ethereum | Private Hyperledger Fabric network | Multi-bank permissioned network |

### Conclusion

Public blockchains provide open participation, private blockchains provide organization-controlled access, and consortium blockchains allow multiple organizations to share control of a distributed ledger.

---

## Q4. Explain Bitcoin, Ethereum and Hyperledger as blockchain platforms. [4 Marks]

### 1. Bitcoin

- Bitcoin is the first decentralized cryptocurrency, introduced under the name Satoshi Nakamoto in 2008; its network began operating in 2009.
- It uses a public and permissionless blockchain.
- It uses the Proof of Work (PoW) consensus mechanism.
- Its primary purpose is to enable peer-to-peer digital payments without a central authority.
- Bitcoin transactions are recorded in a distributed public ledger.

**Example:** Transferring bitcoins from one user to another without involving a bank.

### 2. Ethereum

- Ethereum is an open-source, decentralized blockchain platform proposed by Vitalik Buterin and launched in 2015.
- It supports cryptocurrency transactions, smart contracts and decentralized applications (DApps).
- It uses the native cryptocurrency called Ether (ETH).
- Smart contracts can be written in programming languages such as Solidity.
- Ethereum currently uses the Proof of Stake (PoS) consensus mechanism.

**Example:** Developing decentralized applications, automated payment systems and DeFi applications.

### 3. Hyperledger

- Hyperledger is an open-source collaborative project hosted by the Linux Foundation.
- It provides enterprise blockchain frameworks for developing private and permissioned blockchain networks.
- It is mainly used by businesses and organizations to securely share information and perform transactions.
- Hyperledger Fabric is one of its popular frameworks.
- It supports permission-based access, modular architecture and smart contracts (called chaincode in Hyperledger Fabric).
- Hyperledger frameworks do not require a native cryptocurrency.

**Example:** Supply chain management, banking transactions and healthcare record management.

### 4. Comparison

| Parameter | Bitcoin | Ethereum | Hyperledger |
|---|---|---|---|
| Main purpose | Digital currency | Smart contracts and DApps | Enterprise solutions |
| Network type | Public | Public | Usually permissioned |
| Access | Permissionless | Permissionless | Permissioned |
| Consensus | Proof of Work | Proof of Stake | Depends on framework and configuration |
| Cryptocurrency | Bitcoin (BTC) | Ether (ETH) | No native cryptocurrency required |
| Example | Digital payments | DeFi applications | Supply chain management |

### Conclusion

Bitcoin is mainly used for decentralized digital payments, Ethereum provides a platform for smart contracts and decentralized applications, while Hyperledger is designed for enterprise-level permissioned blockchain solutions.

---

## Q5. Explain Corda and R3 blockchain platforms, including features and CorDapps. [4 Marks]

### 1. R3

- R3 is an enterprise blockchain software company that developed the Corda distributed ledger platform.
- It focuses on providing secure and efficient distributed ledger solutions for businesses and financial institutions.
- R3's technology is designed to support business transactions between organizations while maintaining privacy and security.
- It is used in areas such as banking, insurance and trade finance.

### 2. Corda

- Corda is an open-source distributed ledger platform developed by R3 for business applications.
- It allows organizations to conduct transactions directly and securely without sharing all transaction details with the entire network.
- Unlike traditional public blockchains, Corda shares transaction information only with the parties that need it.
- It uses smart-contract logic to define and verify business agreements.

**Features of Corda:**

1. **Privacy:** Transaction data is shared only with the parties involved and other required participants.
2. **Permissioned network:** Participants are identified and authorized.
3. **Smart contracts:** Business rules are implemented and verified through contract code.
4. **Point-to-point communication:** Transactions are shared with relevant participants rather than broadcast to every network participant.
5. **Notary service:** Helps prevent double-spending by checking transaction uniqueness.
6. **Interoperability:** Supports business transactions between different organizations.

### 3. CorDapps (Corda Distributed Applications)

- CorDapps are applications developed on the Corda platform to automate business processes and transactions.
- They use Corda components such as states, contracts and flows.
- **States:** Represent shared facts or data about a business transaction.
- **Contracts:** Define rules that transactions must follow.
- **Flows:** Manage communication and the sequence of steps between participants.

**Example:** In a loan agreement, a CorDapp can manage the loan application, verify the agreement between the bank and customer, and record the transaction on the Corda network.

### 4. Architecture of a CorDapp

```text
                 CorDapp
                    |
       +------------+------------+
       |            |            |
       v            v            v
     States      Contracts     Flows
       |            |            |
 Transaction    Business      Transaction
    data          rules        process
       |            |            |
       +------------+------------+
                    |
                    v
               Corda Network
```

### Conclusion

R3 developed Corda as an enterprise-focused distributed ledger platform. CorDapps run on Corda and help organizations automate secure, private and reliable business transactions.

---

## Q6. Differentiate between Bitcoin and Ethereum. [4 Marks]

Bitcoin and Ethereum are two popular blockchain platforms, but they differ in their purpose, functionality and applications.

### Difference between Bitcoin and Ethereum

| Parameter | Bitcoin | Ethereum |
|---|---|---|
| 1. Introduction | Introduced by Satoshi Nakamoto in 2009. | Proposed by Vitalik Buterin in 2013 and launched in 2015. |
| 2. Main purpose | Designed mainly for peer-to-peer digital payments and as a store of value. | Designed to support smart contracts and decentralized applications. |
| 3. Cryptocurrency | Uses Bitcoin (BTC). | Uses Ether (ETH). |
| 4. Blockchain function | Primarily records financial transactions. | Records transactions and executes smart contracts. |
| 5. Smart contracts | Has a limited scripting language and programmability. | Supports general-purpose programmable smart contracts. |
| 6. Consensus mechanism | Uses Proof of Work (PoW). | Uses Proof of Stake (PoS). |
| 7. Block timing | Average block interval is approximately 10 minutes. | Slots occur approximately every 12 seconds. |
| 8. Applications | Digital payments and store of value. | DeFi, NFTs, DApps and automated agreements. |

### Conclusion

Bitcoin is mainly used as a decentralized digital currency, whereas Ethereum is a programmable blockchain platform that supports digital currency, smart contracts and decentralized applications.

---

## Q7. Explain IOTA and its role in the Internet of Things. [4 Marks]

### 1. Introduction to IOTA

- IOTA is a distributed ledger technology designed specifically for the Internet of Things (IoT).
- It enables connected devices to exchange data and make transactions without requiring a central authority.
- Unlike traditional blockchain platforms, the original IOTA design used a data structure called **Tangle**, based on a Directed Acyclic Graph (DAG).
- It was designed to support lightweight, scalable and feeless machine-to-machine transactions.

### 2. Tangle Technology

- Tangle is a Directed Acyclic Graph (DAG) rather than a traditional chain of blocks.
- In the original Tangle design, a new transaction approved two previous transactions.
- Transactions could be processed in parallel rather than being grouped into sequential blocks.
- This design aimed to support scalability and efficient data exchange between connected devices.

**Simplified Tangle diagram:**

```text
       T1 ------> T3
        \          \
         v          v
          T2 -----> T4
            \      /
             v    v
               T5
```

*The arrows represent directed approval / reference relationships. This is a simplified conceptual diagram.*

### 3. Role of IOTA in the Internet of Things

1. **Machine-to-machine communication:** Enables IoT devices to exchange information and communicate directly.
2. **Microtransactions:** Designed to support small-value payments between connected devices.
3. **Data integrity:** Distributed ledger techniques help maintain the integrity and authenticity of exchanged data.
4. **Scalability:** The DAG-based design supports parallel transaction processing.
5. **Energy efficiency:** Designed for IoT environments with limited computing resources.
6. **Automation:** Enables automated transactions between devices without continuous human involvement.

### 4. Applications of IOTA in IoT

- **Smart cities:** Connected sensors can exchange traffic and environmental data.
- **Smart vehicles:** Vehicles can make automated payments for charging and parking.
- **Supply chain:** Tracks goods and verifies product information during transportation.
- **Smart energy:** Supports data exchange and automated interactions between energy devices.

### Conclusion

IOTA was designed to use Tangle technology for IoT applications. Its original architecture supports data exchange, machine-to-machine communication and scalable transactions between connected devices.

**Technical note:** This answer describes the original Tangle architecture commonly taught in introductory syllabus material. The IOTA network has evolved, so this description should not be treated as a complete description of the current network implementation.

---

## Q8. Differentiate between Permissioned and Permissionless Consensus Approaches. [4 Marks]

Consensus is the process through which blockchain network participants agree on the validity and order of transactions. Based on participation and access control, consensus approaches can be classified as permissioned and permissionless.

### Difference between Permissioned and Permissionless Consensus

| Parameter | Permissioned Consensus | Permissionless Consensus |
|---|---|---|
| 1. Meaning | Only authorized participants can participate in the consensus process. | Anyone can participate in the consensus process without prior approval. |
| 2. Access | Requires permission or identity verification. | Open to everyone. |
| 3. Identity | Participants are generally known and verified. | Participants may be anonymous or pseudonymous. |
| 4. Speed | Often faster due to a limited and identified set of participants. | Performance depends on the protocol; open participation can add overhead. |
| 5. Scalability | Often provides higher transaction throughput in enterprise settings. | Throughput varies by design and may be limited by open-network consensus requirements. |
| 6. Security | Uses authorized participants and access-control mechanisms, along with consensus rules. | Uses cryptographic techniques and consensus mechanisms to resist malicious activity. |
| 7. Examples | Hyperledger Fabric and permissioned Corda networks. | Bitcoin and Ethereum mainnet. |
| 8. Applications | Banking, healthcare and enterprise data sharing. | Cryptocurrencies and public decentralized applications. |

### Examples of Consensus Algorithms

**Permissioned networks:**
- Practical Byzantine Fault Tolerance (PBFT)
- Raft
- Proof of Authority (PoA)

**Permissionless networks:**
- Proof of Work (PoW)
- Proof of Stake (PoS)

### Conclusion

Permissioned consensus provides controlled participation and often higher performance for enterprise applications, whereas permissionless consensus allows open participation and supports decentralization in public blockchain networks.

---

## Q9. Explain Bitcoin mining and elaborate the functionality of miners. [8 Marks]

### 1. Introduction to Bitcoin Mining

- Bitcoin mining is the process of validating Bitcoin transactions and adding new blocks to the Bitcoin blockchain.
- It is based on the **Proof of Work (PoW)** consensus mechanism.
- Mining is performed by specialized computers called miners, which compete to find a valid block hash.
- The miner who successfully finds a valid solution can broadcast the candidate block to the network.
- If the block is accepted, the miner receives the block subsidy along with the transaction fees included in the block.
- Mining helps secure the Bitcoin network and makes rewriting confirmed transaction history computationally expensive.

### 2. Working of Bitcoin Mining

Bitcoin mining follows these steps:

1. **Transaction collection:** Miners select unconfirmed transactions from the Bitcoin network.
2. **Block formation:** Selected transactions are grouped together to form a candidate block.
3. **Block header creation:** The miner prepares the block header containing information such as the previous block hash, Merkle root, timestamp, difficulty target and nonce.
4. **Hash calculation:** Miners repeatedly calculate the double SHA-256 hash of the block header.
5. **Nonce modification:** Miners change the nonce and calculate the hash repeatedly until they find a hash that meets the network's difficulty target.
6. **Block broadcasting:** The successful miner broadcasts the candidate block to the network.
7. **Block verification:** Other nodes independently verify the block and its transactions according to Bitcoin rules.
8. **Block addition and reward:** If valid, the block can be added to the blockchain. The miner receives the applicable block subsidy and transaction fees if the block is accepted into the active chain.

### 3. Diagram of Bitcoin Mining Process

```text
       Unconfirmed Transactions
                  |
                  v
        Candidate Block Creation
                  |
                  v
       Nonce + SHA-256 Hashing
                  |
                  v
       Is Hash Within Target?
             /          \
           No            Yes
           |              |
           v              v
      Change Nonce    Broadcast Block
           |              |
           +-- Repeat     v
                    Network Verification
                            |
                            v
                    Block Added to Chain
                            |
                            v
                     Miner Gets Reward
```

### 4. Functionality of Bitcoin Miners

1. **Transaction verification:** Check digital signatures, transaction inputs and outputs, and ensure that transactions follow Bitcoin protocol rules.
2. **Block creation:** Collect valid transactions and organize them into candidate blocks.
3. **Solving Proof of Work:** Perform repeated hash calculations to find a block hash that satisfies the network difficulty target.
4. **Preventing double-spending:** Help maintain a consistent transaction history by validating transactions and contributing to the blockchain's agreed history.
5. **Block broadcasting:** Broadcast successfully mined candidate blocks to other nodes for verification.
6. **Maintaining network security:** Make it computationally expensive for attackers to alter confirmed blockchain history.
7. **Earning rewards:** Receive the block subsidy and transaction fees when their block is accepted into the active chain.

### 5. Important Terms Used in Bitcoin Mining

| Term | Explanation |
|---|---|
| **Nonce** | A number that miners change repeatedly to generate different block hashes. |
| **SHA-256** | Cryptographic hash algorithm used in Bitcoin's Proof of Work. Bitcoin applies it twice to the block header. |
| **Hash** | Fixed-length output generated from the block header. |
| **Difficulty target** | A numerical threshold that the block hash must meet; the hash interpreted as a number must be less than or equal to the target. |
| **Block subsidy** | Newly created bitcoins assigned to the miner of an accepted block. |
| **Transaction fees** | Fees attached to transactions and collected by the miner of the accepted block. |
| **Mining difficulty** | A network parameter that adjusts to regulate how difficult it is to find a valid block. |

**Example:** If a miner generates a hash that does not satisfy the difficulty target, the miner changes the nonce and calculates another hash. This process continues until a valid hash is found.

### 6. Advantages of Bitcoin Mining

- Maintains decentralization by allowing miners across the network to participate.
- Provides security through computational work.
- Helps prevent double-spending.
- Helps validate transactions and maintain the blockchain.
- Rewards miners for contributing computational resources.

### Conclusion

Bitcoin mining is an essential process that uses the Proof of Work mechanism to validate transactions, create new blocks and secure the blockchain. Miners verify transactions, solve cryptographic puzzles and maintain the decentralized Bitcoin network while earning rewards.

---

## Unit III – Quick Revision

| Topic | Key points to remember |
|---|---|
| Consensus | Agreement among nodes on valid transactions and blockchain state. |
| Proof of Work | Miners, nonce, hash puzzle, difficulty target; Bitcoin. |
| Proof of Stake | Validators, locked stake, rewards and penalties; Ethereum. |
| PoET | Random waiting time and trusted execution environment. |
| Proof of Activity | Hybrid approach combining PoW and PoS. |
| Proof of Burn | Permanently destroys coins as evidence of commitment. |
| Byzantine Generals Problem | Honest participants must agree despite traitors or conflicting messages. |
| Public blockchain | Open participation; Bitcoin and Ethereum. |
| Private blockchain | One organization controls access. |
| Consortium blockchain | Multiple selected organizations share governance. |
| Bitcoin | Digital payments; PoW; BTC. |
| Ethereum | Smart contracts and DApps; PoS; ETH. |
| Hyperledger | Enterprise blockchain frameworks; permissioned networks; no native cryptocurrency required. |
| Corda | R3-developed enterprise distributed ledger; privacy and point-to-point data sharing. |
| CorDapps | Corda applications built using States, Contracts and Flows. |
| IOTA | Original architecture uses Tangle, a DAG, designed for IoT. |
| Permissioned consensus | Authorized participants. |
| Permissionless consensus | Open participation. |
| Bitcoin mining | Transaction selection, candidate block, double SHA-256, nonce, target, verification and reward. |

## Important Diagrams to Practise

1. General blockchain consensus workflow.
2. Byzantine Generals Problem scenario.
3. CorDapp architecture – States, Contracts and Flows.
4. Simplified IOTA Tangle (DAG).
5. Bitcoin mining flowchart.

## Answer Accuracy Notes

- Bitcoin's network launched in 2009; the white paper was published in 2008.
- Ethereum uses Proof of Stake on its current mainnet.
- Hyperledger is a project / ecosystem of enterprise blockchain frameworks, not one single blockchain.
- Corda is a distributed ledger platform developed by R3; R3 is the company.
- IOTA's Tangle description above refers to its original architecture, not necessarily every detail of the current network.
- Consensus algorithms and performance depend on the specific protocol implementation. Avoid presenting general speed comparisons as universal guarantees.
