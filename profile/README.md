## Welcome!

### Introduction
Fraud across all industries has been increasing exponentially and costs users billions of dollars per year. The core problem boils down to data authenticity and integrity. The solution must address these problems in a scalable manner. AliceNet is an Ethereum-based Layer 2 (L2) Proof of Stake (PoS) blockchain conceptualized to address the concerns around provability, and ease of provability concerning its own state. Its foundation was derived from Google Trillian, the verifiable data structures used with Google’s own Certificate Transparency systems.
 
AliceNet was first developed to build a better public key infrastructure (PKI) for the advertising industry to address the problem of fraud. Our system allows for the negotiation and distribution of encryption keys and enables private data to be securely communicated in any environment. The goal of PKI is to assign unforgeable identities to its members to reduce fraudulent and malicious incidents by ensuring the integrity and authenticity of communications. Early versions of the PKI were iterated on the Ethereum mainnet, but storage costs, throughput, and difficulties integrating enterprise partners made it necessary to explore an alternative L2 solution.

When building AliceNet, we realized that the primitives we applied to transparency and provability in advertising could be leveraged to create a system that would benefit the entire Web3 ecosystem. For example, AliceNet allows multi-chain bridging between the Ethereum mainnet and its satellite L2 chains; finite, indexed datastores that reduce state bloat; and partial transactions that permit users to retain control over their assets. Due to the optimized nature of AliceNet, these features cost less than comparable systems currently available in Ethereum. 

### Architecture
AliceNet is a hybrid of Bitcoin’s Unspent Transaction Output (UTXO) and Ethereum’s account-based architecture, which gives us improved efficiency for transaction processing, flexibility, and scalability. This UTXO-based transaction model enables users to get all of the benefits of complex logic handling that comes with predefined smart contracts, but without requiring smart contract code – or even deploying a smart contract at all. 

For example, UTXO transactions have inputs and outputs. The inputs reference UTXOs that haven't been spent, and the outputs define the new UTXOs that are created when the transaction is successfully transmitted to the network. Once the inputted UTXOs have been spent, any attempts of a replay attack fail immediately because the original UTXO no longer exists. Better yet, users can also perform multiple operations in a single transaction securely, with only the overhead of a normal transaction, while also reducing the possibility of error and unnecessary loss of funds. 

Uniquely, UTXOs in AliceNet can represent different types of assets and let users transact directly with one another without the help of any centralized firms, escrow providers, or other third parties. Furthermore, AliceNet’s escrow mechanism can be directly represented by the transaction itself, which again forgoes the need for a smart contract and reduces the complexity and cost of listing assets.
 
The finality guarantee of the originating chain determines the availability of assets deposited onto AliceNet. We wait for finality guarantees to ensure that the user deposited the asset, and that the history can’t be changed in the originating chain. Once in possession of this object on AliceNet, the user can send it around the market or withdraw it to other sidechains.
 
### Tokens
AliceNet operates on a two-token model: ALCA and ALCB. ALCA acts as the governance and staking token. ALCB is the utility token designed to pay transaction fees inside of AliceNet. Both tokens follow the ERC-20 standard that exists on the Ethereum blockchain. 
 
ALCA allows you to:
Stake your tokens in our public staking system and accrue ETH profits resulting from transactions on AliceNet. If you stake your ALCA tokens long enough, you will earn additional rewards in the form of ALCA and ETH. If you accrue a large amount of tokens, you may even be eligible to become a validator.

Also, those who stake ALCA participate in AliceNet’s governance system. We believe that community governance is a powerful tool that can help direct us on the best path forward for the future utility of the technology we’re building, and we want those who invest with us to have a voice.
 
ALCB allows you to:
Send transactions through AliceNet. ALCB are minted when an interested buyer sends ETH to ALCB’s ERC-20 smart contract on the Ethereum mainnet. When new ALCB tokens are minted, 75% of the associated ETH value set aside per each ALCB contract is distributed to ALCA validators and public stakers. 

To spend ALCB, it must first be deposited into AliceNet. When a transaction is executed, the cost in ALCB is burned from the total available supply, and the remaining 25% of the associated ETH value set aside per each ALCB contract is distributed to ALCA validators and public stakers.
 
### Bridging
AliceNet bridging allows for transactions across the Ethereum mainnet and Ethereum-based L2 chains. To enter into a bridge within AliceNet, assets must first be deposited into a bridge pool. Each bridge pool is uniquely based on an object or asset type with an associated fee that can only be paid with ALCB.

When an asset is deposited in its respective bridge pool, the user is required to transfer possession of it to the appropriate smart contract. After a few blocks (for security), the deposited asset is then accessible on AliceNet. When the transfer is complete, the asset can be withdrawn to another blockchain or back to the mainnet, possibly with a different owner. 

