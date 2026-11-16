# Unit V – Ethereum, Smart Contracts and Development Environment

**Course:** SPPU Fourth Year Computer Engineering (2019 Pattern)  
**Subject:** Blockchain Technology (410243) | **CO:** CO4

> Answers use simple technical English, plain-text formulas and compact diagrams suitable for examination reproduction. Marks and PYQ metadata are shown as supplied.

## Q1. What is Ethereum? Explain its features, architecture and components.

### Introduction
Ethereum is an open-source, decentralized blockchain platform for developing and executing smart contracts and decentralized applications (DApps). It was proposed by Vitalik Buterin in 2013 and launched in July 2015. Ether (ETH) is its native cryptocurrency.

### Features
1. **Decentralization:** Operates through distributed nodes rather than a central server.
2. **Smart contracts:** Executes programs when predefined conditions are met.
3. **Ether:** Native asset used for value transfer and transaction fees.
4. **EVM:** Provides a common environment for smart contract execution.
5. **Transparency:** Public transactions and contract interactions can be inspected.
6. **Security:** Uses cryptography, distributed validation and consensus.
7. **DApps:** Supports decentralized applications in finance, gaming, identity and other areas.
8. **Programmability:** Developers can create tokens and application logic using Solidity and other compatible languages.

### Architecture
~~~
+--------------------------------------+
| Application Layer: DApps, wallets    |
+--------------------------------------+
| Smart Contract Layer: contract logic |
+--------------------------------------+
| Execution Layer: EVM                 |
+--------------------------------------+
| Consensus Layer: PoS, validators     |
+--------------------------------------+
| Data/Network: blocks, transactions   |
+--------------------------------------+
~~~
- **Application:** User-facing interfaces for blockchain applications.
- **Smart contract:** Programs deployed on Ethereum.
- **Execution:** Processes transactions and executes contract instructions through the EVM.
- **Consensus:** Coordinates validators to agree on the canonical chain.
- **Data/network:** Handles blocks, transactions and node communication.

### Components
1. **Ether (ETH):** Ethereum's native cryptocurrency.
2. **EVM:** Executes smart contract bytecode.
3. **Smart contracts:** Programs stored and executed on the blockchain.
4. **Externally Owned Accounts (EOAs):** User-controlled accounts operated through private keys.
5. **Contract accounts:** Accounts controlled by deployed contract code.
6. **Gas:** Measures computational effort and is used to calculate transaction fees.
7. **Nodes:** Computers participating in the network and maintaining blockchain data.
8. **Validators:** Stake ETH and propose or attest to blocks under Proof of Stake.

### Consensus and Applications
Ethereum currently uses **Proof of Stake (PoS)**. It transitioned from Proof of Work in September 2022. Applications include DeFi, NFTs, supply-chain tracking, decentralized identity and blockchain games.

**Conclusion:** Ethereum is a programmable blockchain platform whose EVM, smart contracts, Ether, gas and PoS consensus support decentralized applications.

**PYQ:** Frequency **7/7**; supplied metadata **6, 8, 9**.  
**Exam focus:** Definition, features, architecture diagram, components and current PoS mechanism.

---

## Q2. Explain smart contracts with examples, purpose and types.

### Introduction
A **smart contract** is a self-executing program deployed on a blockchain. It contains predefined rules and executes when specified conditions are satisfied. On Ethereum, contracts are commonly written in Solidity, compiled into EVM bytecode and deployed through a blockchain transaction.

### Working
1. Developer writes contract code.
2. Compiler converts it into EVM bytecode.
3. Bytecode is deployed on the blockchain.
4. A user or another contract interacts with it.
5. EVM executes the programmed instructions.
6. Successful execution records the resulting state changes.

~~~
Write contract → Compile → Deploy
       → User interaction → Execute
       → Update blockchain state
~~~

