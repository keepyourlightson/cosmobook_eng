# Axelar Network

![](https://img2.teletype.in/files/d4/e8/d4e8c214-107e-4eca-9ab7-e20c464f623d.png)

## Axelar Network

Axelar is a universal overlay network connecting all blockchain ecosystems, applications and assets, whose objective is to ensure Web3 interoperability. In simple terms, Axelar serves as an intermediary for interoperability between different networks.

Axelar sees the following as their main goals:

\- Give blockchain developers the ability to easily connect to Axelar and interact with other blockchains.

\- Provide developers of decentralized cross-chain applications with composability (\*composability is a system design principle that deals with the interrelationship of components. A highly composable system includes components that can be selected and assembled in various combinations to meet specific user requirements. Within the cryptosphere, composability refers to the ability of decentralized applications and DAOs to effectively clone and integrate with each other and exchange tokens/messages in an interoperable manner).

\- Allow users to easily and conveniently interact with decentralized applications on various platforms.

The Axelar network consists of three main components operating at two functional levels (network layer, and smart contract layer):

1\. A decentralized network that is served by a set of validators and through which transactions are made.

2\. Gateways are smart contracts that provide a connection between Axelar Network and any other L1 blockchain. Gateways can operate on top of any L1 blockchain. Validators check gateways for incoming requests - READ function (essentially validators read incoming requests from the gateway), then vote for the transaction, as discussed further below, and send the transaction to the destination network gateway - WRITE function.

3\. APIs and SDKs available to developers allow them to easily make their blockchains and applications compatible with Axelar, and thus they have the ability to perform any cross-chain interaction between any blockchain.

### **Validators**

A set of validators is formed in a trustless way (i.e. every user who meets certain selection criteria can be a validator). And it is in the operation of validators that the main distinctive feature of Axelar lies.

Validators in the Axelar network have two main roles. The first role is standard - consensus participation, block finding and transaction validation. And the second is that validators must validate all cross-chain transactions that the Axelar network processes. They are therefore required to run a light client or full node for at least one external network to provide a local record of its state (or states if multiple networks are involved), and while each individual validator can only serve the networks they want, Axelar's reward system is designed so that validators are interested in serving as many networks as possible. Using this knowledge of external network states, Axelar validators collectively vote (consensus voting, more details below) on messaging requests and initiate state changes in order to send a transaction to the receiving network.

### **How it works**

User wants to send token from Solana network to Rekt network. Validators, unlike the user, know that Solana = Rekt, so they allow such transfer without any problems. Now how it actually works.

The user wants to send tokens from network A to network B. To do this, he deposits tokens to a deposit address in network A and waits for the Axelar network to validate this deposit. Axelar validators running nodes (or light clients) in network A check whether the user has actually made a deposit, vote for or against the transfer, and if the required number of votes is accumulated, the Axelar network confirms the transaction. Further, if the receiving network B has an Axelar gateway connected, the transferred tokens are mined by the Gateway smart contract and sent to the deposit address in network B. Each Gateway smart contract is controlled by a private key, for a smart contract to perform any transaction, the transaction must be signed with this key. Each validator has a portion of this key, so they must again come to an agreement by voting to sign the transaction. If this agreement is reached, the token is sent to the deposit address in network B and the token transfer process ends there. It is worth noting that not only token transfer, but also any messaging between networks takes place using this principle.

The whole process is shown graphically in the figure (green arrows show the transaction validation algorithm, purple arrows show the path the message follows from network A to network B).

![](https://telegra.ph/file/3d460206f2710c17cae7b.png)

### **Voting validators**

The consensus voting process combines PoS mechanism and threshold signature scheme (TSS). TSS, like multisig, requires a certain minimum number of validator signatures for request approval. The key difference of TSS model is that for common signature the private keys are assembled before signing. During the validators rotation and formation of a new set of validators, new private keys are generated and distributed, using which a new TSS signature is made. This serves as additional protection against a possible attack on the system, but also adds additional risks associated with the TSS generation process. The minimum threshold value (\*minimum _number of validator signatures_) for approving a messaging request is variable and depends on the receiving network, which allows each interconnection to have unique security parameters.

### **Gateways**

Gateways (or Gateway smart contracts) allow messages to be transmitted between any networks connected to Axelar, with each such EVM compatible network having a separate gateway (\*what _gateways are used for EVM incompatible networks, we could not find information_ at this time). Each gateway is controlled by its own private key, as explained above.

### **Relays (repeaters)**

Why relays are used in Axelar is better explained by a practical example.

In the example above, when a user initiates a token transfer from network A to network B, the user first generates a deposit address associated with that transaction on network A and sends the number of tokens it wants to transfer to network B. The relayers in turn pass a request to the validator to verify this address and vote on the validity of the transaction. Without relays, validators simply wouldn't know which addresses to validate.

### **Satelite**

Cross-chain transfers can be performed by the user through the Satellite app. At the moment, only a beta version is working, which supports only a small set of networks. To see what Satellite is like, [click here](https://satellite.money/).

It is worth adding that the Axelar blockchain only stores information related to gateway contracts and cross-chain transactions (i.e. it does not store a complete registry of the state of the networks that exchange messages through it).

### **Axelar's prospects and risks**

It can be said that Axelar is like the brain for all heterogeneous blockchain networks. It can both read and write functions, aggregates various indeterminate inputs and uses them to compute a single deterministic output, which is a simple yes/no decision. The network boasts an impressive set of offerings that will make it attractive to developers as a base for cross-chain applications.

\- Built-in support for IBC provides the growing Cosmos ecosystem with another solution for interacting with networks that lack consensus mechanisms with immediate finalization.

\- The TSS will allow the system to configure a minimum consensus threshold for each individual network.

\- The hub-and-spoke model allows the number of networks in a system to increase linearly with the number of connections required to connect them. And in a world where the number of different blockchains is growing rapidly, this approach has a huge advantage over pairwise connections (\*pairwise _connections, where a bidirectional link is set up between two separate networks_).

In the short term, Axelar's biggest drawback is their PoS-based economic security model. If fewer funds are locked into Axelar than the network they serve, fraudsters have an incentive to attack. However, since Axelar is built on the Cosmos SDK, this disadvantage may be mitigated with the imminent introduction of a cross-network security model (\*Interchain _Security, sometimes called shared security_) in the Cosmos ecosystem.

### **Long-term risks**:

1\) If an attacker gains control of 2/3 of all validators, then they will be able to control Axelar and send any requests to all networks connected through Axelar.

2\) If 1/3 of Axelar validators (meaning 1/3 of all Axelar minted coins) stop working, other networks will suffer because interchain messaging between them will not be possible.

So if Axelar succeeds, the crypto world will have another potential, albeit unlikely, black swan.

### **Links**

Axelar official website [here](https://axelar.network/).

The official Axelar blog [is here](https://axelar.network/blog).

Whitepaper (lots of technical description about Axelar's work) [here](https://axelar.network/wp-content/uploads/2021/07/axelar\_whitepaper.pdf).

Article about cross-chain model comparison by 0xpostman (there's one about Axelar) [here](https://0xpostman.medium.com/part-2-cross-chain-security-models-compared-c4f91107cad4).
