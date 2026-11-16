# Unit V – Quick Revision

**Blockchain Technology (410243) | Unit V | CO4**

## Q1. Ethereum – 7/7
- Open-source decentralized blockchain for smart contracts and DApps.
- Proposed 2013; launched July 2015; native asset ETH.
- Features: decentralization, smart contracts, EVM, gas, transparency, DApps and programmability.
- Architecture: Application → Smart Contract → Execution (EVM) → Consensus → Data/Network.
- Components: ETH, EVM, contracts, EOAs, contract accounts, gas, nodes and validators.
- Current consensus: Proof of Stake; transition from PoW in September 2022.
- Metadata: 6, 8, 9.

## Q2. Smart Contracts – 7/7
- Self-executing blockchain programs triggered by predefined conditions.
- Lifecycle: Write → Compile → Deploy → Interact → Execute → State update.
- Purpose: automation, transparency, fewer intermediaries, accuracy and efficiency.
- Functional types: Smart Legal Contracts, DAOs, Application Logic Contracts (ALCs).
- Examples: escrow, DAO voting, DEX swaps, NFTs and supply-chain records.
- Limitations: bugs, difficult upgrades, oracle dependency and gas costs.
- Metadata: 4, 6, 8, 9.

## Q3. Swarm – 6/7
- Decentralized P2P storage/content-distribution platform for Ethereum ecosystem.
- Features: distributed storage, content addressing, redundancy, DApp integration and BZZ incentives/payments.
- Working: Upload → Chunk → Address/distribute → Store on nodes → Retrieve → Reconstruct.
- Role: off-chain storage for large files, websites and DApp content.
- Ethereum executes contracts and maintains state; Swarm stores/distributes content.
- Metadata: 4, 6, 9.

## Q4. Whisper – 5/7
- Historical decentralized P2P messaging protocol designed for Ethereum applications/nodes.
- Features: encryption, topic filtering and off-chain messaging.
- Working: Create → Encrypt → Topic/filter → P2P propagation → Filter → Decrypt/read.
- Purpose: DApp communication, notifications and reduced on-chain message load.
- Not permanent blockchain storage or the current core Ethereum messaging service; Waku is associated with successor work.
- Metadata: 6, 9.

## Q5. Ethereum Networks – 5/7
- **Mainnet:** Production public Ethereum network; real-value ETH and live applications.
- **Testnet:** Public testing environment; test ETH has no intended real value. Sepolia for application development; Hoodi for validator/protocol testing.
- **Private network:** Isolated, controlled network for development or enterprise use.
- Compare purpose, access, ETH value, transactions, control and usage.
- Deployment: Develop → Local test → Testnet → Verify/fix → Mainnet.
- Metadata: 6, 9.

## Q6. EVM – 3/7 [6 Marks]
- Decentralized execution environment for Ethereum smart contract bytecode.
- Working: Solidity → Compiler → Bytecode → EVM → Transaction execution → State update.
- Components: Stack (LIFO), Memory (temporary), Storage (persistent), Program Counter, Gas, Opcodes.
- Significance: deterministic execution, common rules, DApp support and controlled computation.
- Metadata: 4, 6, 8.

## Q7. Solidity implementation/deployment – 2/7 [6 Marks]
- Solidity: high-level, statically typed language for EVM smart contracts.
- Steps: Setup IDE → Write → Compile → Bytecode + ABI → Test → Select network → Connect wallet → Deploy → Contract address → Interact.
- Example: SimpleStorage contract with set and get functions.
- Bytecode is deployed/executed; ABI describes external interaction.
- Metadata: 6.

## Q8. Gas – 1/7 [9 Marks]
- Gas measures EVM computational effort.
- Terms: Gas limit, gas used, effective gas price, base fee, priority fee.
- Formula: Transaction Fee = Gas Used × Effective Gas Price.
- Example: 21,000 × 20 Gwei = 420,000 Gwei = 0.00042 ETH.
- Base fee is burned; priority fee incentivizes validators.
- Out-of-gas execution fails; state changes revert and gas consumed is charged.
- Metadata: 9.

## Important distinctions
| Concept | Meaning |
|---|---|
| EVM memory | Temporary during execution |
| EVM storage | Persistent contract state |
| EVM stack | Temporary instruction working area |
| Bytecode | Compiled instructions executed by EVM |
| ABI | Interface for external contract interaction |
| Contract address | Address identifying deployed contract |
| Gas | Unit of computational effort |
| Gwei | ETH denomination used for gas prices |
| ETH | Asset used to pay transaction fees |
| Ethereum | Contract execution and blockchain state |
| Swarm | Decentralized content storage/distribution |
| Whisper | Historical off-chain messaging protocol |

## Diagrams to practise
1. Ethereum architecture.
2. Smart contract lifecycle.
3. Swarm upload/chunk/distribution/retrieval.
4. Whisper message flow.
5. Testnet-to-Mainnet deployment.
6. EVM execution.
7. Solidity implementation/deployment.
8. Gas execution and out-of-gas branch.