### Purpose
1. **Automation:** Performs operations when conditions are met.
2. **Transparency:** Code and transactions can be inspected on public networks.
3. **Reduced intermediaries:** Reduces dependence on third parties for programmed operations.
4. **Accuracy:** Executes predefined rules consistently.
5. **Efficiency:** Can reduce manual processing and administrative overhead.
6. **Trust:** Participants can rely on agreed code and blockchain execution.

### Types (functional classification)
1. **Smart Legal Contracts:** Represent obligations or agreements in code. Example: release payment after delivery confirmation.
2. **Decentralized Autonomous Organizations (DAOs):** Use smart contracts to manage rules, proposals and voting. Example: token-holder voting.
3. **Application Logic Contracts (ALCs):** Implement the business logic of DApps. Example: a decentralized exchange contract processing token swaps.

These are functional categories, not three programming languages or mandatory technical standards.

### Examples, advantages and limitations
Examples include escrow, decentralized exchange swaps, voting, NFT ownership and supply-chain event records.

**Advantages:** Automation, transparency, traceability, reduced manual intervention and consistent execution.  
**Limitations:** Coding errors can cause loss; deployed code may be difficult to change; external real-world data may require oracles; execution consumes gas.

**Conclusion:** Smart contracts automate predefined rules on blockchains and support decentralized applications in finance, governance, supply chain and digital assets.

**PYQ:** Frequency **7/7**; supplied metadata **4, 6, 8, 9**.  
**Exam focus:** Definition, working diagram, purpose, functional types and examples.

---

## Q3. Explain Swarm as a decentralized storage platform and its role in the Ethereum ecosystem.

### Introduction
**Swarm** is a decentralized peer-to-peer storage and content-distribution platform designed for the Ethereum ecosystem. It distributes data across participating nodes instead of depending on one central storage server. Ethereum executes smart contracts and maintains blockchain state; Swarm is intended for storage and distribution of larger content.

### Features
1. Decentralized storage across participating nodes.
2. Peer-to-peer data exchange.
3. Content addressing to identify stored content.
4. Data distribution and redundancy mechanisms that can improve availability.
5. Reduced dependence on a single hosting provider.
6. Integration with decentralized applications.
7. BZZ token used for economic incentives and payments in the Swarm ecosystem.

### Working
1. User uploads a file.
2. File is divided into smaller chunks.
3. Chunks are content-addressed and distributed among nodes.
4. Nodes store and serve the relevant chunks.
5. A user requests the content.
6. Network retrieves and reassembles the chunks.

~~~
Upload file → Split into chunks
     → Address and distribute
     → Distributed Swarm nodes
     → Retrieve chunks
     → Reconstruct file
~~~

### Role in Ethereum
- **Off-chain storage:** Stores large files unsuitable for direct contract storage.
- **DApp support:** Provides decentralized content storage.
- **Decentralized websites:** Can host website content without one central server.
- **Content availability:** Distribution can help serve content through participating nodes.
- **Censorship resistance:** Reduces dependence on one hosting provider.
- **Integration:** DApps and contracts can refer to Swarm content addresses.

### Advantages and limitations
**Advantages:** P2P architecture, content addressing, support for large content and reduced central-storage dependence.  
**Limitations:** Availability depends on node participation and incentives; retrieval performance can vary; Swarm does not replace Ethereum's smart contract execution layer.

**Conclusion:** Swarm complements Ethereum by providing decentralized storage and content distribution while Ethereum handles transactions, contracts and blockchain state.

**PYQ:** Frequency **6/7**; supplied metadata **4, 6, 9**.  
**Exam focus:** Definition, features, chunking/retrieval workflow, BZZ and role alongside Ethereum.

---

## Q4. Explain Whisper as a decentralized messaging platform and its purpose in Ethereum.

### Introduction
**Whisper** is a decentralized peer-to-peer messaging protocol originally designed for communication between Ethereum nodes and DApps. It was intended to support messaging without recording every message permanently on the blockchain. Whisper is a historical protocol design, not the core messaging service of today's Ethereum network; later work in this area is associated with Waku.

