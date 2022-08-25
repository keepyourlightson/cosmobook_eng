# CosmosHub

## Cosmos ecosystem and Cosmos Hub

### **What is Cosmos?** <a href="#jkzn" id="jkzn"></a>

Cosmos is not a blockchain. It is decentralized network of independent and interacting blockchains called zones in the ecosystem. These zones run on Tendermint and communicate with each other through IBCs using hubs.

#### **Concept**

The Cosmos network operates on three different levels.

1\. Network layer. It allows transaction confirmations and other consensus messages to interact with the hub's blockchains.

2\. Consensus layer. It arranges nodes according to validators' decisions to add new transactions.

3\. Application layer: responsible for updating the state given a set of transactions, i.e. processing transactions..

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

All levels is combined by toolkits and applications with opensource code. For example, Tendermint connects the network layer and the consensus layer in a ready-to-use scheme that works automatically. This saves developers time and resources because they only work with app promotions.

### **Tendermint**

Tendermint is a solution that combines the network and consensus layers of the blockchain into a common engine, allowing developers to focus on application development rather than the complex underlying protocol.

Technically Tendermint can be described as a low-level protocol that performs the functions of a peer-to-peer network protocol and is responsible for the consensus algorithm. At the same time, it is optimized to solve the problem of fault tolerance of Byzantine generals (i.e. to find consensus) in distributed applications and for processing data in a large number of nodes (nodes).

\*_Byzantine fault-tolerance problem (hereinafter referred to as BFT) - in simplified form, this is the problem of finding consensus between network nodes, provided that a certain number of nodes are “fraudsters”_

Jae Kwon began working on the creation of a BFT protocol in 2014. On it could run a system of hundreds of nodes with trustless access and PoS as a protective mechanism. After all the necessary settings were made by 2018, the launch of the Cosmos network took place.

Validators in the network are chosen randomly in proportion to their stack share of the total number of coins cloned (i.e., in a perfectly standard way).

