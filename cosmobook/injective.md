# Injective

![](https://img2.teletype.in/files/1a/f2/1af2d2b9-0315-405d-b378-4560e891fc5a.png)

## Injective

**Injective** is a DeFi L1 blockchain designed for decentralized exchange of next-generation derivatives. Injective Chain has a decentralized DEX protocol running on the order book model and an ERC-20 token bridge to Ethereum.

Every component of Injective has been designed to be fully secure, censor-resistant, and publicly verifiable.

On Injective, developers can create their own derivatives and trading markets.

### Team <a href="#vwfx" id="vwfx"></a>

Behind the creation and development of Injective is Injective Labs.

Injective Labs is not only responsible for the repeater interface that connects users to the Injective network, but also provides backend support for the protocol.

The Injective team has a web page dedicated exclusively to their labs. Visit it [here](https://injectivelabs.org/).

**The future of finance for mass-adoption Injective outlined in the following talking points:**

* Optimization for DeFi. Interchangeable primitives for creating basic DApps.
* Interoperability. Seamless communication between sovereign blockchains for a user-friendly experience.
* High level of security and fast reliable transactions with instant closure.
* Intuitive interface for the developer. Flexible and expressive development environments based on Rust and Golang.
* Horizontal scalability. Instant data transfer over parallel networks for dynamic scalability.
* Low fees for the use of various financial products.
* Eco-friendliness. Carbon footprint reduced by 99% thanks to the Injective consensus mechanism.
* Full customizability/customizability. Ability to quickly change any product usage parameter to suit your scenario.

### **What Injective is trying to do to attract its customers:**

* Injective is optimized to work with decentralized finance and provides off-the-shelf financial primitives, such as a fully decentralized order book, allowing developers to build their dApps easily and easily. For example, apps can use the order book to run exchanges, prediction markets, and other similar products.
* Compatibility: Injective is initially compatible with a number of blockchain networks and also supports IBC. Injective enables cross-network transactions between Ethereum, Moonbeam and IBC-enabled networks such as CosmosHub.
* Creating dApps using CosmWasm: Injective supports CosmWasm, a new smart contract platform built for the Cosmos ecosystem. This means that developers can easily run their own apps based on out-of-the-box smart contracts on Injective. Smart contracts running on other networks that support CosmWasm can easily be ported to Injective.
* Running tokens compatible with Ethereum and IBC: Since Injective supports cross-network transactions with Ethereum and all IBC networks, tokens running on Injective can run on different networks by default.
* Intuitive developer interface: Ability to use flexible and expressive development environments based on Rust and Golang.
* 25.05.2022 Injective Labs [announced](https://blog.injective.com/defi-injective-adds-solana-avalanche-polygon-interoperability-with-wormhole-integration/) the integration of Wormhole, a messaging protocol, into the Injective ecosystem. The integration will allow decentralized applications (dApps) in the Injective ecosystem to connect with Algorand, Avalanche, BNB Chain, Fantom, Oasis, Polygon and Solana blockchains.
* \- From June 3rd, 2022 you can start transferring assets from Polkadot using [**Injective Bridge** ](https://hub.injective.network/bridge)(thanks to integration with Moonbeam and Axelar) (details [here](https://blog.injective.com/injective-integrates-polkadot-assets-to-expand-the-cross-chain-cosmos-universe/))

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

The Injective protocol consists of several key components.

**Injective Chain** is a decentralized exchange (DEX) protocol built on top of Cosmos that also allows Ethereum tokens to be transmitted and traded. This network is designed to address the scaling and bandwidth challenges faced by many Tier 1 blockchains, while allowing developers to use Ethereum's familiar development toolkits.

### **Traders can access multiple modules within Injective Chain DEX:**

**Auction** - allows token holders to stake baskets of tokens that have been accumulated through fees from exchange trading. INJ tokens (native network token) paid by the highest bidder are burned, or eliminated from circulation, according to the protocol algorithm.

As decided by the Injective community as part of the canonical mainnet rollout, each week 60% of the fees charged by the protocol for token swaps will go through a buy-back and burnout process that is managed by an auction run by the community. The auction works as follows:

* The commissions collected by the protocol are included in the auction (for example: suppose there is a basket of $100. $50 in ETH and $50 in WBTC).
* Users can **bid using only INJ** (let's say user A bids $90 in INJ and user B bids $95 in INJ).
* User B will win the bet with $95. In fact, User B can own a $100 asset basket for only $95, potentially opening up arbitrage opportunities.
* The $95 paid to INJ will be burned immediately.
* After that, a new auction begins

**Exchange** - helps traders create and trade in new spot and derivatives markets. Injective Exchange is an exchange with an order book model based on the popular 0x protocol. The Injective team has opened the source code of all exchange components (user interface, smart contract set, order book management system), aiming to make the platform transparent and accessible.

Injective Exchange also uses a Trade Execution Coordinator (TEC). The TEC creates a delay so that new orders cannot be placed before old orders, thus attempting to address the problem of advanced information received by some market makers or bots.\
**Insurance** - facilitates insurers that support derivatives markets that are listed on the exchange.\
**Oracle** - obtains real price data (e.g., traditional stock market data) used to set asset prices on the INJ exchange. Basically, it is an oracle system.\
**Peggy** - connects the Injective protocol with the Ethereum blockchain, allowing ERC-20 tokens to be traded.

### Injective architecture <a href="#iiur" id="iiur"></a>

Architecturally, there are two main services that are provided to the user:

1. **Injective Chain node** (network API) - details [here ](https://api.injective.exchange/#chain-api).

There are currently three nodes in Mainnet that can be connected to, which are located in the US and Tokyo:

U.S. Sentry Node: sentry0.injective.network

U.S. Sentry Node: sentry1.injective.network

Tokyo Sentry Node: sentry3.injective.network

2\. **Injective Exchange API** - details [here](https://api.injective.exchange/#exchange-api)[.](https://api.injective.exchange/#chain-api)

The Exchange API is read-only, while the Chain API is write-only, and includes a limited set of read-only API requests. Chain API reads a blockchain state request directly from a node, as opposed to Exchange API, which recovers state from events sent by the network.

At a high level, endpoint trading applications and Injective products use the Exchange API to read data and the Chain API to write data to the blockchain. While it is possible to develop trading applications using only Chain API, Exchange API includes more methods, streaming support, gRPC, and allows historical data (Chain API queries the state of the blockchain, which does not include historical records).

### How does it work? <a href="#rpea" id="rpea"></a>

Let's take a look at the life cycle of a trade to understand the processes going on under the hood of Injective, which is as follows:

1. First, traders cryptographically sign a transaction containing one or more order messages (e.g.`,MsgBatchCreateDerivativeLimitOrders`, `MsgCreateSpotMarketOrder`, `MsgCancelDerivativeLimitOrder`, etc.).
2. The transaction is then broadcast to an Injective network node.
3. The transaction is then added to mempool and included in the block. More information about this process can be found [here](https://docs.cosmos.network/master/basics/tx-lifecycle.html).
4. A handler is started for each relevant message. While the handler is running, messages for cancellation and liquidation of an order are processed immediately, while messages for creation of an order are added to the queue.
5. At the end of the block, the batch auction process begins for matching orders.

* First, market orders placed in the queue are executed against the remaining order book (which does NOT include new orders from the current block) and are cleared at a single clearing price.
* Second, queued limit orders are matched against each other and against the rest of the order book to avoid repetition and overlap. Limit orders created in this block are cleared at a single clearing price, while other limit orders created in previous blocks are cleared at a price equal to or better than their limit order price.

6\. Funds are settled accordingly, with positions created for derivative transactions and assets exchanged for spot trades.

7\. Events containing trade and settlement information are generated by the network.

8\. The server side of the Injective Exchange API indexes events and sends updates to all subscribed traders.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Transaction processing in Injective Chain is beneficial to the end user, as accessing the network through an exchange's DApp alleviates the burden of gas charges. Since exchanges broadcast subscribed messages to Injective Chain nodes rather than traders, all fees associated with network interactions are covered by the exchange DApp, resulting in zero gas fees for traders. This enables users to trade on the exchange without having INJ in their account. This approach is a significant improvement to the UX. Moreover, Injective allocates a $100,000 rebate pool to cover gas charges for users who transfer funds from Ethereum for the first time.

### Differences from CEX <a href="#zuea" id="zuea"></a>

Now we can highlight the main differences from CEX:

* All information is publicly available, including things like unused Stop/Take orders or pending orders in mempool.
* The data stored on the network is minimal for performance reasons and reflects only the current state, the relays provide additional historical data as well as a user interface for traders via the server side of the Injective Exchange API.
* Usually DEX suffers from problems related to frontrunning, but by quickly generating and validating FBA (Frequent Batch Auction) blocks, Injective partially solves this problem (frontrunning is still possible, but more difficult to implement).
* The order of execution is different. Any new exchange action is a new transaction and is not executed immediately. Instead, it is added to the queue (mempool) and executed after the block is committed. During a block commit, all included transactions occur almost instantaneously. First, the code that is inside the handler is executed according to the transaction sequence that is defined by the miner. This is not a problem, as the sequence does not affect the matched prices due to FBA, and thus users are guaranteed fair execution of their requests.

### **A little bit about Frequent Batch Auction (FBA) or Frequent Batch Auction.**

The goal is to be even more able to prevent any [Front-Running](https://www.investopedia.com/terms/f/frontrunning.asp) in a decentralized environment. Most DEX suffers from this because all information is public, and traders can collude with miners or pay high gas fees, allowing their requests to be processed before anyone else**(putting their price before yours**).

Read more about this phenomenon, which is called MEV (miner extractable value) [here](https://cyberacademy.dev/blog/20-temnyy-les-ethereum-chto-takoe-mev).

Injective mitigates this with fast block generation times combined with frequent batch auctioning:

In any given block:

1. One single clearing price is calculated for all market orders and they are executed. For an example of matching market orders using FBA [, see here](https://api.injective.exchange/#examples-market-order-matching).
2. Limit orders are combined with the rest of the order portfolio and the orders are matched as long as the negative spread is maintained. All limit orders are matched at the same clearing price. For an example of how limit orders can be matched using FBA [, see here](https://api.injective.exchange/#examples-limit-order-matching).

**Trading fees and gas**\
If you trade on existing centralized exchanges, you are familiar with the concept of trading fees. Traders are charged a fee for each successful trade. However, on DEX there are additional gas charges that need to be paid by the network. The gas fee when trading on Injective is minimal. If you are a trader using DEX UI, you don't have to worry about gas costs because the relay will pay them for you. But in return, you will pay the full trade fee.\
If you're using API, you'll have to pay the cost of gas.\
Currently, the cost of gas is very low. 20K transactions will cost about 1 INJ ($1.72 on 08.08.2022).\
You can set recipient\_fee to any address of your own wallet, since you are essentially your own relay, which saves you about 40% of all fees.

#### Exchanges based on Injective <a href="#jfgl" id="jfgl"></a>

There are currently six exchanges built on Injective Chain: Picasso Exchange, MarsX, Unlimited Exchange, Lunatics Exchange, Inj Dojo Exchange and Injective Pro, which is provided by the core team.

All of these exchanges are connected to the same markets through a common order book, but differ in how they provide access to the user. For example, unlike the Injective Pro relay, the Picasso exchange offers a swap mechanism for spot markets with a user interface similar to AMM DEXs. And MarsX gives access to two of the perp markets, while other exchanges give access to all four. Essentially, these exchanges only offer different UX and UI, but, the more players, the more decentralization.

### Injective Hub <a href="#wmxy" id="wmxy"></a>

**Injective Hub** is a dashboard that gives users the ability to make the most of the Injective protocol (how-to guide [here](https://blog.injective.com/injective-hub-guide/)).

Through Injective Hub, you can place an INJ (native network token) to become a network validator, or delegate your tokens to other validators.

The Injective Hub also acts as a platform for making suggestions and votes on further development of Injective. For example, here INJ holders vote on the inclusion of new trading pairs, amendments to management procedures, additions or changes to existing platform functionality.\
The wallet page displays important information about your assets. Here you can view your balance, delegate, re-delegate and brand awards.

On the Injective Bridge page, users can transfer assets between Injective Chain and Ethereum (Cosmos Hub, Osmosis, Persistence, Evmos, Axelar, Moonbeam).

### $INJ <a href="#8bds" id="8bds"></a>

**INJ** is a native Injective Protocol token and is used for governance, auctioning (was described above), providing liquidity and stacking. As the Injective ecosystem continues to evolve, new projects will promote token burning (has been described in auctions) and reduce the supply of INJ over time. Options for using INJ include, but are not limited to: protocol management, payment of exchange fees, derivatives provisioning, liquidity mining, and stacking.

**Utility Token:**\
**1. Proof of Stake security.** INJ's preliminary initial offering has been set at 100,000,000 tokens and will increase over time through block generation rewards.

The INJ inflation target will provisionally be 7% during the genesis phase and will decrease to 2% over time. Gradually, the total supply of INJ may fall below the initial supply due to the deflationary mechanism described below in the section "Exchange fee accrual".

**2. Governance.** The INJ token also serves as the primary governance token for Injective Chain.

INJ is used to manage all aspects of the network, including:

\- Parameters of the "Auction" module.\
\- Custom offers and parameters of the Exchange module.\
\- Parameters of the Insurance module.\
\- Oracle's User Bids module.\
\- Parameters of the Peggy module.\
\- Software Updates.\
\- Cosmos-SDK module parameters for the auth, bank, crisis, distribution, gov, mint, slashing and staking modules .\
Full information about the management process can be found [here](https://blog.injective.com/injective-governance-proposal-procedure/).

**3. Incentives for repeaters.**\
The exchange protocol implements a common minimum trading commission of 0.1% for those who place orders and 0.2% for those who accept these orders. As an incentive mechanism for repeaters to use the exchange protocol, repeaters who send orders to the general order book are rewarded 40% of the trade commission on the orders they send.

**4. Accrual of the value of the exchange fee.**\
The remaining 60% of the exchange fee is subject to repurchase at auction and further incineration (again, this was described above). Details [here](https://docs.injective.network/modules/auction/).

**5. Collateralization of derivative financial instruments.**\
INJ will be used as an alternative to Stablecoins as margin and collateral for Injective derivatives markets. In some derivatives markets, INJ may also be used as collateral or an insurance pool where participants can earn interest on their blocked tokens.

The weekly supply burn creates a deflationary effect and to some extent compensates for the increase in supply caused by token minting. To be more precise, a 5% annual inflation of 13 million INJ equals 650,000 INJ minted over the year, while the total minted over eight weeks is 204,000, which adds up to about 1,326,000 INJ minted over the year, which is 1.325% of the total supply.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### Injective update <a href="#t2zg" id="t2zg"></a>

**On July 5, 2022**, [Injective](https://blog.injective.com/mainnet-chain-upgrade-smart-contracts-are-now-live-on-injective/) underwent a major update:\
1\. Injective has undergone a network update in mainnet that includes support for CosmWasm smart contracts, inter-net accounts, binary options, negative maker commissions, and more.\
2\. Injective's unique implementation of CosmWasm allows smart contracts to be executed manually by external users as well as automatically on each block.\
3\. negative market maker commissions will provide more benefits to market makers, while stimulating increased liquidity in the network.\
4\. network update launched a new binary of Injective Chain application.

Smart contracts are now ready to be implemented on Injective with the Injective Canonical 1006-rc1 (or Injective CosmWasm Mainnet Upgrade).

In addition to support for smart contracts with CosmWasm, the update includes:

* Supporting negative creation fees.
* Supporting the binary options markets.
* Support for inter-network accounts via IBC v3.
* And much more.

To _learn more about management offers, click_ [_here_](https://blog.injective.com/injective-governance-proposal-procedure/).

### Support for smart contracts (CosmWasm) <a href="#qj9p" id="qj9p"></a>

Injective now supports CosmWasm smart contracts.

This new implementation of CosmWasm will allow any developer to create a variety of applications on Injective while using out-of-the-box modules. The main example is the Injective order book module, which allows developers to use a decentralized order book "out of the box" to create dApps such as exchanges, prediction markets, lending protocols, and more.

The CosmWasm implementation in Injective is uniquely different from any other CosmWasm layer in the Cosmos ecosystem. This update to Injective mainnet will allow smart contracts to execute _automatically_ on every block.

Smart contracts traditionally require an external agent, such as a user, to invoke the contract and run the logic associated with the contract.

However, Injective's implementation of CosmWasm will also allow smart contracts to run on each blockchain _independently_, without an external agent, giving developers the ability to create truly decentralized, trustless applications.

CosmWasm will allow developers to create more complex functions and applications on Injective. In addition, the ability to automatically execute smart contracts is a paradigm shift in blockchain interaction methodology.

Injective will now be **the only** blockchain that allows to independently execute smart contract logic. This will attract more developers, users, and community members, leading to the growth of the Injective ecosystem as a whole.

### Negative fees from makers <a href="#k8wg" id="k8wg"></a>

Injective will now support negative maker commissions on approved markets in all exchange dApps built on Injective.

Market makers providing liquidity in certain spot or open-ended markets with negative mark-to-market commissions will receive a percentage of the total amount traded as compensation.

Community members can submit proposals to management on which markets they would like to introduce negative commissions for market makers, and once approved by management, the proposal will be implemented.

### Support Binary Options <a href="#ypq2" id="ypq2"></a>

Binary options markets will now be supported online.

Similar to open-ended asset markets, binary options are another type of financial derivatives. However, binary options are financial contracts in which a payout occurs depending on one of two outcomes of the underlying asset or issue.

For example, binary options can be a contract on the outcome of an election: Will candidate A become president? The given options are binary - candidate A will either become the new president or not - and the correct answer will generate profits in the binary options market.

[Frontrunner](https://getfrontrunner.com/), for example, can use binary options to run its fully decentralized sports betting platform.

### Links <a href="#brfn" id="brfn"></a>

[Website](https://injectiveprotocol.com/)

[Telegram](https://t.me/joininjective)

[Discord](https://discord.gg/injective)

[Blog](https://blog.injective.com/)

[Twitter](https://www.twitter.com/@InjectiveLabs)

[Learn](https://blog.injective.com/tag/learn/)

[Youtube](https://www.youtube.com/channel/UCN99m0dicoMjNmJV9mxioqQ)

[Facebook](https://www.facebook.com/injectiveprotocol)

[LinkedIn](https://www.linkedin.com/company/injective-protocol/)

[Reddit](https://www.reddit.com/r/injective/)

[Instagram](https://www.instagram.com/injectivelabs/)

[Weibo](https://weibo.com/7452104340/profile?rightmod=1\&wvr=6\&mod=personnumber\&is\_all=1\&ssl\_rnd=1612829152.4355)

[Orbit Newsletter](http://eepurl.com/hcrjwP)
