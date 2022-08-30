# Osmosis

![](https://img2.teletype.in/files/50/71/507178a3-549e-41ef-b704-83e2f9f50b51.png)

## Osmosis

Any blockchain ecosystem needs a good DEX, or decentralized exchange, in Russian. DEXs allow you to attract liquidity to the network, invest in projects, exchange tokens, and generally create a healthy economic model. And the most significant DEX with the greatest liquidity, trading volume and commissions in the Cosmos network is Osmosis.

### **What is Osmosis**

Osmosis is a high-tech AMM (automated market maker) protocol that allows you to run customised liquidity pools with a wide range of customisable parameters. Was founded in January 2021 by Sunny Aggarwal, Josh Lee, and Dev Ojha, all three characters are experienced blockchain developers having worked at Tendermint, where they developed the architecture for their DEX. Their company Osmosis Labs is currently responsible for developing and writing the code. The Osmosis team, inspired by projects such as Balancer and Uniswap, set out to provide users and developers with best-of-breed tools to create and customize AMMs that go far beyond the functionality of a simple "swapper".

### **How Osmosis works**

At the functional level, Osmosis is no different from other AMMs - the liquidity pools lock tokens through a smart contract that enables the operation of trades (swaps). Liquidity providers deposit their tokens in the liquidity pools, receiving for that LP tokens (liquidity pool tokens) and, accordingly, a share of commissions generated in the pool. The pricing model is also standard for most AMMs - the share of a token in a pool must remain constant. And why Osmosis is so remarkable and unique, we will tell you further.

### **Incentives to provide liquidity**

Osmosis uses two key mechanisms to provide the necessary liquidity - bonded liquidity gauge and exit fees.

#### **Share of provided liquidity**

This mechanism allows the formation of additional (in addition to the yield from the commissions received by the pool) remuneration to liquidity providers based on their share in the liquidity pool and on the time for which they lock their LP tokens of the pool. 45% of the daily issuance of OSMO tokens is allocated to this additional reward. The user has different options (or specific weight, in the original **gauges**) for choosing the time of locking their LP tokens. For example, in the ATOM/OSMO pool there are daily, weekly and monthly options - option 1, option 2 and option 3 respectively. The additional rewards are allocated between these options in a certain way. Some practical examples:

1\. John adds his assets to the pool, receives LP tokens, but does not want to lock them. Then his income will consist of commissions received by the pool, he will not receive any additional remuneration.

2\. John chooses option 1. Now his income consists of pool commissions and additional remuneration provided by option 1 (of course, proportionally to the share of LP tokens of John's total share of LP tokens receiving remuneration from option 1).

3\. John chooses option 3. Which means that now his income in addition to the pool commissions will now include additional rewards provided for option 1, option 2 and option 3. In short, the guy is taking life by the maxes.

It's worth considering that users have the option to split their LP tokens into different options, for example, send 50% to the first option and 50% to the second option.

Not all liquidity pools can receive additional rewards in OSMO tokens. OSMO stackers select by on-chain voting which pools will receive this reward and in what proportion it will be distributed among the various options. For this purpose, the stackers assign so-called "allocation points" to the pools and their options. For example, if a vote results in a total of 20 allocation points, 2 allocation points are given to option 1 of pool X, then that option will receive 2/20 = 10% of all additional rewards.

In addition to the "official" additional reward (45% of the daily OSMO token issue), any project or user can designate their own additional reward and set an option distribution for any particular pool.

The specific gravity of the provided liquidity serves another important function - it protects from "vampire attacks", because in order to get extra income users have to withdraw their funds, third-party DEXs have no opportunity to lure liquidity providers to their site with a short-term superprofitable offer.

You can read about all this in detail [here](https://medium.com/osmosis/osmosis-liquidity-mining-101-2fa58d0e9d4d).

#### **Fee for withdrawal from the liquidity pool**

The withdrawal fee is a small percentage of LP tokens that is charged from the liquidity provider when it sends a withdrawal request from the pool. At the same time, these tokens are burned.

#### **Liquidity pools customization**

Liquidity providers can experiment with different market making functions, this means that Osmosis doesn't have any particular mathematical function like most other AMMs, which is how liquidity pools work (for example Uniswap uses x\*y = k function, where x and y are respectively the number of one and second tokens in pools and k is a constant value, if you are completely new and don't understand anything, read how Uniswap works, it is the basic knowledge needed). Pool parameters, such as initial token density (share of certain token in pool), commission for swaps and TWAP calculation (Time-Weighted Average Price, something like average price for certain period of time) are chosen by pool creators. But all LP token holders of each pool have voting right for accepting any changes in the pool, proportionally to their LP share (and there are some ratios, which take into account how long users were liquidity providers in given pool and they get boosts to their votes depending on it).

Pool customization in the original vision of the Osmosis team should serve to find optimal pool parameters experimentally, moreover, such flexible settings should allow for new types of DeFi activities on Osmosis in the future, such as options, markets with dynamically changing commissions, etc., as well as help pools function better during periods of high volatility.

#### **Superfluid staking (superfluid staking)**

Multi-chain ecosystem has one big disadvantage - ensuring network security, which is achieved through stacking. In ETH 2.0, for example, security is provided by ether stackers, while in Polkadot ecosystem, security is provided by the relay channel, i.e. the polka itself. Both have a large number of coins locked, so security is at a high level. The Cosmos ecosystem, on the other hand, currently doesn't have its own "core" responsible for security, so there may be a problem, when on the one hand native tokens are needed for stacking and security, on the other hand native tokens are also needed to create liquidity. Osmosis has figured out how to kill two birds with one stone. Superfluid stacking is a mechanism that allows you to use some of the OSMO tokens in liquidity pools to simultaneously stack them.

A small practical example:

The user adds $1000 of liquidity to the ATOM/OSMO pool ($500 in ATOM tokens and $500 in OSMO tokens) and chooses a term to locate his tokens in the pool that guarantees him a certain APR (annual percentage rate - or annual interest rate). Let this APR = X. The user then has the option to add some of his OSMO tokens locked in the pool to the stack. How much of these tokens the user can add to the stacking is determined based on security considerations. Initially, this portion was equal to 50% of the OSMO tokens. Thus in our example the user will receive income X for providing liquidity to the pool and additional income Y for stacking OSMO tokens by the equivalent of $250 (50% of $500 in OSMO tokens added to the liquidity pool).It is worth noting that income Y is a dynamically changing value, as the ratio of ATOM/OSMO tokens constantly changes as their price changes relative to each other. These changes are accounted for by TWAP (time-weighted average price, or average price at a given time interval) oracle.

_Unofficial video in Russian, where in detail and clearly with practical examples is explained how superfluid steaming works_ [here](https://www.youtube.com/watch?v=JRBOUrrKa3s)

_Official video on how superfluid steaming works in English_ [here](https://www.youtube.com/watch?v=JRBOUrrKa3s)

Superfluid steaming allows liquidity providers to earn more rewards (liquidity pool rewards + steaming rewards) while improving Osmosis security (more OSMO in steaming).

### **Osmosis Frontier**

![](https://img4.teletype.in/files/b2/0d/b20d0dcc-cba5-46bc-9f82-cae60dc757c1.png)

There is a problem associated with the fact that there is no single efficient and secure multi-chain bridge. Using multiple bridges creates different wrapped token variations of the same asset (e.g. you want to transfer ether to Cosmos network using bridge X, you get xETH, if you use bridge Y you get yETH), this firstly dilutes liquidity, and secondly leads to confusion for ordinary users who see a bunch of different wrapped variations of the same token and don't know what to choose. Osmosis categorically doesn't want this to happen on their site, but waiting for the perfect bridge to appear isn't an acceptable option either. So they've launched a sort of experimental DEX - Osmosis Frontier - where any user can create their own pool with any asset. Such a wild west for any experiments (you may want to scam coins, play with pools settings, test bridges).

_Link to the site_ [here](https://frontier.osmosis.zone/). **!!! **_**Remember that here you can run into a scam, the pool can be empty and slippage will hit you sickle in the nuts**_**. **_**In short, be careful if you suddenly decide to experiment!**_

\*It's also worth noting that it was mentioned in passing in the official Osmosis medium that perhaps in the future Osmosis will have the ability to display all the different wrapped versions of the same asset as a single token.

\*\* A user has the ability to add some assets from the Ethereum network to Osmosis using the Axelar interface. As of early June 2022, these assets were limited to USDC, WBTC, WETH and DAI.

The official guide on how to do it is [here](https://medium.com/osmosis/bridging-ethereum-assets-to-osmosis-a-guide-to-the-axelar-interface-ac63c16cfb98).

\*\*\* In late June 2022, Osmosis, through the integration of the Kado app, enabled users to directly purchase axUSDC and OSMO tokens from their credit cards or bank accounts.

More information can be found [here](https://medium.com/osmosis/osmosis-integrates-kado-for-direct-fiat-on-ramping-to-the-dex-a1a49f2cf157).

### **Tokenomics**

![](https://telegra.ph/file/d05af7bfa92167816b705.png)

The $OSMO native token performs governance and utility functions.

First, it serves to provide economic security to Osmosis through stacking, and when the general security feature is launched, Osmosis is going to become part of the Cosmos hub. Second, $OSMO allows holders to participate in on-chain voting. Third, the token is used to pay commissions and provide additional remuneration to liquidity providers.

It is worth noting that the maximum supply is only 1 billion tokens and the deflationary model is achieved by reducing the issuance of new tokens by a third each year. The new tokens serve as rewards for staking, providing liquidity to pools and liquid mining, as well as incentives for ecosystem developers.

### **UPD**

Osmosis recently announced that they are going to work with Polkadot and ERC tokens, which will be possible thanks to their integration with Axelar and Moonbeam. You can read more about it [here](https://blockworks.co/osmosis-co-founder-doesnt-see-cosmos-and-polkadot-as-competitors/)
