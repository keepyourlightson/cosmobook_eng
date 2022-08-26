# Juno

![](https://img4.teletype.in/files/f8/6c/f86cc85f-01a0-4568-a019-22c6435e9b1b.png)

## Juno <a href="#uler" id="uler"></a>

The Juno blockchain is the result of an initiative by the Cosmos community of developers, validators, and delegators.

The goal of the initiative was to isolate the depletion of smart contracts into a dedicated Cosmos subsidiary hub. It is a kind of decentralized ecosystem sandbox with no restrictions or censorship. Developers don't have to wait for validators' approval to become part of the hub: this allows projects to launch quickly, but also leads to low-quality dApps that can get onto the platform. Popular frameworks and the ability to compile smart contracts in Rust and Go are available for developers. C and Cpp are planned to be added.

### **Differences between Juno and other smart contract blockchains**

Here's what sets JUNO apart from Ethereum and Solana (according to JUNO developers):

1. _Simple Deployment of Smart Contracts;_
2. _Basic level without permissions;_
3. _Dom CosmWasm (Interwasm DAO);_
4. _Built-in compatibility;_
5. _High scalability;_
6. _High security level;_
7. _Creation of a decentralized network;_
8. _Community-led core development;_
9. _Leading community liquidity;_
10. _Community led ecosystem development;_
11. _Balanced management;_
12. _Dynamic balancing of fees;_
13. _Сlear legal status (no pre-sale, private sale or public sale)._

The network was launched on 01.10.2021 with the distribution of tokens to $ATOM hodlers, and in December of the same year with the Moneta update the CosmWasm module was added to the network.

![](https://telegra.ph/file/edd1d4ad1a5af58ef5344.png)

### CosmWasm <a href="#cosmwasm" id="cosmwasm"></a>

CosmWasm is a platform on CosmosSDK that adapted the WebAssembly language for the Cosmos blockchain. Wasm, in turn, is low-level bytecode for use in a browser. The trick is that the code can be converted to machine code right at boot time (stream compilation). CosmWasm allows developers to write modules in Rust, which in turn integrate seamlessly into the Cosmos SDK, and it also allows code to be loaded directly into transactions.

We'll skip the rest of the details, but it's important to understand that it makes smart contracts fast;)

Although the Rust+CosmWasm bundle is more difficult to develop than Solidity, it is claimed that it allows you to write complex contracts without any security holes (commemorate that point;)

You can read more about CosmWasm [here](https://docs.junonetwork.io/juno/home-of-cosmwasm.)

### $Juno <a href="#token-juno" id="token-juno"></a>

The native network token is $JUNO.

As mentioned earlier, 47% of the initial volume of tokens ($64,903,242 JUNO) was dropped for $ATOM stackers at a 1:1 ratio. That's why they love the space in the first place; there are a lot of drops here. A 12-year vesting is in place for the team.

![](https://telegra.ph/file/4f419f7d78451f7dc6292.png)

The total issuance over 12 years will be 185,562,268, with the JUNO reward model distributing a fixed number of JUNO tokens per block depending on the inflation rate and block time of the network. The inflation model is as follows:

![](https://telegra.ph/file/4af0ab56dcdab1316ab4d.png)

### Governance & scandals <a href="#gavernans" id="gavernans"></a>

What else is important to know is the sensational Proposition 16, when the community voted to take the honestly earned $2.5M JUNO from the whale, and put the squeezed out into the community pool, or destroy it.

The motivation of the decision was that the initial limit of 50K tokens per person was broken, as well as the high risk for collective management - that's already half of the quorum. The results of the vote are on the screenshot.

![](https://telegra.ph/file/b8a6d8d292416476384ab.png)

After that there was a lot of buzz, exclamations for and against, the whale "surfaced" including a post in Medium (it was deleted along with the account, but "the Internet remembers everything," the post can be read in the web archive, the link [here](https://web.archive.org/web/20220313021752/https://medium.com/@WhaleJuno/our-statement-on-juno-prop-16-5a06b26e6cff)

A series of operations performed by CCN (that's the whale from Japan) can be found [here](https://docs.google.com/spreadsheets/d/1McQE3Ot-QkAElou6\_Qs1TS9ZaCHeTVp0dYRAWZ7TOYM/edit#gid=0).

If you look into this story in more detail, you can stumble upon 4 proposals: the whale had already been calculated by that time, but the offer was rejected as a result of dubious arrangements. And later, when they began to discount $ JUNO, the story has found its continuation. This whole mess gave birth to many tweets, as well as controversy in various chat rooms.

In addition to the strange actions of the founding fathers, details emerged that the whale, who acted in the interests of older investors from Japan, embezzled drops. The whole thing was resolved by a 20-proposal, which was supported by the community. As a result of that proposal, the chine was renewed, with all but an "honest" $50,000 JUNO taken away from the big holder.

Oh, yeah. At the end of the 20-poS, the fat that was cut from the whale was supposed to be sent to the Juno address in the community pool, but the developer copied the tranza hash instead of the wallet address and sent the funds there. Since this is PoS, the community was able to vote again to transfer the funds. "Code is law" in action...

Meanwhile, Takumi Asano, the same whale, claims that Juno's price is falling because tokens are being dumped by...wolfcontract, one of the developers of the chain. To prove his words he cites analytics, link [here](https://docs.google.com/spreadsheets/d/1kQYL-lu3UNJqzLArhbTAFOpFjWm5Wa7-RStS-coMuys/edit)

Note that this is the first community decision in the history of crypto to shave a whale, not hamsters:)

### Faults <a href="#uyazvimosti" id="uyazvimosti"></a>

On April 5, 2022, the blockchain suspended operation due to a deployed smart contract disguised as a classic "Hello, World!" The vulnerability affected all blockchains using CosmWasm.

This, by the way, happened less than a month after the sensational 16th sentence.

### Ecosystem <a href="#ekosistema" id="ekosistema"></a>

Now there are about 50 applications on Juno. Among big protocols - Junoswap (DEX), DAODAO (DAO creation toolkit), TFM (DEX aggregator), JunoMint (DAPP to mint your token on JUNO), StrangeClan (p2e game on u5 engine).

There are strange things here too: Junoswap is still in beta. This is probably because of the complicated development on CosmWasm. It's one thing to fetalize Uniswap/Sushiswap on EVM, but another to write from scratch. The github looks pretty good (you can see it [here](https://github.com/cosmoscontracts/junoswap-interface)), and the UI designers should look up Osmosis. Because at the moment, the UI looks like this:

![](https://telegra.ph/file/5d2def098abd1560492d2.png)

What we have in the end: a blockchain focused on the development of fast contracts, but probably too innovative to be afloat already.

### Links <a href="#ssylki" id="ssylki"></a>

1. Current blockchain statistics you can check in the dashboard from Bro’n’Bro [here](https://monitor.bronbro.io/d/juno-stats/juno-stats?orgId=2\&refresh=5s)
2. Get to know the ecosystem [here](https://www.junonetwork.io/ecosystem/)
3. Official docs [here](https://docs.junonetwork.io/)
