# Gravity Bridge

![](https://img3.teletype.in/files/25/69/2569f548-689e-4733-b6af-97857ab7a2a6.png)

## Gravity Bridge

In December 2021, together with more than 100 validators, the Swiss non-profit organization, Interchain Foundation, which manages the Cosmos (Atom) ecosystem, launched Gravity Bridge, a bridge created by decentralized service provider Althea.

**Gravity is** a bridge between Ethereum and Cosmos-based blockchains.

First, a high-level overview: Gravity allows people to transfer tokens from Ethereum to Cosmos and back by locking tokens on the Ethereum side and mining equivalent tokens on the Cosmos side. Unlike many other bridges, Gravity is non-castodial - you only need to trust the security of the Cosmos network, not third-party bridge administrators who can run off with your funds.

### **Here's how you can use Gravity as a practical example:**

You send 25 DAI to Gravity's contract on Ethereum, specifying that your address on Cosmos should receive the DAI.

Validators on the Cosmos network see that this has happened and mine 25 DAI on Cosmos for your address.

DAIs can now be sent to other Cosmos accounts, used in Cosmos applications, transferred to other Cosmos networks via IBC, etc.

To return to Ethereum, you send a DAI to the Gravity module on the Cosmos network, indicating that it should be received by your Ethereum address.

Cosmos validators burn DAIs on the Cosmos network and send an Ethereum transaction, forcing the Gravity.sol contract to send 25 DAIs to your Ethereum address.

### **How it works**

The Gravity Bridge consists of several components:

* Gravity.sol: an Ethereum smart contract on the Ethereum blockchain.
* Cosmos Gravity module: a Cosmos module designed to run on the Cosmos Hub.
* Orchestrator: a program running on Cosmos validators that monitors the Ethereum chain and sends events occurring on Ethereum to Cosmos as messages.
* Relators: a network of nodes that compete for the ability to receive payment for sending transactions on behalf of Cosmos validators.

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

Tokens are blocked on the Ethereum side by sending them to the Gravity.sol smart contract. This triggers an event that can be observed by the validators running the orchestrator. When a quorum of validators agrees that the tokens have been blocked on Ethereum, including the necessary confirmation blocks, a relay is selected to send an instruction to the Cosmos Gravity module, which issues new tokens.

To transfer tokens from the Cosmos hub to the Ethereum blockchain, tokens in the Cosmos network are destroyed and an equal amount of them are released (they were previously deposited) from the Gravity.sol smart contract.

The Cosmos Gravity Bridge is designed to work on the Cosmos Hub. It is focused on maximum simplicity and design efficiency. The bridge can transfer ERC-20 assets created on Ethereum to the Cosmos-based network and back to Ethereum. Transactions are done in batch mode, and transfers are pure transfer. This provides efficiencies at scale and reduces the transaction cost per transfer.

Bridges with Cosmos networks derive their reliability from the degree of trust associated with the Cosmos network to which they connect. Peg-zone validators must support a trusted Ethereum node. This is mandatory. This removes all of the trust and game theory issues that typically arise when engaging independent relays. Once again, this greatly simplifies the design.

You can view all the details of the bridge [here](https://www.gravitybridge.net/post/how-gravity-works).

Today Gravity Bridge allows you to transfer the following tokens:

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

Gravity is also compatible with any EVM network, so in the future we plan to see suggestions from the community to implement other tokens from other networks, such as Polygon.

### **Security**

Gravity Bridge was developed with security in mind. The code has been in test networks with a decentralized set of validators for over a year, and three audits have been conducted - Code4Arena-based, Informal and Least Authority audits.

The Althea team (one of the authors of Gravity Bridge) is also working closely with the Interchain Foundation to support the security of Gravity Bridge rentals from Cosmos Hub, which will improve Gravity Bridge security at the cost of tokens placed on Cosmos Hub.

**GRAV token**

Cosmos® Gravity Bridge™ was launched with a decentralized set of validators and approximately half of the tokens allocated to the DAO community for discretionary airdrops, future ecosystem support and liquidity mining. It is supported by an active and healthy community of token holders and validators who will make guiding decisions such as implementation of interconnect stacking, LM and airdrops.

<figure><img src="../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

**Statistics on a single slide (**[**here**](https://monitor.bronbro.io/d/gravity-stats/gravity-stats?orgId=2\&refresh=5s)**):**

<figure><img src="../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

### **NFT bridge**

There are a number of NFT projects being developed or implemented in the Cosmos ecosystem today, but there is still work to be done before Cosmos projects get a robust and fully working NFT protocol. To that end, Gravity Bridge is working closely with one well-known project, Stargaze, to provide an NFT bridge between the Cosmos ecosystem and Ethereum via Gravity Bridge.

Thus, while it is currently possible to mine NFT and even connect EVM/ERC721 NFT to Cosmos, the standard for transmitting NFT between networks via IBC has not yet been implemented, severely limiting the adoption and use of NFT in this ecosystem.

ICS721 is a proposed Cosmos-based NFT standardization similar to the ERC721 standard for Ethereum. It was created by the IRISnet development team and describes the requirements needed for NFT interworking.

Gravity Bridge and Stargaze are currently working closely on ERC721 and ICS721 interoperability, including creating the structure and initial test transactions to send ERC721 NFTs across the bridge to Cosmos.

Nevertheless, further work on the ICS721 standard is needed to implement cross-chain, proper use of Cosmos NFTs, and to send ERC721 NFTs through the Cosmos ecosystem in an interoperable way.

For this reason, Gravity Bridge is initiating an NFT ICS721 working group to bring together representatives of NFT projects across the Cosmos ecosystem to strategize and implement the ICS721 standard. Details [here](https://www.gravitybridge.net/post/announcing-the-ics721-workgroup).

Also the [cooperation](https://www.gravitybridge.net/post/irisnet-to-integrate-gravity-bridge-providing-eth-cosmos-liquidity) with IRISnet has been announced.

### **DAO**

Gravity Growth is a multi-organizational management and curatorial concept: a structure of checks and balances to not only keep the infrastructure running smoothly, but also to prepare it for any storm and carry it into the future (same thing from project to project, but everyone gets twisted in the description as they can).

The federated DAO will consist of representatives from the Gravity Grants team and working groups known as Gravity Groups, which manage the GRAV wallet with a multisig. This multisig is designed to curate and administer Gravity Grants.

Gravity bands can be divided into the following categories:

* community development;
* marketing;
* recruiting and ecosystem growth;
* development toolkit;
* the public goods of the cosmos.

Instead of a corporation or board of insiders, each gravity group or sub-DAO will elect a representative who will be a member of Gravity Grants and sign 2/3 multi-sig. After the original charter members have served their term, new members must be elected at least once a year, or a special election may be scheduled through the board. These members evaluate the completion of Gravity Grants and release the remaining funds.

<figure><img src="../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>

### **Airdrop**

On February 9, 2022, the Airdrop was announced and passed by a vote:

_Proposal 16_ - Provide 13,750,000 GRAV to the Osmosis community general fund, the use of which will be determined by Osmosis management. In addition, this proposal allocated 1,100,000 GRAV to ION owners during the Vega update on December 15, 2022 (Snapshot taken on 12/15/2021).

_Proposal 14 and Proposal 15_ - Provide a total of 110,000,000 GRAV to ATOM Stackers who voted or passed to a validator who voted on Cosmos _Proposal_ #49, which occurred on June 29, 2021 (Snapshot taken on 06/29/2021).

\~80,000 ATOMs qualified for the airdrop, which means that participants received an average of 1,350 GRAVs. The actual number obtained was calculated based on the number of ATOMs possessed at the time of the snapshot.

### **Team plans for 2022-2023**

* Improved user interface and smoother UX ;
* ICS721 + NFT bridge implementation ;
* tighter integration of EVMOS ;
* support for multiple evm+permanent integration with new projects;
* liquidity for DEX/AMM ;
* increased volume and reduced commissions/time tx for bridge users.

**Links:**

* [GitHub](https://github.com/Gravity-Bridge/Gravity-Docs/blob/main/docs/upgrading.md)