### Features
1. Decentralized peer-to-peer communication.
2. Encrypted message support.
3. Topic-based filtering to identify relevant messages.
4. Off-chain messaging rather than permanent blockchain transactions.
5. DApp communication support.
6. Asynchronous message exchange, subject to protocol behaviour and message availability.

### Working
1. Sender creates a message.
2. Message is encrypted.
3. Topic or filter is associated with it.
4. Message propagates through the P2P network.
5. Interested recipients filter and receive it.
6. Intended recipient decrypts and reads it.

~~~
Create message → Encrypt → Add topic/filter
     → P2P propagation → Recipient filters
     → Decrypt and read
~~~

### Purpose
- Communication between DApp participants.
- Encrypted notifications and messages.
- Off-chain communication without recording every message as a blockchain transaction.
- Avoids using blockchain execution for every application message.
- Supports decentralized messaging and user interaction.

### Advantages and limitations
**Advantages:** Decentralized design, encryption support, topic filtering and off-chain messaging.  
**Limitations:** Historical protocol; delivery and availability are not equivalent to permanent blockchain transaction finality; P2P propagation may have availability and performance limitations.

**Conclusion:** Whisper was designed to provide encrypted, topic-based, off-chain communication for Ethereum applications.

**PYQ:** Frequency **5/7**; supplied metadata **6, 9**.  
**Exam focus:** Definition, features, working diagram, purpose and distinction between off-chain messages and on-chain transactions.

---

## Q5. Explain different types of Ethereum networks, including Mainnet, Testnet and Private Networks.

### Introduction
Ethereum provides different network environments for deploying and operating smart contracts. Mainnet, Testnets and Private Networks serve different purposes during development, testing and production.

### Mainnet
- Primary public Ethereum blockchain used for production applications.
- ETH has real economic value.
- Public users can connect and interact with applications.
- Uses Ethereum's Proof of Stake consensus.
- Used for production contracts, token transfers, DeFi and NFTs.

### Testnet
- Separate public blockchain environment for testing applications and protocol changes.
- Test ETH is intended to have no real monetary value and is generally obtained through faucets.
- Helps developers find errors before Mainnet deployment.
- Sepolia is used for application development/testing; Hoodi is used for validator and protocol testing. Network roles can change, so current guidance should be checked.

### Private Network
- Isolated network created for a developer, organization or group.
- Participation can be restricted to approved members.
- Network parameters and permissions can be configured.
- Used for internal development, experiments and enterprise applications.
- A private network is not automatically secure; it still requires proper configuration.

### Comparison

| Basis | Mainnet | Testnet | Private Network |
|---|---|---|---|
| Purpose | Production | Testing | Controlled/internal use |
| Access | Public | Public | Restricted |
| ETH | Real economic value | Test ETH, no intended real value | Configured for network |
| Transactions | Real | Experimental | Internal |
| Control | Public network | Public test network | Organization/group |
| Usage | Live DApps | Test contracts/upgrades | Enterprise/development |

### Importance and deployment path
Testnets allow safe experimentation, error detection and testing without spending real-value Mainnet ETH. Private networks provide controlled participation. Mainnet is used after testing is complete.

~~~
Develop → Local test → Testnet
   → Verify/fix → Deploy to Mainnet
~~~

**Conclusion:** Mainnet supports live applications, testnets provide a safe development environment, and private networks support controlled organizational use.

**PYQ:** Frequency **5/7**; supplied metadata **6, 9**.  
**Exam focus:** Definitions, purpose, comparison table and deployment flow.

---

## Q6. Explain Ethereum Virtual Machine (EVM) and its significance. [6 Marks]

### Introduction
The **Ethereum Virtual Machine (EVM)** is a decentralized execution environment that runs smart contracts on Ethereum. It provides a common environment for executing smart contract code and executes bytecode generated by compilers such as the Solidity compiler.