\*\* _Briefly: Tendermint acts as a network layer protocol, allowing nodes to communicate with each other and to come to a consensus. The consensus is based on the BFT model, while security is provided by the PoS mechanism. The principle and peculiarities of Tendermint operation are described in details and not very complicated_ [_here_](https://blog.cosmos.network/tendermint-explained-bringing-bft-based-pos-to-the-public-blockchain-domain-f22e274a0fdb)_._

Key features of Tendermint that make it a competitive blockchain mechanism:

1\. It can be applied to both public and private blockchains. If the application built on the engine determines that validators are elected based on ownership share, then the blockchain will be a PoS. But if developers introduce pre-authorization for validators, the blockchain will become private;

2\. High performance. Tendermint can process up to 1000 transactions per second;

3\. Instant finalization. This means that users can be sure that their transactions will be considered complete and final as soon as a block is created (which is not the case with Proof-of-Work blockchains, where a block is considered final only after a certain number of blocks are confirmed after it);

4\. Security. If a fork does happen, there is a way to determine responsibility. By a fork here we mean the simultaneous creation of several blocks, as a result of which the network is like a "branching". You can read more about this \[here].(https://docs.tendermint.com/master/spec/light-client/accountability/)

The Tendermint engine connects to the application layer using a protocol called Application Blockchain Interface (ABCI). The protocol can be built into any programming language, so developers have plenty to choose from.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Although Tendermint reduces blockchain development time manifold, creating a secure ABCI application from scratch remains a daunting task. CosmsSDK was developed to simplify this task as much as possible.

### **CosmosSDK**

CosmosSDK is an open-source framework for creating permissionless PoS blockchains like CosmosHub, or permissioned Proof-of-Authority (PoA) blockchains.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

The Cosmos SDK aims to allow developers to create their own customized blockchains that are compatible by default with other blockchains in the ecosystem, using pre-made modules and toolsets. In doing so, each developer can create a new module and it will be available to all other developers.

Features of the Cosmos SDK

1\. The consensus engine available by default when developing on the Cosmos SDK is Tendermint, currently the best BFT solution.

2\. The use of modules when creating an app-chain (an app-chain is a blockchain created for a separate decentralized application). All modules are in the public domain and their number is only growing.

3\. The Cosmos SDK was created by genuine experts in blockchain technology, is constantly being improved and is a secure environment for blockchain creation.

### **Stacking**

Stacking is the process of blocking a token to secure a public blockchain.

A validator is a node that is responsible for creating blocks, thereby protecting the network and processing transactions. Validators are rewarded for their work, which can consist of block finder rewards, transaction fees, and delegator commissions.

A delegator is any user who has sent (delegated) their tokens to any validator. The delegator receives rewards, proportional to their share of tokens, from the total number of tokens of the validator, and pays the validator a small commission for its services (the commission is set by the validator itself and usually does not exceed 5% of the delegator's reward).

To avoid cheating, the Validator that publishes incorrect data to the blockchain is penalized financially, losing some of its tokens. This is called slashing.

_We put liquid steaking in Cosmos network in a separate publication, there is another little sheet =) You can read it here. (russian language)_

### **Slashing**

Slashing is a "punishment" for the validator, which consists of confiscating a portion of his tokens. What percentage of tokens will be "slashed" depends on the breach committed by the validator and the threat to the safety of other network participants. This is not only a financial incentive for the validator to perform his duties in good faith, but also a measure that forces validators to "risk their own skin. At the same time, it's what motivates delegates to choose validators more carefully, since they too risk losing some of their tokens.

There are two types of events that lead to slashing:

**- Slashing 0,01%** can occur if the validator is offline for too long. Idle time is fixed if the validator does not sign at least 500 blocks out of the last 10,000 blocks.

In addition, the validator is dropped from the consensus and does not receive a block reward for at least 10 minutes (the term jail). Once the problems are fixed, the validator can re-join the validator set by sending an unjail transaction.

![](https://telegra.ph/file/f6a5f216f13d513987a2b.png)

\- **Slashing 5%** can happen if the validator signs two different blocks at the same time. This malfunction is harder to predict and results from poor operating practices or outright malicious intent on the part of the node operator. In addition to the 5% token, the validator loses the right to offer blocks and receive remuneration without the possibility of unlocking (effectively being removed from the validator set forever). All delegators of a given node receive their tokens back, the anbond period (i.e., the time to return tokens from stacking) is 21 days.

![](https://telegra.ph/file/97e89b3f303117a84a471.png)

### **IBC**

The Inter-Blockchain Communication Protocol, or IBC, is a framework that allows zones to cross-chain communication without establishing trust assumptions from a third party (i.e., without using bridges, for example), it can be compared to the TCP/IP protocol in traditional networking technologies. Interacting networks agree to trust each other's security model and use a distributed messaging standard to communicate and verify changes in network state. Thus, the IBC model inherits the lowest of the security of the networks involved in the message exchange (\*\_ meaning that if, say, the security of one network is 10/10 and the other 8/10, the security of the IBC model will also be 8/10\_).

The establishment of such interaction is resource-intensive for both networks. When one network initiates the sending of a message to another network, the public relayer transmits a proof of request message to the other network. The network receiving the message validates this proof using a light client, which reads the state of the sending network and writes a copy of this state to its own registry. This direct verification process guarantees the receiving network that the request was indeed valid, and only then does the state of the receiving network itself change.

IBC model has several important features (necessary trade-offs) because of the optimization towards security:

The receiving network is forced to assume that the transactional request has been finalized (finalized) in the network sending the message (request). Forks and block reorganization, which are common for probabilistic finality (e.g., the ether network), would destroy the fundamentals of the IBC security model. Therefore, IBC is compatible only with consensus mechanisms that have a guarantee of finality, such as Tendermint. As a solution, so-called "pegzones" can be used to set a finality threshold when interacting with a probabilistic network. But such a solution complicates the system and thus creates additional vectors for an attack on it.

The IBC model is too expensive for blockchains with low bandwidth and expensive blocks. But the Cosmos ecosystem does not have this problem, because IBC was originally developed to work with blockchains built with the Cosmos SDK, where IBC modules work at the network level, not at the smart contract level. In addition, it allows networks within the Cosmos ecosystem to redirect the cost and responsibility of recording the state of other ecosystem networks from applications to network validators.

Transaction costs for messaging between networks are borne by retransmitters, not users. Repeaters are often managed by validators who are motivated to keep both (sending and receiving) networks running. The economic model of IBC makes it rational to coordinate between different repeaters so that at the same time only one repeater serves one IBC channel. If a situation arises where none of the repeaters serves the channel, then the message is "stuck" until there is a serving repeater. Although this fact has no effect on the security of either the receiving or sending network, the viability of an IBC can be temporarily reduced for this reason. In order for IBC messaging to completely break down, one-third of all validators would need to stop working.

A schematic of the IBC is shown in the figure below (source \[here])(https://0xpostman.medium.com/part-2-cross-chain-security-models-compared-c4f91107cad4))

\* _The green arrows show the validator check stages of the transaction, and the purple ones show the transaction path (or any other cross-chain message)_

![](https://telegra.ph/file/de18cb6908699b3bf74e9.png)

Essentially, IBC transactions are packets of information that are transferred from one zone to another by publishing Merkle-proofs (more [here](https://ethereum.org/pt/developers/tutorials/merkle-proofs-for-offline-data-integrity/)) as proof that the information was sent and received.

In order for the receiving network to verify this proof, it must be able to keep track of the sender's block headers. This mechanism is similar to that used by [sidechains](https://blockstream.com/technology/sidechains.pdf) (more info [here](https://forklog.com/cryptorium/sidechains-faq/)), which requires that two interacting networks know about each other through a bidirectional flow of existence-validating transactions.

The IBC protocol uses two types of transactions: `IBCBlockCommitTx` , which interact with [hash](https://academy.binance.com/en/glossary/hash) the last block of any zone, and `IBCPacketTx,` which contain data about the legitimacy of the information packet and the sender's application.

For example, to update a "Zone1" block to "Hub" (or "Hub" to "Zone2"), an IBC BlockCommitTx transaction must be placed on "Hub" with a "Zone1" block hash (or on "Zone2" with a "Hub" block hash). (More information on transactions in the whitepaper: [тут](https://v1.cosmos.network/resources/whitepaper#ibcblockcommittx))

![](https://telegra.ph/file/97bd3b1e1bd282435bf2b.png)

To summarize: IBC allows interacting networks to function like read-oracles for each other. The security of such a model is resource-intensive, but allows the networks to interact without the need for a third party trusted party. For this reason, IBC is a very popular model and is always cited as one of the alternatives among some other messaging models.

IBC was launched in March 2021, and as of now (July 2022) it is enabled on 49 networks, and there are currently over 2.5M transactions per month using IBC (you can see [here](https://www.mapofzones.com/?testnet=false\&period=720\&tableOrderBy=ibcVolume\&tableOrderSort=desc)).

### **Peg zones**

Peg-zone is an account-based blockchain that connects zones within Cosmos with external blockchains such as Bitcoin or Ethereum. The need for them arises because Cosmos uses deterministic finalization, while Ethereum, for example, is probabilistic.

![](https://telegra.ph/file/1c83c9b2998526787f661.png)



Components that are used to interact external blockchains and Cosmos:

1. Ethereum smart contracts that act as asset custodians, capable of taking responsibility for their own Ethereum tokens and issuing their own Cosmos tokens.
2. Witness (witness, oracle): The witness component witnesses events in Ethereum. It waits for 100 blocks, the finality threshold, and implements this pseudo-finality. It runs a full Ethereum node to confirm state changes in Ethereum by sending \`WitnessTX' to the peg-zone. A common security model is used here, with Cosmos Hub validators also as witnesses to the peg-zone.
3. peg-zone is a blockchain interpreter built on Tendermint. It allows users to execute and request transactions. This is how Cosmos connects with Ethereum.
4. the authorizing party (signer in the schema) signs messages using the secp256k1 scheme. The signer component generates secp256k1 signatures via a `SignTx` message and sends it to the binding area to retransmit transactions for verification in the smart contract via the pipeline.
5. Relayer : The relayer component transmits an array of transactions signed by the Signer component and sends them to the Ethereum smart contract.

### **Interchain Security (ICS)**

One of the arguments that argue in favor of polkadot or cosmos is the shared security model (you can read it here). Briefly: all parachemes (as polk calls blockchains) use shared security, with polkadot guaranteeing that all blockchains in the network are secure and that any interactions between them are done correctly. The difference between traditional isolated security and shared security is well illustrated in the diagram. On the left is the traditional (isolated) security model, which is what Cosmos has now. On the right is the shared security model, as in Polkadot...and as it will be in Cosmos.

![](https://telegra.ph/file/8050d53cf4ef190181ea2.png)

At the moment, Cosmos security (block creation) is the responsibility of validators for each zone separately, but in the 3rd quarter of 2022 it is planned to introduce Interchain Security (interblockchain security) technology. This will allow a pool of validators, such as Cosmos Hub, to create blocks for a young zone, while the mechanisms of penalties for long offline mode, or for double blocks remain as for the "donor" hub, and an attack on the blockchain becomes economically inexpedient (as the price and number of tokens zastaykaned is higher). Important features are that the IBC is used for security de-encryption, and ICS is not required for each zone. Although the introduction of the technology has already been announced, the schemes and details are not yet available. It is only known that the first version will use all donor-chain validators, and later will include the possibility of partial donation. You can read more [here](https://github.com/cosmos/gaia/blob/main/docs/interchain-security.md).

### **CosmosHub**

To avoid connecting each new blockchain to all existing ones directly through an IBC, Cosmos offers a modular architecture in which there are regular heterogeneous blockchains - zones - as well as hubs - blockchains specifically designed to connect zones to each other.

The first hub launched on CosmosNetwork is CosmosHub. CosmosHub is a Proof-of-Stake general-purpose blockchain whose own token is called ATOM.

Cosmos Hub is the ecosystem's transaction registry, so tokens can be sent directly between zones via the IBC protocol. CosmosHub is the central blockchain of the Cosmos ecosystem. In fact, it is where the entire ecosystem started.

![](https://telegra.ph/file/bd28480cc4a5b3e2843e3.png)

Link to picture [here](https://mapofzones.com/?period=720\&testnet=false\&tableOrderBy=ibcVolume\&tableOrderSort=desc\&zone=cosmoshub-4\&fullscreen=true)

Development began in 2014, the Cosmos concept appeared in 2016, and as early as March 13, 2019 CosmosHub went live (recording of the launch broadcast [here).](https://www.youtube.com/watch?v=OALEhpn7ccM)

![](https://telegra.ph/file/79404f91631c8ae87a048.png)

The Cosmos network's native coin is Atom.

It has three main use cases:

1. Payment of transaction fees by users;
2. Participation in the management of CosmosHub;
3. Stacking.

ATOM tokens were distributed in the sid-round (5%), 10% went to Tendermint Inc. and 75% went in 30 minutes in the initial coin offering (ICO) in 2017. The cost of 1 Atom was 10 cents, the proceeds were 17 million. We will not calculate how many and who got the tokens (although we are very happy for those who made at least 10 bucks from 10 cents and their hand did not shake).

At the moment the total supply is 302347059 ATOM, the maximum supply is unlimited. This is due to the fact that TendermintCore rewards are paid to steakers with new coins. At the same time, the inflation rate is adjusted in real time depending on the amount of coins in the stacking and the number of stakers. At the time of this writing, it was 12.4%. You can see the current information in Bro'n'Bro [dashboard](https://monitor.bronbro.io/d/cosmos-stats/cosmos-stats?orgId=2\&refresh=5s).

### **Links:**

Cosmos whitepaper: [here](https://v1.cosmos.network/resources/whitepaper)

Tendermint: [here](https://docs.tendermint.com/)

IBC: [here](https://ibc.cosmos.network/)

Peg zones: [here](https://blog.cosmos.network/the-internet-of-blockchains-how-cosmos-does-interoperability-starting-with-the-ethereum-peg-zone-8744d4d2bc3f)

About slashing: [here ](https://medium.com/p2peconomy/slashing-in-cosmos-network-bbbaff949ee5)and [here](https://docs.cosmos.network/master/modules/slashing/)

### Wallets and dashboards in Cosmos ecosystem <a href="#yine" id="yine"></a>

#### **Wallets**

Crypto wallets store your private keys and give the user access to their own assets. There are many different types of crypto wallets, from mobile apps and web wallets to hardware wallets.

#### **Keplr**

![](https://telegra.ph/file/83bf46d303d26af59b14a.png)

Keplr has quickly become a staple wallet for the Cosmos ecosystem, and stealing with Keplr's wallet and dashboard is easy (full [guide](https://antropocosmist.medium.com/%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C%D1%81%D1%8F-%D0%BA%D0%BE%D1%88%D0%B5%D0%BB%D1%8C%D0%BA%D0%BE%D0%BC-keplr-462d430615b3)). Keplr offers a mobile wallet app for iOS and Android, as well as a browser extension similar to Metamask, which is the easiest way to safely start steaking. In addition to the browser extension, Keplr provides a simple [monitoring dashboard](https://wallet.keplr.app/) to view available tokens, staked coin balances and rewards across the 20+ networks it currently supports. Cosmos chains can also integrate a dashboard [staking management](https://wallet.keplr.app/#/dashboard) so users can stack tokens in their own ecosystems.

According to the 2022 roadmap, Keplr is planning several interface improvements that will make the already one of the best user interfaces even better. For example, one such upcoming improvement is the addition of a "validators" section.

Choosing the right validators is very important, and newcomers to Cosmos may not know which ones to choose, so Keplr wants to help validators that are active get a significant vote. The team plans to do this by updating the validator page and providing helpful descriptions that will make it easier for users (potential delegates) to decide which validator to choose. It will also be possible to communicate between validators and delegates, which should encourage them to work more closely together. You can find the various resources for steking[ on Keplr here](https://keplr.crunch.help/).

You can connect the Ledger following these [manual](https://support.ledger.com/hc/ru/articles/4411149814417-%D0%9A%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-Keplr-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81%D0%BE-%D1%81%D1%87%D0%B5%D1%82%D0%B0%D0%BC%D0%B8-Cosmos-ATOM-%D0%B2-Ledger?docs=true).

#### **Cosmostation**

![](https://telegra.ph/file/6a6f2c24f559dc9f894ae.png)

Cosmostation is a solution that provides a mobile wallet for convenient steaming right from your phone, as well as a web wallet that allows you to connect and sign transactions from your hardware wallet. As a longtime investor in the Cosmos ecosystem, Cosmostation has earned a solid reputation for providing excellent end-user support with proven products such as Cosmos Explorer [_Mintscan._ ](https://www.mintscan.io/cosmos)Cosmostation also supports over 30 networks, giving users many options to use.

Cosmostation also has many [manuals](https://www.cosmostation.io/files/cosmostation\_guide\_web\_en.pdf) and support resources to help you if you get stuck. A video tutorial on how to set up a mobile wallet is [here](https://www.youtube.com/watch?v=pMzrOypmTOk). A video tutorial on how to steak with Cosmostation is [here](https://www.youtube.com/watch?v=tWQOlDm1i74\&t=43s).

If you want to select different validators, you can see their history, activity and uptime right from the validators section on [Mintscan](https://www.mintscan.io/). There's a video tutorial on how to choose a validator -[here](https://www.youtube.com/watch?v=f44SAnke1hk) and [here](https://www.youtube.com/watch?v=lX1QY4mFC6E). Cosmostation will be launching a browser extension later this year. To start steaking through your mobile wallet, download [Cosmostation for Android](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion) or [iOS here](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion).