### Transactions
AliceNet simplifies the rules of transaction validation by using object-specific validation logic. This makes the verification algorithm more efficient and provides more granular proofs of the blockchain state. The faster throughput significantly reduces the computation load on our network, which works well when bridging to the Ethereum mainnet. Also, given that the UTXO set constantly updates every time a new block is added to the network, AliceNet receives and sends the most up-to-date information to the bridged chain. 
 
AliceNet has no scripting language and operates like a series of precompiled smart contract templates. Each transaction in AliceNet encompasses its complex smart contract, as defined by the user at the time of construction. The smart contract logic is created by chaining together a set of small operations, with each operation defined by the UTXOs consumed and created. The composition of these simple operations is leveraged to create complex interactions like performing secure escrow for the exchange of assets between individuals.
 
### Proofs and Verifications
AliceNet is a system designed to enable compact proofs of state and efficient verification of state transitions in a blockchain network. We use Sparse Merkle Trees (SMT) to store and prove the state of the system. Additionally, SMTs support a variety of cryptographic primitives for signature verification.

One promising feature of AliceNet is the construction of state channels, which facilitates off-chain transactions. By utilizing a hybrid solution based on AliceNet, parties can negotiate a BLS multi-signature account and create a smart contract on the Ethereum blockchain. This allows for the exchange of value with only a single deposit required, and provides a mechanism for exits through proofs of state against a recent snapshot of AliceNet.

### Security Through Accusations
Validators are the first line of defense for AliceNet’s security, specifically by making accusations against other validators when an invalid state proposal is performed. Invalid state proposals can take the form of any illegal state transformation, such as creating money out of thin air or making two proposals at the same height and round. When an accusation is proven to be true, the malicious validator loses their position and their staked ALCA holdings are slashed and distributed to the other stakers; a portion of the ALCA is set aside for the accuser.

Accusers are required to pay a small gas fee in ETH to make an accusation on the mainnet, but the reward they receive far outweighs the initial cost upfront. We also entrust our public stakers to be vigilant when it comes to malicious activity on the chain. After submitting the necessary logic to the appropriate smart contract, all stakers receive their proportionate amount of the slashed ALCA tokens. This reward encourages stakers to look out for malicious behavior to preserve the integrity of AliceNet.
 
### Marketplace Partial Transactions
UTXO-based blockchains that support multiple assets can be used to construct escrow-based transactions for the secure exchange of assets between parties. This is fundamentally different from the traditional methods used in Ethereum, which require a smart contract or external party. AliceNet restricts the transaction hash so that you can arbitrarily extend a transaction to include participants who can sign the inputs and the outputs independently of each other. The first participant effectively seals a transaction by inputting an asset they're currently holding, outputting a specific amount of an asset that they want in exchange, and then broadcasting it to the network. Another participant agrees to the terms set in the predefined inputs and outputs and then completes the transaction by generating their signature on the outputs. Only then is the transaction considered valid and can be successfully transmitted to AliceNet to be included in the block.
 
### AliceNet.js
AliceNet.js is the supporting library for interacting with AliceNet. It’s an underlying subset of abstractions for interacting with the RPC endpoints of an AliceNet node to accomplish most basic tasks in JavaScript such as handling secp256k1/BN wallets and constructing UTXO-based transactions composed of value and datastore types. Our team designed this library to simplify the development process on our chain. Users streamline complex tasks which would otherwise require hundreds of lines of code into a single function. You run the function, and all our code happens in the background.

### Conclusion
In the beginning, L2s were created in no small part as a solution to blockchain scalability. But as the Web3 ecosystem expands, L2 interconnectivity is more important than ever. There are already enough competing L2s in Web3. What we need is an L2 that can give users easy access to a host of features and platforms that can’t be found on any one chain, that helps create an optimal Web3 by way of bringing the competition together. 
We designed AliceNet to be the L2 chain that does exactly just that. Our combination of compact state proofs, state rent, and UTXO-based datastores act as the ideal base for a Web3 PKI. You can also create keys and enforce them with compact state proofs while paying only for the duration they are required to exist. Using our native multisig support and state channels, you can be certain that your activities will be as inexpensive as possible, and everyone involved will be secure in the process. Our transaction model leverages the security of the Ethereum mainnet and ZK rollups to achieve a secure hub and spoke model that is not centered upon the Ethereum mainnet itself. Partial transactions cost users nothing to propose an action, and fees are only paid if a transaction occurs. Our technology allows for true no-risk, no-loss offers—not possible in conventional Ethereum account-based chains. 

