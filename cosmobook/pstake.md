# pSTAKE

![](https://img3.teletype.in/files/e5/d0/e5d0156c-0bdf-44ed-a383-f281830802c8.png)

## pSTAKE

pSTAKE is a liquid-stacking protocol that allows users to benefit from additional PoS asset stacking. When a user stacks their PoS tokens on the pSTAKE platform, their wrapped counterparts, known as stkAssets or stkTokens (e.g., an Atom token would be represented as stkAtom) are minted. In doing so, the original tokens are sent by pSTAKE to reliable validators; each supported network has its own set of such validators. In this way, the user can earn rewards for staking, while directing the wrapped tokens to various DeFi activities, thereby leveraging their assets and gaining additional profit compared to simple staking.

Currently, all stkTokens are ERC-20 tokens and operate on the ether network, but in the long run pSTAKE is going to evolve into a multichain protocol and add support for many other networks.

Behind the creation of pSTAKE is the [Persistence](https://persistence.one/) team, which is an early contributor to the space ecosystem and focuses on the development of PoS in general, and liquid-stacking in particular. They also own AUDIT.one, which validates over 20 networks and has over $150 million in assets under management.

Today, ATOM, XPRT (Persistence Network native token), ETH and BNB can be zapped through the pSTAKE platform.

### **Liquid staking ATOM**

\*Stacking Persistence and other native tokens from the Cosmos ecosystem that will be added in the future follow the same model

![](https://coin98.s3.amazonaws.com/69DFSFVXX2)

The user deposits their ATOM into the pSTAKE pad (the minimum number of ATOMs to deposit is five), and receives wrapped ERC-20 pATOM tokens in a 1:1 ratio. pATOM can be unwrapped into ATOM at any point in time, a bridge called pBridge is responsible for issuing and burning pTOKEN such as pATOM, discussed in more detail below.

The user can then send their pATOMs to the stack and in doing so they receive ERC-20 stkATOM tokens that they can use for various DeFi activities. For example, to get rewards for providing liquidity in ETH/stkATOM pool on SushiSwap (link to pool [here](https://app.sushi.com/add/ETH/0x44017598f2AF1bD733F9D87b5017b4E7c1B28DDE)).

The user is also rewarded for staking pATOM (as if he were just staking ATOM tokens), currently the APR for staking pATOM is 13.5% APR and for staking pXRPT it is 24.63% APR. Rewards to the user are accrued in pTOKENS, the period of anstaking is 21 days (set by the ATOM network havernance). APR is not a static value and can automatically change, for example, if the ATOM network stops functioning for some time, pSTAKE smart contracts will make the necessary adjustments to accrue rewards to stakers.

### **pBridge**

pBridge is a bridge that enables value transfer between different networks such as Cosmos and Ethereum.

pBridge is responsible for minting/burning, stacking/anstaking, reward transfer and other actions that the user performs on the pSTAKE platform when delegating non-native Ethereum assets. That is, pBridge ensures that transactions that occur on the platform side (i.e., on the Ethereum network) are also instantly executed on the protocol side of the native network (in our example, the Cosmos network).

### **Validators**

pSTAKE sends ATOM tokens in equal shares to a validator from its set, which includes only reliable and trusted validators. This set is subject to change, but initially it includes: Stake.fish, Chorus One, Figment, Cosmostation, Everstake, SG-1, AUDIT.one

The pBridge validator set is also defined by the pSTAKE command, initially this set includes: Stake.fish, Chorus One, Figment, Cosmostation, Everstake, AUDIT.one

As of the end of July 2022, ATOM's liquid staking, in addition to pSTAKE, offered only one other decentralized protocol - StaFi. The comparative characteristics of these two platforms are shown in the figure below.

![](https://img1.teletype.in/files/c5/64/c564662d-5292-44bf-99e1-41b2ab58a5a8.png)

You can read about how to zip the ATOM via the pSTAKE pad [here](https://docs.pstake.finance/How%20to%20connect%20a%20blockchain%20wallet/)

### **Liquid staking BNB**

\*The BNB network consists of two components:

* BNB Beacon Chain (BC), formerly called Binance Chain, is a network used on havernance (e.g. voting) and staking.
* BNB Smart Chain (BSC), formerly called Binance Smart Chain, is an EVM compliant network that hosts consensus layers and hubs to connect with other networks.

The module responsible for staking in the BSC network is located on BC.

BNB token holders can stack their coins via pSTAKE and receive wrapped stkBNB tokens. At the same time, the value of stkBNB's swiped tokens increases relative to BNB's value as they "accumulate" staking rewards. As a matter of fact, it is exactly the same model as Compound uses (more details about this model you can find [here](https://compound.finance/docs/ctokens), or if you want to get really deep, you can calculate stkBNB to BNB value ratio [here](https://www.mathcha.io/editor/2X2VVI3mi5DtPxG5ZHLGypBFpEBXWQHlqM6YY)).

Staked BNB tokens are sent to the StakePool contract. Every day at 23.00 UTC the bot in the BC network launches a staking transaction that aggregates all BNB tokens received during the day on the StakePool contract and sends them to the approved pSTAKE validator set.

If user wants to take his BNB tokens from staking, his stkBNB tokens will be burned, the current stkBNB/BNB exchange rate will be automatically calculated, which takes into account the rewards received by user during the staking period, but the anstaking process takes 15 days. If the user wants to get BNB tokens immediately, he can exchange his stkBNB to BNB on decentralized exchanges.

It's worth noting that a small percentage of the staking rewards go to the validators and also go as a commission to the protocol. These commissions will be sent by pSTAKE to the ecosystem, but at the moment the protocol fee is 0% (the website says that the zero protocol fee is only valid for the first three months of stacking).

### **How pSTAKE generates a set of validators**

Assets of pSTAKE users are placed only with reliable and trusted validators, and they try to choose the ones that charge the lowest commission percentage. When selecting a validator, the focus is on the following two factors:

**1. APR** (annual percentage rate) provided by the validator. APR is influenced by validator's commissions (the less the better for the user) and the number of coins that the validator is charging (in the official documentation it is written that the LESS stak the validator has, the more likely the APR will be higher).

**2. security**. BNB network does not apply slashing to delegators (stackers), so they cannot lose the tokens they already have, but if a penalty is applied to a validator, users may get less rewards. Therefore, when selecting a validator in your set, pSTAKE looks at how often the validator has been penalized in the last year, as well as its uptime in the last six months.

\*What slashing is and what the term jail means you can read in the "Slashing " section in the first part of Hitchhiking through Cosmos.

Based on these two criteria, pSTAKE assigns a rating to all validators, and the top 10 are added to their active set.

The process of BNB staking and anstaking is very simple and straightforward and is done via the pSTAKE platform; [here](https://blog.pstake.finance/2022/08/07/stkbnb-user-guide-bnb-liquid-staking-tutorial/) you can see step-by-step instructions.

### **Using stkBNB in DeFi protocols**

At the moment users have the following options to use their stkBNB:

* Providing liquidity in the stkBNB/BNB pool at Pancakeswap (link to the pool [here](https://pancakeswap.finance/add/BNB/0xc2E9d07F66A89c44062459A47a0D2Dc038E4fb16)) and receiving trading commissions, as well as the opportunity to use LP tokens of the pool for staking and farming rewards in the form of CAKE tokens;
* Farming with leverage in the stkBNB/BUSD pool on Alpaca.

Also on Pancakeswap, the user can instantly exchange their stkBNB to BNB.

pSTAKE pays special attention to the security of the smart contracts responsible for BNB steering. A full audit of these smart contracts was conducted by Halborn (report [here](https://pancakeswap.finance/add/BNB/0xc2E9d07F66A89c44062459A47a0D2Dc038E4fb16)), Peckshield (report [here](https://github.com/persistenceOne/pStake-auditReports/blob/main/stkBNB/pSTAKE\_stkBNB\_Smart\_Contract\_Audit\_Halborn%20\[05.08.2022].pdf)) and Certora (currently no report in the public domain, but promises to be). For on-chain tracking of suspicious activity, pSTAKE collaborated with Forta.

### **Liquid ETH staking**

At the moment, ETH stacking is possible on the Ethereum 2.0 Beacon network, which is connected to the ether PoW network via a deposit contract. After the merge planned for September, the two networks will become one. If a user steams his ether on the Beacon network, he will be able to withdraw his ether only after the merge.

The model of ETH staking via the pSTAKE platform is very similar to BNB staking, token minnet stkETH and "accumulation" of rewards via stkETH value increase also follow a model similar to the Compound model. However, there are differences in the mechanism of the staking itself. The ether deposited through the site is deposited to a special contract. When 32 ethers (the minimum number of ethers needed to start a node) are deposited to the contract, those ethers are sent to the validator (node operator). To become a validator, you must first deposit 1 ETH in the Beacon network and specify withdrawal credentials provided by pSTAKE, thus pSTAKE identify the validity of the steering address. If there is more than one person who wants to become a validator, the choice is made on a first-come-first-serve principle (i.e. the one who applied first is the validator). After the air is staked in the Beacon network, pSTAKE receives the data about the successful staking through the oracle. In the future, it is planned that oracles will also monitor the effectiveness of the validators to perform their duties and inform the platform if there are any problems. Also, unlike Binance Chain, in case of slashing, not only validator's personal stack is reduced, but also delegator's stack. To protect its users in further updates pSTAKE is going to introduce slashing risk mitigation mechanism.

\*At this point in time you need to contact pSTAKE to become an operator of a node and if the application is approved, the potential node operator should follow the process described [here](https://docs.pstake.finance/stkETH\_Node\_Operators\_Onboarding/)\
\*\* For more details on what constitutes withdrawal credentials [, please click here](https://launchpad.ethereum.org/en/faq)

ETH staking is done via the pSTAKE platform, instructions and description of the process can be found in the official user guide [here](https://blog.pstake.finance/2022/06/08/stketh-user-guide-eth-liquid-staking-tutorial/).

The user receives standard rewards for ETH stacking, with 5% paid to the validator for its work and another 5% to the protocol commission (these funds also go to pSTAKE ecosystem development).

### **Using stkETH in DeFi protocols**

At the moment users only have an option to add tokens to stkETH/ETH liquidity pool on Uniswap V3 or exchange their stkETH tokens for ETH there as well. However, like in case of stkBNB, in time more supported DeFi protocols and more new possibilities to use strETH will appear, at least pSTAKE assures that.

Audit reports on smart contracts responsible for staking stkETH can be viewed [here](https://github.com/persistenceOne/pStake-auditReports/blob/main/stkETH/pSTAKE%20ETH2.0%20Staking%20Audit%20-%20Trail%20of%20Bits%20\[26.04.22].pdf) and [here](https://github.com/persistenceOne/pStake-auditReports/blob/main/stkETH/pSTAKE%20ETH2.0%20Staking%20Audit%20-%20Peckshield%20\[26.05.2022].pdf)

### **Token $PSTAKE**

PSTAKE is a native ERC-20 token of pSTAKE Finance and performs governance functions. Holders of this token can participate in votes on the development of the protocol and make their own proposals. To do so, they must lock their tokens into a special smart contract. Active users are rewarded for their activity, but in case of their malicious activity or non-compliance with their duties (e.g. if the pBridge validator fails to perform its functions) the user can be punished by slashing part of their stack. PSTAKE is also used to pay rewards to key contributors to the pSTAKE ecosystem.

The total turnover of PSTAKE is 500 million tokens. The distribution of tokens and their unlocking period are shown in the figure below

![](https://img2.teletype.in/files/90/fa/90fa2208-5d58-457f-9fff-134461f83369.png)

Read more about the PSTAKE token and its role in the ecosystem [here](https://blog.pstake.finance/2021/09/09/introducing-pstake/)

### **Links** <a href="#n1ws" id="n1ws"></a>

Official website [here](https://pstake.finance/)

The official medium is [here](https://pstake.medium.com/).

Official blog [here](https://blog.pstake.finance/)

Statistical data of pSTAKE [here](https://analytics.pstake.finance/)

Persistence network website [here](https://persistence.one/)

Citadel.One's article on derivatives stacking [here](https://medium.com/citadel-one/what-are-staking-derivatives-8fd86ed315a2)
