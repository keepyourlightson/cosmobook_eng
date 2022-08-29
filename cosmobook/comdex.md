# Comdex

![](https://img4.teletype.in/files/34/76/3476854c-7a4c-4ee6-bcdb-d946d0eb9c68.png)

## Comdex

Comdex is a protocol for creating and exchanging synthetic assets called cAssets. This protocol plays a crucial role in Comdex's mission to democratize finance. Creating digital trade representations (synthetic assets) of a wide range of assets enables investors to gain global access to finance. Comdex's interoperable ecosystem can aggregate liquidity from multiple DeFi ecosystems. Synthetic assets lay the foundation for realizing this vision by creating bridges to cryptocurrency ecosystems and financial instrument markets.

Today, investors do not have access to a wide range of asset classes due to censorship, limited global availability, liquidity constraints and high transaction costs. The emergence of DeFi has brought with it a wave of products that expand the possibilities for any investor. Comdex is based on technology that enables the creation of digital representations of financial assets that can be tracked and traded on immutable smart contracts. Tokenized synthetic assets provide global accessibility, improved liquidity and reduced transaction costs.\
While DeFi does increase crypto investors' access to a wide range of financial services, investment opportunities are still largely limited to online assets. Few products can build bridges between crypto-assets and real-world financial assets, allowing capital to move from the DeFi ecosystem to CeFi (centralized finance). Even within CeFi, there are a number of regulatory hurdles and restrictions to access stable, inflation-resistant assets and debt products.\
In addition to the need for bridges between cryptocurrencies and CeFi, there is also a need for bridges that will ensure the seamless movement of digital assets across different blockchain networks. Cosmos solves this problem with its IBC protocol. Using IBC, the decentralized synthetic protocol will allow users to access a range of inflation-resistant synthetic assets through Comdex.

The main network was launched in November 2021[(](http://www.youtube.com/watch?v=UTNKMjydIFA)launchparty ).

#### **What are cAssets?** <a href="#fdzn" id="fdzn"></a>

cAssets are synthetic assets that reflect commodity derivative contracts. Synthetic assets help eliminate boundaries and truly decentralize commodity trading. Unlike traditional commodities, which represent the real underlying asset, cAssets are purely synthetic and therefore reflect the price movement of the underlying asset. For example, cXAU (gold) reflects the price movements of real derivative contracts for gold.

#### **Listing of cAsset** <a href="#ioiq" id="ioiq"></a>

cAsset will be included in the Comdex synthetic protocol listing after the following steps:

* creating a cAsset token and defining all parameters;
* the purpose of the oracle-feeder;
* creation of cAsset-CMST trading pair (CMST is a stablecoin with redundant collateral, it will be often referred to below) on cSwap and its LP token.

The listing is approved by the new management proposal and is immediately implemented once 51% of the total management votes are received. The cAsset can then be used to mine liquidity in the Cosmos ecosystem and will be available on cSwap. Liquidity providers earn CMDX tokens that can be used to create new cAssets.

#### **Removing cAsset** <a href="#ggt2" id="ggt2"></a>

If the decision is made to exclude cAsset from the list of available synthetic assets, then:

* Liquidity mining using this cAsset becomes impossible.
* All existing cAsset offerings are burned at a fixed final price set by the oracle feeder to remove collateral from existing open positions. Users will be prompted to burn the cAsset to restore collateral on any open positions on the Comdex protocol. The old cAsset will be withdrawn from circulation and marked "delisting", after which it can only be burned, close open debt positions, withdraw collateral and liquidity.

It is important to understand that crypto has no direct connection to the real world. You can't just tokenize a security or real estate. This is an interesting task that many people are trying to solve right now. If you want to dive into this topic, I suggest you interesting posts from [0x\_unidentified](https://t.me/uselesscryptoscam) [here, ](https://t.me/uselesscryptoscam/112)[here](https://t.me/uselesscryptoscam/113)[ and ](https://t.me/uselesscryptoscam/112)[here](https://t.me/uselesscryptoscam/114)[.](https://t.me/uselesscryptoscam/112)

#### **Comdex modules** <a href="#ofmp" id="ofmp"></a>

Comdex consists of different modules (tools). Since they didn't draw a nice picture with modules (like Agoric's, for example), read the dull text and turn on your imagination.

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

**The Vault module** is responsible for creating and managing the repositories.

Collateralized Debt Position (CDP, Collateralized Debt Position, i.e. an open position, secured by some asset) allows you to create a commodity synthetic asset by locking another asset as collateral.

The Vault module manages and stores CDP creation information. The collateral is locked in the vault and a new asset is mined. If the user wants to retrieve their collateral, they must repay the debt by returning the mined asset to the vault and paying a fee. At this point, the minified asset will be burned and the collateral provided will be unblocked.

Asset prices are tracked using oracles such as Band Protocol or a decentralized pool such as Osmosis. Liquidation occurs when the position security ratio falls below the minimum threshold (Liquidation Ratio), i.e. everything is standard.

Collateral ratio = (Value of collateral assets)/(Value of borrowed assets).

The collateral threshold for a liquidation occurrence may vary depending on the type of pledged asset and the type of leveraged asset. In addition, this threshold value can be changed through management proposals for each asset.

Example:\
A user locks an ATOM worth $200 to borrow a cAsset worth $100. In this case, the collateral ratio is 200%. Assuming a liquidation ratio of 150%, two cases could occur that would reduce the collateral ratio:

Case 1: cAsset prices are rising and liquidation will occur when the cAsset value rises to 133.33 (assuming the collateral value (ATOM) remains the same).

Case 2: The pledge price decreases and liquidation will occur when the atom price decreases to $150 (assuming the cAsset value remains the same).

**The Collector module** is where all fees and revenues generated by the protocol will be accumulated.

#### **Commissions** <a href="#d4te" id="d4te"></a>

Withdrawal fee:

This is a fixed amount of CMST charged on the user's debt with each CMST withdrawal.

A commission for mining CMST:\
Charged to users who mine CMSTs from their vaults. Upon repayment, the interest is deducted from their borrowed position and sent to the Collector module.

Penalty for liquidation:\
In the case of a liquidation, the value of the asset auctioned off to close the debt exceeds the debt amount by a small fixed percentage. The resulting additional CMST amount is sent to the Collector module.

StableMint Commission:\
Each transaction with stablemint module is charged a fee in CMST.

Locker Savings Commission:\
This is the only component of the collector module's deductions where the interest earned by users leaves the collector module.

This module has a surplus threshold and a debt threshold. In an ideal scenario, CMST will continue to accumulate in this module and eventually exceed the surplus threshold, CMST will be withdrawn from the collector module in fixed lots and auctioned for HARBOR tokens. HARBOR tokens received through the protocol will be burned.

Read more about HARBOR protocol [here](https://docs.harborprotocol.one/).

In the event of an increase in debt, CMST in this module will continue to deplete, eventually falling below the debt threshold. In this scenario, HARBOR will be auctioned back for fixed CMST lots. CMST will be sent to the Collector module for replenishment and new HARBOR tokens will be smoothed and issued to the user who won the auction.

**The liquidation module**, as the name implies, is responsible for the mechanism of liquidations.Liquidated cAssets are sent to the Auction.

Bidding at the auction lasts for 6 hours, and the highest bid takes the liquidated cAsset. The auctioned assets are transferred to the bidder's account.

**The Locker module** allows any CMST owner to earn variable interest on principal by locking CMSTs into the Locker vault in the Harbor Protocol. Users are not required to deposit a minimum amount of CMST to earn interest from the vault, and they can withdraw some or all of their capital from the vault at any time.

**The Market module** is responsible for providing external data to the blockchain using an oracle system. Price quotes are updated by market feeders and periodically synchronized and then transmitted by the protocol. All data is taken only from reliable and authoritative sources.

**The liquidity module** integrates the Gravity Dex Protocol. This module allows Comdex users to swap, transfer and merge assets.

**cSWAP**\
cSwap allows platform users to exchange their cAssets via AMM. Users can also contribute their assets to liquidity pools and earn rewards for doing so.

#### **$CMDX** <a href="#m3yu" id="m3yu"></a>

**The CMDX token** is a native token of the COMDEX network.

The token performs the following basic network functions:\
\- Governance: COMDEX users and CMDX token holders have the right to manage and control various platform parameters. They also have the ability to change key parameters such as fees, cAsset, etc.\
\- Payment of transaction fees.\
\- Payment of rewards to users and active network members.

The CMDX token is inflationary in nature with a 30% inflation rate in the first year and a subsequent 25% inflation rate reduction in each year with a maximum supply cap of 200,000,000 CMDX.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Airdrop of the CMDX token at [Airdrop.comdex.one](http://airdrop.comdex.one/) for Cosmos ecosystem communities such as Persistence, Cosmos, Terra and Osmosis started on March 7, 2022. Airdrop is put to those who hold/stick XPRT, ATOM, ~~LUNA~~ or OSMO during snapshot.

<figure><img src="../.gitbook/assets/image (33) (1).png" alt=""><figcaption></figcaption></figure>

#### **Comdex ecosystem** <a href="#0zda" id="0zda"></a>

In addition to cAsset and the enterprise trading platform, the Comdex team is working on several new products such as Commodo, ShipFi, and the $CMST stablecoin, which will be launched shortly.

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Enterprise Trading is a B2B application created to tokenize real commodity assets and facilitate instant trading, settlement and financing. The platform has already connected more than 18 organizations from the Southeast Asian region.

Commodo is a secured lending/borrowing app (learn more [here](https://docs.commodo.one/)).

With ShipFi, Comdex aims to enter the NFT world by digitizing and exchanging ownership of commodity finance debt. This platform will use the SHIP token.

$CMST should become the native super-secured stablecoin of the Comdex ecosystem.

#### Roadmap <a href="#hlst" id="hlst"></a>

_January 2022_: Comdex integration with CosmWasm.\
_February 2022_:

\-beginning of native Stablecoin development;\
\- start of Commodo development.

March 2022:

\- launch of CAsset devnet;\
\-start of CSwap development.

_In progress_:

\- running the Composite test;

\-starting the CSwap test;

\- running Commodo's test run.

_Planned for August 2022_:

\- Composite run on the main network.

\- CSwap startup on the main network;

\- Commodo run on the main network;

\- ShipFi test run.

#### **Scandal, intrigue...** <a href="#5v3p" id="5v3p"></a>

As I was writing, the scandal between Comdex and Osmosis was in the spotlight.

OsmosisLab made [a ](https://www.reddit.com/r/OsmosisLab/comments/w7zu03/comdex\_foundation\_wallet\_wash\_trading\_profit/)reddit announcement in late July, followed by [a suggestion ](https://www.reddit.com/r/OsmosisLab/comments/w7zu03/comdex\_foundation\_wallet\_wash\_trading\_profit/)on the Osmosis chatroom (a decision is still up to the community to vote on) that proposed removing all OSMO and superfluid-stacking incentives from pool #600 ATOM/CMDX and pool #601 CMDX/OSMO. This relates to allegations against Comdex that wallets connected to Comdex Foundation nodes were involved in volume manipulation/washing through Osmosis DEX and selling CMDX through OSMO for USD, in many cases hourly, every hour since May 2022. The evidence and analysis (with images) of this behavior is thoroughly documented here: [https://medium.com/@Rarma\_/comdex-foundation-wallet-wash-trading-receipts-ddb90b9c7717](https://medium.com/@Rarma\_/comdex-foundation-wallet-wash-trading-receipts-ddb90b9c7717).

[Comdex responded](https://twitter.com/SidP95/status/1550861194302717952) by stating that they did not launder the funds, that [tokenomics](https://blog.comdex.one/cmdx-token-economics-utility-cd66bda2c1bb) requires them to sell their tokens, and that the team will not receive its due until December 2023.

In any case, it all looks like manipulation, and given that Osmosis has no order book, and everything is built on pools of liquidity, the consequences of such actions are very unpleasant.

The token itself hasn't responded yet, but we'll see how this story ends.

#### **Summary** <a href="#iki7" id="iki7"></a>

The project has many ambitious plans, but there are no ready solutions in the mainnet yet. To make an assessment, we need to wait for the finished product. The topic of synthetic assets is popular now, but we are all still very far from specific working schemes for a wide range of users. That said, the token has been traded for quite some time.

I hate to bring the Osmosis story into this, but I'd wait for it to unfold, as the consequences could be serious for the project. Let's watch, now we have an idea of what's going on here...

#### **Links** <a href="#xqhe" id="xqhe"></a>

Website: [https://comdex.one/home](https://comdex.one/home)

Twitter: [https://twitter.com/ComdexOfficial](https://twitter.com/ComdexOfficial)

Discord: [https://discord.gg /](https://discord.gg/)

Telegram: [https://t.me/ComdexChat](https://t.me/ComdexChat)

Medium: [https://blog.comdex.one /](https://blog.comdex.one/)

Reddit: [https://www.reddit.com/r/ComdexOne](https://www.reddit.com/r/ComdexOne) /