### Features
1. **Decentralized execution:** Contract execution is part of the distributed network.
2. **Deterministic execution:** Given the same valid transaction and state, compatible nodes obtain the same result.
3. **Smart contract execution:** Runs EVM bytecode produced from Solidity and other compatible languages.
4. **Gas mechanism:** Operations consume gas to measure computational resources.
5. **Controlled environment:** Contract code runs within a defined virtual machine.
6. **State management:** Executes operations that can update account balances and contract storage.

### Working
1. Developer writes Solidity code.
2. Compiler converts it into EVM bytecode.
3. Bytecode is deployed through a transaction.
4. User interacts with the contract.
5. EVM executes bytecode instructions and accounts for gas.
6. Successful execution records resulting state changes. Failed execution reverts state changes, although gas may still be consumed.

~~~
Solidity → Compiler → EVM bytecode
   → EVM execution → Transaction processing
   → Ethereum state updated
~~~

### Components
1. **Stack:** Temporary working area for instructions; follows LIFO.
2. **Memory:** Temporary data area during execution.
3. **Storage:** Persistent data associated with a smart contract.
4. **Program Counter:** Tracks the next instruction position.
5. **Gas:** Measures computational resources consumed.
6. **Opcodes:** Low-level instructions for arithmetic, logic, memory and storage operations.

### Significance
- Provides the execution environment for smart contracts and DApps.
- Ensures compatible nodes follow common execution rules.
- Supports decentralized rather than central execution.
- Provides controlled execution of contract instructions.
- Enables EVM-compatible networks to support EVM-based contracts, subject to network-specific differences.
- Gas limits help control computation and prevent unbounded execution.

**Applications:** DeFi, NFTs, decentralized exchanges, voting and token creation.

**Conclusion:** EVM is a fundamental Ethereum component that executes smart contract bytecode and enables deterministic, decentralized application execution.

**PYQ:** Frequency **3/7**; supplied metadata **4, 6, 8**.  
**Exam focus:** Definition, working diagram, components and significance. Remember: memory is temporary, storage is persistent, and stack is the instruction working area.

---

## Q7. Explain the implementation and deployment of smart contracts using Solidity. [6 Marks]

### Introduction
**Solidity** is a high-level, statically typed programming language used to develop smart contracts on Ethereum and other EVM-compatible platforms. Solidity source code is compiled into EVM bytecode.

### Implementation steps
1. **Set up environment:** Use Remix IDE or a framework such as Truffle or Hardhat; select compiler version.
2. **Write contract:** Define contract, state variables, functions and application rules.
3. **Compile:** Solidity compiler checks the code and generates EVM bytecode and ABI.
4. **Test:** Execute functions in a local environment or testnet and verify expected behaviour.

### Example: Simple Storage Contract

~~~solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleStorage {
    uint public storedData;

    function set(uint x) public {
        storedData = x;
    }

    function get() public view returns (uint) {
        return storedData;
    }
}
~~~

**Explanation:**
- pragma specifies the compiler version range.
- SimpleStorage defines the contract.
- storedData is a public unsigned integer state variable.
- set(x) stores the supplied value.
- get() returns the value without modifying blockchain state.

### Compilation outputs
- **Bytecode:** Compiled instructions used for deployment and EVM execution.
- **ABI (Application Binary Interface):** Describes how external applications encode calls and interpret contract results.

### Deployment steps
1. Select local network, public testnet or Ethereum Mainnet.
2. Connect a compatible wallet such as MetaMask and select the intended network.
3. Ensure funds are available for transaction fees where required.
4. Submit a deployment transaction containing contract creation bytecode and constructor parameters.
5. Network processes the transaction and includes it in a block.
6. Successful deployment gives the contract an address on that network.
7. Use the contract address and ABI to interact with its functions. State-changing calls require transactions and consume gas.

### Diagram
~~~
Write Solidity contract
        ↓
Compile: bytecode + ABI
        ↓
Test contract
        ↓
Select network and connect wallet
        ↓
Submit deployment transaction
        ↓
Obtain contract address
        ↓
Interact using ABI and address
~~~

