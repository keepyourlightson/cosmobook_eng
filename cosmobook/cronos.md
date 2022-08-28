# Cronos

![](https://img1.teletype.in/files/c4/1c/c41c6fa0-b808-46bc-8dab-cce24266b892.png)

## Cronos <a href="#lint" id="lint"></a>

\*We couldn't find any detailed description of Cronos in public sources, so we took as a basis the publication of Messari "Cronos: An Introduction and Analysis of a New L1" (original_ [_there_](https://messari.io/article/cronos-an-introduction-and-analysis-of-a-new-l1?referrer=list-view)_), though we couldn't find any technical information there either._

**Crypto.org** - a blockchain built on the Cosmos SDK, used for stacking and transactions within the Crypto.com crypto exchange

**Cronos** (formerly called Crypto.org EVM chain) is an Etherium-compatible network built on the Cosmos SDK. Crypto.com is behind the creation of Cronos, but Cronos Labs is now responsible for the design and development of the network. Cronos is a trustless, open-source blockchain, and Cronos Labs' main goal is to enable developers and users to instantly port their apps and assets from other networks, thereby attracting new DeFi, GameFi and new users to the Cosmos ecosystem.

_\*Since there is nothing remarkable about the Crypto.org network, i.e. it is a common area in the Cosmos ecosystem that essentially brings no innovations, but, like all other blockchains based on the Cosmos SDK, is fully compatible with other blockchains within the ecosystem, the description of the Cronos network will mostly follow._

### **Crypto.com and history of Crypto.org&Cronos**

Crypto.com was founded in June 2016, at first it was called Monaco and was a centralized exchange. The number of Crypto.com users grew from 1 million in 2019 to 50 million in 2022. Crypto.com conducts an aggressive marketing campaign (I'm sure many of you have seen their logo at various major sporting events - NBA, NHL, UFC, formula 1, etc.), is currently among the ten largest exchanges, they own a very popular cryptocurrency wallet of the same name and they have developed a kind of cryptocashback to the card. In this case, rewards to cardholders are paid in native CRO token, and users must also keep some amount of CRO on their card to receive these rewards.

In 2019, the Crypto.com team launched its own blockchain, Crypto.org, with the goal of enabling users to trade, make payments and use financial services on blockchain "rails." However, normal development of the network was impossible due to insufficient functionality of native smart contracts. To solve this problem, the Crypto.org EVM network was launched in 2021, which after rebranding became known as Cronos, and Cronos Labs was formed to design and develop the network, which immediately received a $100 million grant from Crypto.com.

### **Cronos Tech**

At first, the team planned to create their own EVM compatible blockchain, but in the end they used a ready-made solution from Ethermint (now Evmos) with some necessary modifications.

As of July 2022, there were 27 validators in the Cronos network (the current number of validators can be seen [here](https://cronoscan.com/stat/miner/2?range=7\&blocktype=blocks)), with plans to increase that number to 60-80 by the end of 2022. However, in order to become a validator, a user must have a certain number of havernance tokens, which are called "Cronos governance token," this token is not traded on any exchange and is issued to active members of the community. Although the consensus mechanism is based on Tendermint (i.e. a typical PoS, where the probability that the current block will be signed by a certain validator depends on the number of coins of that validator), the team itself characterizes Cronos as a Proof-of-Authority blockchain. Block generation time is 6 seconds, validators do not receive any rewards for finding a new block, only transaction fees. Also, havernance token holders have the right to participate in votes, where the strength of their vote is also proportional to their number of tokens.

### **Tokenomics**

The Cronos token (CRO) is common to Crypto.org and the Cronos network, but exists in three different standards: native CRO for Crypto.org, CRC-20 CRO for the Cronos network and ERC-20 CRO for the Ethereum network.

In the Crypto.org ecosystem, the CRO token is used for stacking, payment of transaction fees, payment of rewards to validators (5 billion tokens out of a total saplus of 30 billion are allocated for this purpose) and in the long term will also serve as a havernance function. Users can stack CROs to validators (any user can be a validator, but only the top 100 validators get rewards), and depending on the number of tokens and local time they get certain rewards (more details [here](https://crypto.com/earn)).

There are two tokens in the Cronos network. The use of the havernance token was described above, and the CRC-20 CRO token serves to pay transaction fees. As noted, there are no additional rewards for finding a block in the Cronos network. Therefore, to attract more validators, the team is working to expand the user base with CRO token holders from the Crypto.org ecosystem.

### **Ecosystem, and important/expected events**

Currently, there are more than 200 applications in the Cronos ecosystem (the figure is large, so the link to it is [here](https://twitter.com/NewsCronos/status/1524554990454546432/photo/1)). The team is actively engaged in attracting developers through a system of grants and hackathons (more details [here](https://medium.com/cronos-chain/cronos-ecosystem-grants-7a4a2de3b721) and [here](https://hidorahacks.medium.com/cronos-hackathon-application-guide-up-to-500k-prize-pool-workshops-and-more-ed8d5c8f9dcc)). Also in the near future it is planned to launch its own gas pedal.

### **Significant ecosystem projects**

- VVS Finance - DEX in Cronos ecosystem, has the largest TVL of all projects on Cronos, 70k users (per month), and also stands out by a unique mechanism of listing new tokens, called Initial Gem Offerings (more details [here](https://medium.com/vvs-finance/introducing-vvs-initial-gem-offering-7802bc9aa383)).

- MM Finance is another DEX, with a yield optimizer and its own native algorithmic Stablecoin.

- Tectonic is the largest lending protocol on Cronos (TVL about 450 million as of July 2022).

- Single Finance and Thetanuts Finance - both projects focus on structured finance (options, derivatives).

Important/Expected Developments

- April 2022 saw the launch of Cronos Play, a platform that will allow game developers to use popular engines such as Unity and Unreal, as well as provide a set of tools to create their games within the Cronos ecosystem (more [here](https://medium.com/cronos-chain/cronos-announces-cronos-play-and-its-first-integration-with-chainsafe-gaming-sdk-523fdbc28d7)).

- On July 11, 2022, Cronos announced its integration with Covalent (see [here](https://medium.com/cronos-chain/covalent-integrates-with-cronos-blockchain-to-ease-data-access-for-developers-data-analysts-and-32879a424918)).

- For July 2022, Cronos integrated Gravity Bridge technology (there is also a blockchain of the same name in the Cosmos ecosystem, but Cronos uses its technology, not the bridge itself), which will allow users to transfer ERC-20 tokens into the Cronos network. As of July 2022, Gravity Bridge is in test mode.

- By the end of the second quarter of 2022, Aave v3 is expected to launch on Cronos.

It is worth noting that while Crypto.com is a well-known exchange and has been operating for a long time, Cronos is a very young network even by the standards of the Cosmos ecosystem. They have yet to address the issue of centralization (few validators) and build/attract quality DeFi and GameFi protocols and applications, but Crypto.com is a very recognizable brand and Cronos Labs has a good team that is recruiting new employees in large numbers. While Cronos' plans and goals don't seem particularly new, it will be interesting to see if Cronos Labs can pull them off.