# Agoric

### &#x20;<a href="#wpt1" id="wpt1"></a>

### &#x20;<a href="#0ugm" id="0ugm"></a>

![](https://img2.teletype.in/files/5e/35/5e356a10-0239-4840-92a1-303cd3c9a9d6.png)

Currently, most DeFi applications use an architecture where the Web2 frontend (the user interface) is written in JavaScript and the backend (the executable code), which is a set of smart contracts, is written in another specialized programming language. First, this requires the developers of smart-contracts to know a highly specialized language, and second, it complicates the creation of a robust framework linking the frontend and backend.

_\* In some networks, smart contracts are written in widely known languages, such as Rust in Near, but still most smart contracts are written in Solidity, so for most developers there is a threshold of entry into the crypto sphere, which is the need to learn a new language_

**Agoric is** a smart contract platform that allows developers to use Hardened JavaScript to write contracts. In this way Agoric intends to attract a large number of developers to DeFi, NFTs and Dapps, as JavaScript is one of the most common programming languages.

**Hardened JavaScript** is a variation of JavaScript that allows you to work with potentially unsafe code without the risk of being affected by bugs or malicious third parties. Simply put, it is an advanced sandbox for working with any kind of code, even insecure code. A more detailed technical description can be found [here](https://github.com/endojs/endo/blob/master/packages/ses/docs/guide.md)

The Agoric network was developed to reduce risk in decentralized financial systems, and the team aims to create a large-scale composite library of crypto-economic standards, similar to the libraries that have led to the explosive growth of JavaScript ecosystems (e.g., Node.js). Having such a library would give developers the ability to quickly create smart contracts from pre-built components (that's why the library is called composite). Agoric has also added improved determinism and asynchrony features to JavaScript, giving developers even more options for developing unique smart contracts.

#### **Agoric components** <a href="#vrot" id="vrot"></a>

![](https://telegra.ph/file/baca9a0852324c99c65e7.png)

#### **Endpoints (key elements of Agoric architecture)**

**Zoe,** a JavaScript framework for writing smart contracts, is responsible for secure code execution, and provides users and developers with protection against malicious third-party actions. Moreover, Zoe acts as a kind of escrow agent, i.e., the user has a guarantee that either the transaction is executed or he gets his assets back.

**Digital assets** are any tokens (including NFTs).

**Endo -** Performs the same function for Hardened JavaScript as Node.js does for JavaScript, namely running guest programs and interacting with the CapTP messaging protocol.

**Tendermint is** the engine on which all blockchains in the Cosmos ecosystem are currently built (\*more details in chapter one).

#### **Protocols** <a href="#jawq" id="jawq"></a>

**ERTP (Electronic Rights Transfer Protocol)** is an Agoric standard for creating and transferring digital assets. Using ERTP IP the user can create and use tokens (NFT too), and all these tokens have the same security properties and can be transmitted within the network.

**Cap TP (capability transport protocol)** - A protocol that allows objects on one computer to securely exchange messages with objects on another computer.

**IBC** - read about what this is in the first chapter.

#### **Agoric VM** <a href="#qb6q" id="qb6q"></a>

Agoric VM is an Agoric virtual machine that provides three main functions:

1\) Provides secure distributed environment for JavaScript code execution with the ability to use out-of-the-box modules. Safe use of modules and code reuse is provided by OCap.

_\* By using prefabricated modules we mean a feature called composability, you can read about it_ [_here_](https://en.wikipedia.org/wiki/Composability)_._

_Code reuse is the use of already prepared code to write new functions or application._

2\) Object-Capability model (OCap for short**) is** a security model used in secure computing systems. Agoric have extended this model to allow asynchronous programming between networks (\*I must_admit that we don't really know what this means ourselves_).

_Read more about OCap_ [_here_](https://en.wikipedia.org/wiki/Object-capability\_model)_._

3\) Exponential composability - This term refers to the use of off-the-shelf code, modules and packages to create new applications. To give you an idea of the scale - by the middle of 2021 more than 800k different packages have been downloaded from Node.js libraries, and the daily number of downloads exceeds 1 billion (\*data from official Agoric documentation). Only 3% of the code is written from scratch, the rest is ready-made and reusable. However, using someone else's code can carry security risks, and OCap protects users and developers from these risks by bringing all the benefits of using off-the-shelf code to the blockchain sphere.

#### **Tokenomics and economic model Agoric** <a href="#8kr2" id="8kr2"></a>

The economic model of Agoric is built on decentralized applications. Developers build and run their applications on the Agoric network, users can create their digital assets (tokens and NFTs), use the applications and make transactions while paying commissions. All in all, everything is pretty standard.

There are two native tokens on the Agoric network - IST (originally called RUN) and BLD.

**BLD** acts as a **Inter Protocol token IST** is a super-secured ecosystem stablecoin tied to USD. All commissions on the Agoric network are paid in IST, then those IST go to reward validators and partially to the protocol reserve fund. Agoric's long-term plans are to make IST the primary staple in the Cosmos ecosystem, as users will have the ability to mine IST against the native tokens of many IBC blockchains, such as ATOM, OSMO, SCRT and others. Which tokens can be used as collateral by voting will be determined by BLDer DAO members. Users will be charged a small fee for the IST mine, which the user will pay when repaying the loan. This commission, as well as transaction fees, will be distributed in the form of rewards to network validators and deductions to the protocol reserve fund.

IST is linked to the U.S. dollar through three types of arbitrage mechanism, which depend on the type of pledged asset. Parity stability mechanism is used if Stablecoins serve as collateral, Vaults - if assets approved by BLDer DAO serve as collateral, ISTstake - if BLD tokens in staking serve as collateral.

**Vaults** are smart contracts in which users lock their assets as collateral and mine IST. Each user creates their own individual vault for each type of pledged asset. Users are charged a fee for the mint (intended mainly to prevent spam), as well as an interest rate that the user pays to the protocol for the use of the debt (interest rate).

In addition, depending on the volatility of a particular pledged asset, an overdraft ratio is determined for it (e.g., to withdraw 100 IST against Coin A, the user would have to deposit the equivalent of 150 USD in Coin A, which means that the overdraft ratio for Coin A is 1.5. And there will be a different coefficient for coin B, set to reflect the volatility of that coin). The over-collateralisation ratio, maximum loan amount, fees and liquidation penalty for each pledged asset are set by the BLDer DAO.

To reduce liquidation risks, the user can bind ISTstake to the treasury and then when the liquidation threshold is passed, IST tokens will be automatically added to increase the collateral. About ISTstake in the next paragraph.

**ISTstake is** an alternative way of minting IST available to BLD stackers. Users who have minted their BLD tokens to validators can mint some of these tokens as collateral and mint IST. These pledged tokens continue to earn users staking rewards, but they cannot be withdrawn from staking until the debt is paid off and the mint fees are paid. The repayment of the debt is done by deducting the staking rewards in payment of the debt. ISTstake has no liquidation mechanism (i.e. BLD collateral cannot be liquidated). The maximum amount of possible debt and the limit per min, as well as the commissions are set by the BLDer DAO.

**Parity stability module** - gives users the ability to mint IST against popular stablecoins through a special smart contract without creating vaults. This method of minting is subject to the lowest commissions and allows to quickly take advantage of arbitrage opportunities in case IST deviates from the nominal value of $1.

**Kinetic,** the native AMM of the Agoric network, provides exchange and trade of assets in the network and is also responsible for executing liquidation processes.

**The Reserve Pool** plays two key roles: it provides Kinetic with liquidity for liquidations and ensures repayment of debt positions from its reserves in case of force majeure. The Reserve Pool holds various crypto-assets for these purposes.

To summarize, IST is designed to play a key role in the development of DeFi in the Agoric network, binding IST to USD rate is protected by the following mechanisms:

* Overcollateralization of collateral assets;
* Liquidation, in case the collateral ratio falls below the threshold value;
* Reserve Fund;
* Commissions payable at the time of the mines;
* The possibility of using ISTstake as insurance.

It should also be noted that during the preparation of the material some questions arose for which we could not find an exact answer. We have greatly reduced the technical description of the project due to our incompetence in this matter, however, if you have a good understanding of JavaScript, you can read the entire technical documentation on the official site. The project has really Napoleonic plans, and only time will tell whether they will succeed.

**Where to see, what to read**

Official website (with links to all documentation and resources) [here](https://agoric.com/blog/)

Whitepaper [here](https://agoric.com/wp-content/uploads/2021/12/Agoric-White-Paper-v1.0-1.pdf).

Whitepaper Inter Protocol [here](https://agoric.com/wp-content/uploads/2022/05/Draft-Inter-Protocol-Whitepaper-v0.9-1.pdf).

Inter Protocol mechanics (video) [here](https://www.youtube.com/watch?v=0bd9zsNXDpY)

Official blog [here](https://agoric.com/blog/)

The Agoric group is on the trolley [here](https://t.me/agoricrussian). token and serves to secure the network through staking. That is, any holder of these tokens can deposit them with validators and receive staking rewards for doing so, as well as participate in BLDer DAO (Agoric's DAO network name) voting. Here again, everything is standard, but this token also has another function, which will be described below.

Distribution of tokens is shown on the diagram

![](https://img4.teletype.in/files/34/75/3475426d-f36e-48fe-a7fa-791e8f686724.png)

At the time of writing this chapter (late July 2022), the token was not traded on any exchange, but users had the option to add their tokens to the stack.

**Inter Protocol token IST** is a super-secured ecosystem stablecoin tied to USD. All commissions on the Agoric network are paid in IST, then those IST go to reward validators and partially to the protocol reserve fund. Agoric's long-term plans are to make IST the primary staple in the Cosmos ecosystem, as users will have the ability to mine IST against the native tokens of many IBC blockchains, such as ATOM, OSMO, SCRT and others. Which tokens can be used as collateral by voting will be determined by BLDer DAO members. Users will be charged a small fee for the IST mine, which the user will pay when repaying the loan. This commission, as well as transaction fees, will be distributed in the form of rewards to network validators and deductions to the protocol reserve fund.

IST is linked to the U.S. dollar through three types of arbitrage mechanism, which depend on the type of pledged asset. Parity stability mechanism is used if Stablecoins serve as collateral, Vaults - if assets approved by BLDer DAO serve as collateral, ISTstake - if BLD tokens in staking serve as collateral.

**Vaults** are smart contracts in which users lock their assets as collateral and mine IST. Each user creates their own individual vault for each type of pledged asset. Users are charged a fee for the mint (intended mainly to prevent spam), as well as an interest rate that the user pays to the protocol for the use of the debt (interest rate).

In addition, depending on the volatility of a particular pledged asset, an overdraft ratio is determined for it (e.g., to withdraw 100 IST against Coin A, the user would have to deposit the equivalent of 150 USD in Coin A, which means that the overdraft ratio for Coin A is 1.5. And there will be a different coefficient for coin B, set to reflect the volatility of that coin). The over-collateralisation ratio, maximum loan amount, fees and liquidation penalty for each pledged asset are set by the BLDer DAO.

To reduce liquidation risks, the user can bind ISTstake to the treasury and then when the liquidation threshold is passed, IST tokens will be automatically added to increase the collateral. About ISTstake in the next paragraph.

**ISTstake is** an alternative way of minting IST available to BLD stackers. Users who have minted their BLD tokens to validators can mint some of these tokens as collateral and mint IST. These pledged tokens continue to earn users staking rewards, but they cannot be withdrawn from staking until the debt is paid off and the mint fees are paid. The repayment of the debt is done by deducting the staking rewards in payment of the debt. ISTstake has no liquidation mechanism (i.e. BLD collateral cannot be liquidated). The maximum amount of possible debt and the limit per min, as well as the commissions are set by the BLDer DAO.

**Parity stability module** - gives users the ability to mint IST against popular stablecoins through a special smart contract without creating vaults. This method of minting is subject to the lowest commissions and allows to quickly take advantage of arbitrage opportunities in case IST deviates from the nominal value of $1.

**Kinetic,** the native AMM of the Agoric network, provides exchange and trade of assets in the network and is also responsible for executing liquidation processes.

**The Reserve Pool** plays two key roles: it provides Kinetic with liquidity for liquidations and ensures repayment of debt positions from its reserves in case of force majeure. The Reserve Pool holds various crypto-assets for these purposes.

To summarize, IST is designed to play a key role in the development of DeFi in the Agoric network, binding IST to USD rate is protected by the following mechanisms:

* Overcollateralization of collateral assets;
* Liquidation, in case the collateral ratio falls below the threshold value;
* Reserve Fund;
* Commissions payable at the time of the mines;
* The possibility of using ISTstake as insurance.

It should also be noted that during the preparation of the material some questions arose for which we could not find an exact answer. We have greatly reduced the technical description of the project due to our incompetence in this matter, however, if you have a good understanding of JavaScript, you can read the entire technical documentation on the official site. The project has really Napoleonic plans, and only time will tell whether they will succeed.

**Where to see, what to read**

Official website (with links to all documentation and resources) [here](https://agoric.com/blog/)

Whitepaper [here](https://agoric.com/wp-content/uploads/2021/12/Agoric-White-Paper-v1.0-1.pdf).

Whitepaper Inter Protocol [here](https://agoric.com/wp-content/uploads/2022/05/Draft-Inter-Protocol-Whitepaper-v0.9-1.pdf).

Inter Protocol mechanics (video) [here](https://www.youtube.com/watch?v=0bd9zsNXDpY)

Official blog [here](https://agoric.com/blog/)

The Agoric group is on the trolley [here](https://t.me/agoricrussian).