### Advantages and applications
Advantages include automation, transparency, consistent execution, reduced intermediaries and decentralized operation. Applications include DeFi, NFTs, supply-chain tracking, voting and digital identity.

**Conclusion:** Implementation includes writing, compiling and testing the contract. Deployment submits its bytecode to a selected network, after which applications interact using its address and ABI.

**PYQ:** Frequency **2/7**; supplied metadata **6**.  
**Exam focus:** Solidity definition, simple program, bytecode vs ABI, deployment steps and diagram.

---

## Q8. Explain the role and significance of gas in smart contract execution. [9 Marks]

### Introduction
**Gas** is a unit used in Ethereum to measure the computational effort required to execute transactions and smart contracts. Each EVM operation consumes a specified amount of gas. Users pay transaction fees in ETH based on gas consumed and the effective gas price.

### Role of gas
1. **Measures computation:** Measures resources needed for arithmetic, execution and storage updates.
2. **Transaction fee calculation:** Gas consumed is used to calculate transaction fees.
3. **Limits execution:** Gas limits restrict resources available to a transaction.
4. **Prevents unbounded computation:** Transactions cannot execute unlimited instructions without consuming gas.
5. **Resource management:** Helps control computation performed by the network.
6. **Validator incentives:** Priority fees incentivize validators to include transactions.
7. **Code optimization:** Encourages developers to avoid unnecessary computation and expensive storage operations.

### Gas-related terms
1. **Gas Limit:** Maximum gas allowed for a transaction. If execution runs out of gas, it fails and state changes are reverted, but gas already consumed is charged.
2. **Gas Used:** Actual gas consumed by a transaction, depending on the operations performed.
3. **Effective Gas Price:** Amount paid per gas unit. Under Ethereum's fee mechanism it depends on the base fee and priority fee, subject to user fee settings.
4. **Base Fee:** Protocol-determined fee per gas required for inclusion; changes with network demand and is burned.
5. **Priority Fee (Tip):** Additional fee offered to incentivize validators to include a transaction.

### Fee calculation
**Transaction Fee = Gas Used × Effective Gas Price**

**Example:**
- Gas used = 21,000 units
- Effective gas price = 20 Gwei

Transaction fee = 21,000 × 20 Gwei  
= 420,000 Gwei  
= **0.00042 ETH**

### Working
1. User initiates a smart contract transaction.
2. User sets gas limit and fee parameters.
3. Transaction is submitted to Ethereum.
4. EVM executes contract instructions.
5. Gas is consumed according to operations.
6. If execution succeeds, state changes are processed and actual fee is charged.
7. If gas runs out, execution fails and state changes are reverted, but gas consumed is charged.

~~~
User submits transaction
        ↓
Set gas limit and fee parameters
        ↓
EVM executes contract and consumes gas
        ↓
     Execution?
      /      \
   Success  Out of gas
      ↓         ↓
State update  Revert state changes;
              gas consumed charged
~~~

### Significance
1. **Spam prevention:** Makes excessive transactions and computation costly.
2. **Network stability:** Helps control computational demand.
3. **Fair resource allocation:** Users pay according to resources consumed.
4. **Execution control:** Limits prevent unbounded transaction execution.
5. **Validator incentive:** Priority fees incentivize transaction inclusion.
6. **Efficient development:** Encourages optimization of smart contract code.

### Factors affecting gas consumption and fees
- Number and type of EVM instructions.
- Complexity of contract functions.
- Reading and writing contract storage.
- Transaction data and execution path.
- Network demand, which affects the base fee and transaction cost.

**Conclusion:** Gas measures computational resources, controls smart contract execution, discourages misuse and encourages efficient code, supporting Ethereum's stable operation.

**PYQ:** Frequency **1/7**; supplied metadata **9**.  
**Exam focus:** Definition, gas limit, gas used, base fee, priority fee, fee formula, numerical example, working and significance.

**Remember:** Gas is the unit of computational effort; Gwei is a denomination of ETH commonly used for gas prices; ETH is used to pay transaction fees.
