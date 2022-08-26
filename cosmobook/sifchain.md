# Sifchain



![](https://img4.teletype.in/files/3c/2c/3c2c61bb-beac-45a2-b742-0b58f315f921.png)

## Sifchain

"Sifchain aims to create a blockchain and cryptocurrency world in which any asset around the world can move freely between different blockchains, and do so quickly and at the lowest possible cost." This is the statement made by the Sifchain team.

**SifDEX is** a decentralized exchange (DEX) that allows users to exchange digital assets from a wide variety of blockchain ecosystems in one place, connecting all major blockchains together using an advanced bridge technology they call "Peggy".

Sifchain currently provides routing from the Ethereum core network to the Cosmos ecosystem. This is achieved via Peggy from Ethereum to Sifchain and via IBC from Sifchain to other Cosmos-based blockchains. In the future, up to 25 major blockchains will be able to communicate seamlessly through the Sifchain interface.

Within SifDEX, all trading is possible through a pool with a native ROWAN token.

Sifchain is built using Cosmos SDK. In addition to connecting to the Cosmos hub via IBC, Sifchain already supports inter-network transactions for Ethereum ERC-20 tokens. In the future, 20-25 leading blockchains such as Bitcoin, Polkadot and EVM networks such as Avalanche and Polygon will also be connected via Sifchain.

### **Peggy & Peg-zones**

To provide cross-network support, Sifchain uses a concept called "Peggy" to create a tethered token model. This model is inspired by Cosmos' peg-zone model. "Peggy zone" is an account-based blockchain that connects "zones" within Cosmos to external networks such as Bitcoin or Ethereum. These "anchor zones" allow easy transfer of assets between Sifchain and the external network.

Sifchain uses the 2WP protocol, which allows the exchange of pegged tokens. For example, LTC to BTC currency will be exchanged as transactions of pegged versions of these tokens (cLTC and cBTC) on the Cosmos SDK blockchain. Sifchain users will trade pegged tokens in the Sifchain system.

The use of these tethered tokens also creates unique crypto-economic incentives for its participants. For example, Sifchain validators need only run a "Sifnode" (Sifchain network) and leave the cross-chain transaction work to peg zone validators. Each peg zone validator only needs to run a node for the peg zone blockchain and external blockchain (i.e. Bitcoin or Ethereum) and then can send assets to and from Sifchain via the IBC protocol.

Following the successful launch of the first Peggy implementation during the second half of 2021, the team began to approach the launch of Peggy 2.0, which will enable rapid deployment of connectivity to all EVM blockchains.

### **Connecting to IBC**

With an IBC, users can freely move their assets between Sifchain and any connected IBC blockchain.

With IBC and Peggy, Sifchain users can export approved Cosmos assets to Ethereum and transfer Ethereum assets across any IBC-enabled blockchain. This is a huge step towards Sifchain's goal of becoming the world's first omni-chain DEX.

### **Havernance**

Sifchain will use decentralized governance with SifDAO (Such a high-profile announcement was made back in 2021 on the wave of popularity of decentralized community governance).

SifCore (Sifchain's core team) is focused on developing SifDAO and fully delegating the management of all aspects of the protocol to its members.

For true sovereignty, Sifchain development must be self-funded and self-sustaining. Models such as Linux and Wikipedia are considered as examples of organizations that support the funding needed to continuously create critical open source resources. Details of SifDAO [here](https://sifchain.notion.site/SifDAO).

### **Security**

To ensure the security of the Sifchain ecosystem, the SifCore team will guide the design and implementation of each bridge. The SifCore team intends to provide the same security assurance to all bridges. As collateral, the plan is to use the native ROWAN token where appropriate, or a different token will be created solely for use by these peg zones, depending on the success of the rebalancing mechanism and market conditions.

### **$Rowan**

ROWAN is a native Sifchain token that has many uses in the ecosystem:

* ROWAN is a universal SifDEX liquidity pairing token. To enable exchange between tokens, each asset is paired with a ROWAN to create an LP pool. Thus, half of TVL DEX consists of ROWAN. As TVL expands, the demand for ROWAN grows along with it.
* ROWAN also plays a central role in Sifchain's crypto-economic security. Node validators must stack it with at least the equivalent TVL of DEX to ensure that the network is secure and the cost of malicious activity (slash) is not worth what the validator can get from fraud - according to the Tendermint consensus. Thus, additional TVL has a multiplicative effect on the market value of ROWAN. As TVL increases on DEX, half of the TVL must be derived from ROWAN. To ensure this, an amount at least equal to TVL must be bound by the validators. Thus, for every $1 of any external asset added to SifDEX, the system requires $3 of ROWAN.
* Node validators must bind ROWANs to compete for entry into the validator pool. Only the top 100 validators (ranked by the number of ROWANs sent to the stack) can receive block rewards. Block rewards are paid to ROWAN.
* Commissions for swap and transfer transactions are paid to ROWAN.
* Remuneration for providing liquidity is payable to ROWAN.
* ROWAN is a Sifchain havernance token - the more ROWAN a member has, the more weight their vote has in management decisions.

A more detailed description of ROWAN and its tokenomics can be found in [the whitepaper](https://assets.website-files.com/60ec70152eafa8dd30cb2fb5/6100250b18eca84d2952ea0e\_sif\_tokenomics\_latex.pdf).

Rowan was also discussed on the project's [Medium](https://medium.com/sifchain-finance/uses-for-rowan-the-polyvalent-token-for-omni-chain-decentralized-exchange-dex-3207e7f70f02) page.

Right now the picture looks like this:

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

C TVL had questions about the project as well. Suplai smoothly increased well above the claimed 1 billion tokens.

Nevertheless, take a look at [**the Q1 2022 results**](https://medium.com/sifchain-finance/sifchain-update-spring-summer-2022-ec7cda4896c8):

* Sif's Acsension liquidity mining program was launched;
* monetary trading policy (PMTP) was launched, with control of policy setting transferred to the SifDAO (essentially users);
* The formation of multiple DAO boards, including a validator delegation board, a token listing board, and a PMTP board;
* decentralization of the Sifchain frontend. Six different frontend providers now host Sifchain DEX frontends (including Akash Network);
* Hire and grow the Sifchain team by hiring key people in engineering, business and marketing;
* Sifchain's ambassador program was launched, with 11 ambassadors now participating;
* Adopted 35 proposals for the network, including software updates, community pool funding initiatives, expansion of the validator set, policy parameter updates and board elections;
* increasing participation in governance, with more than 60% of tokens consistently participating in DAO voting;
* first guide for validators on how to set up, delegate and update the network is released;
* The list of community-owned and managed tools has been expanded to include three different dashboards, a ROWAN tap and a blockchain explorer.

In addition, the engineering team performed the following backend work, which resulted in improved Sifchain performance:

* Sifchain.js;
* native integration testing;
* running the administrator module;
* new links with IBCs and partnerships with several IBC repeaters;
* transition of non-Sifchain RPC endpoints to external vendors;
* Implement best practices, including Agile practices and a support ticket system, to help improve the user experience with Sifchain;
* Finally, before the recent market crash, Sifchain was showing incredible growth rates. After the collapse, the performance declined.

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

Key areas that the team expects to focus on in the near future:

* margin trading;
* Omni-EVM;
* Sifchain DEX upgrade;
* engineering pipeline optimization and Sifchain Back-End;
* partnership, marketing and PR;
* team building;
* crypto-economy update.

Sifchain was the first bridge between ETH and Cosmos, and now the team sees its main mission as connecting Cosmos to the Ethereum Virtual Machine (EVM)-based blockchain world.

Over the past few months, the business development team has been working hard to build relationships with other EVM networks. Forty-five different EVM networks were analyzed to identify the most suitable ones. Today, the list of top contenders has been narrowed down to six possible options for the next EVM connection.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

At the same time, the engineering team is working on a critical Peggy 2.0 update. Peggy 2.0 code base is in the process of smart contract migration and load testing. The code has already passed 3 audits, with a fourth in progress.

Timeline: Peggy 2.0 is scheduled for release in Q3 2022.

By the end of this year the team also plans to perform the following works:

* Cosmos SDK update 0.45. This will provide proper order book support and AuthZ support, and allow CosmWasm to be installed.
* full CLP refactoring, which will make it easier for other external developers to work on core Sifcore functionality (and make it easier to create new products based on Sifchain);
* several DevOps pipeline optimizations and monitoring improvements;
* implementation of a data integrity, monitoring and optimization strategy.

Overall, the feeling is that the team is trying to correct the mistakes made.

**Links:**

* [Medium](https://medium.com/sifchain-finance)
* [Hitbook](https://docs.sifchain.finance/welcome-to-sifchain/start-here)
* [Website](https://sifchain.finance/)
* [Twitter](https://twitter.com/sifchain?s=20)
* [Discord](https://discord.gg/sifchain)
* [Telegram](https://t.me/sifchain)

