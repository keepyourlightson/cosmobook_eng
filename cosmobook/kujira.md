# Kujira

##

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## Kujira

The Kujira project was originally conceived as an ecosystem of dApps in the Terra network. The first dApp from Kujira was ORCA (Q4 2021), which allowed some users to receive a discounted deposit from other users with excessive debt. The next dApp was Beluga, which allowed users to send any CW20 token to Terra to multiple addresses simultaneously in a single transaction.

On May 12, 2022 at 01:58:49 (UTC), after days of uncertainty, the Terra blockchain was shut down. The tragic death spiral buried many projects and today we will talk about Kujira, which survived, moved to its own network and became stronger.

With the launch of FIN (the new decentralized order book exchange), some concerns about technical limitations began to emerge. One concern was scalability, as sharing the network with other protocols also meant sharing network bandwidth for transactions, which had become congested even before Terra's problems began.

After the events with Terra, Kujira essentially had two options:

A) build a network on top of an existing L1 network such as Ethereum or Avalanche;

B) create its own independent, sovereign network.

Option A provides an off-the-shelf platform with existing security and interoperability, but requires Kujira products to be built within the technical boundaries of smart contracts and does not help solve the scalability (bandwidth) problem. Option B, however, gives full control over the protocol design, allowing for more sophisticated functionality where, for example, support for trading bots can be built into the underlying protocol.

The problem of choosing between A and B (and given that Terra was built on Cosmos) is solved by moving to the Cosmos ecosystem's own L1 network, where the development team has full control over protocol design, as well as initial compatibility with all other Cosmos networks thanks to the Cosmos SDK. This solution allows applications and infrastructure to be quickly migrated to the new network, giving a much faster start than any other alternative.

Already in June 2022, Kujira launched a testnet, and in July the main working network. Also, migration of $KUJI tokens from Terra network was organized via Keplr wallet (link [here](https://blue.kujira.app/migrate)[)](http://kujira/).

Kujira kicked off in July 2022 with the launch of 3 products in its network (4th project - ORCA on the way):

* Kujira Blue.[(A KUJI dashboard](https://blue.kujira.app/) that allows all the classic Cosmos activities (voting, steaming, awarding, etc.) to be done in one place.)
* Kujira Finder ( [the](https://finder.kujira.app/kaiyo-1) classic web explorer ).
* Kujira FIN (DEX).

**An idea.** Everyone deserves to be a whale.

**Concept.** For decentralized finance to be truly revolutionary, there must be an opportunity to generate income both when the market is rising and when it is falling. Kujira aims to help retail investors move beyond exchanges, betting and ICOs to unlock opportunities that were once only available to whales and the elite.

**Objective.** To create tools that are simple and cost-effective for everyone from the novice crypto-enthusiast, to the seasoned retail investor, regardless of their consistency of choice, without having to risk more than they can afford to lose.

Kujira boasts a block generation time of around 2.2 seconds, making it one of the fastest networks in Cosmos along with Evmos (1.9 seconds) and Injective (2.4 seconds), while other Cosmos blockchains typically have block generation times around 5-7 seconds.

Fast block generation is especially important for FIN, as it is a DEX based on order book. Short block generation times are important for the Kujira network, especially for a decentralized FIN exchange operating on the order book model. Moreover, the shorter the delay between the generation of two successive blocks, the less opportunity validators have for front-running.

### **Kujira ecosystem** <a href="#lv40" id="lv40"></a>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### **FIN by Kujira** <a href="#el6t" id="el6t"></a>

FIN is a decentralized order book exchange. Soon the possibility of margin trading will be added.

Within one week of the launch, trading volume was just under $1 million in just two pairs: [KUJI-axlUSDC](https://fin.kujira.app/trade/kujira14hj2tavq8fpesdwxxcu44rty3hh90vhujrvcmstl4zr3txmfvw9sl4e867) and [wETH-axlUSDC](https://fin.kujira.app/trade/kujira1suhgf5svhu4usrurvxzlgn54ksxmn8gljarjtxqnapv8kjnp4nrsqq4jjh).

FIN**fees** are divided into two parts:

1\) **"Maker Fees" are commissions** paid if you place limit orders that are not immediately executed and thus "create" liquidity in the order books. FIN declares its main distinction to be that there is no need for a liquidity pool, which offers three huge advantages:

\- You don't need to hand out millions of printed/inflationary tokens just to keep people in LP;

\- Your community is not at risk of Impermanent Loss just for trying to support your project;

\- You can reallocate the liquidity belonging to your protocol to something more productive.

Every degen faces a vicious cycle where as the supply of tokens increases, their value decreases and inflationary rewards begin to decrease in dollar terms. As the APR decreases for liquidity providers, the rewards may no longer justify the opportunity cost, and they may seek profit elsewhere while taking their liquidity with them. To put it another way, it's a classic story where we farm for the first 3-5 days, then take funds out of the pool and run to another DEX. Exchanges operating on the order book principle are not subject to this problem.

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

2\) Taker **Fees** - fees paid when placing market and limit orders, which are executed immediately. They "take" liquidity from the books and therefore pay a higher fee.

Commission fees for placing and executing orders on FIN are much lower than on most AMMs. The standard commission for trading on AMMs is 0.3%, which is twice as much as on FIN.

Gas fees on Kujira are also very cheap, and users on FIN can pay in several different denominations of gas. This is beneficial because when an asset rises in value, gas will consequently cost more when using that token; paying commissions in different tokens allows customers to use the currently cheapest option . For example, if the value of KUJI is skyrocketing, you can switch to paying for gas in OSMO.

However, on Ethereum, commissions often become an issue only when the network is overloaded. Therefore, in addition to low commissions, FIN can guarantee execution of transactions at more favorable prices for the user.

**Execution of trades**\
Thanks to the order matching mechanism on exchanges operating on the order book principle, traders are guaranteed execution at or better than the specified price. When you place a limit order, your trade will not execute at a worse price, regardless of the size of your trade.

All the details and features of the FIN and its benefits are described in [this article](https://medium.com/team-kujira/fin-a-dex-to-stand-the-test-of-time-6a311e040297).

FIN has chosen to use Axelar's USDC wrapper, axlUSDC, as its stablcoin.

Trading is possible with KUJI, ATOM,OSMO, EVMOS, JUNO, LUNA, SCRT, wETH.

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

Read more about how to trade on Fin [here](https://medium.com/team-kujira/how-to-buy-kuji-on-fin-485172f23eea).

### **ORCA** **by Kujira** <a href="#iw6v" id="iw6v"></a>

ORCA is a public trading platform that allows users to purchase liquidated assets at discounts.

On Terra Classic, ORCA allowed users to bid for liquidated positions on the Anchor protocol using UST and aUST. This was made possible by the Anchor liquidation queue contract, which incentivised liquidators to undertake liquidation activity on collateralised positions by allowing them to receive the underlying collateral at a discount.

Users placed bids with a preferred premium, which is the discount a bidder receives for liquidating loans on Anchor. Premiums ranged from 0% to 30%, and loans were liquidated starting with the lowest premium, after which the next highest premiums were activated until no collateral remained for liquidation or there were no more bids.

Before ORCA, loans could only be liquidated by bots or users directly interacting with the smart contract of the liquidation queue. This put ordinary users at a disadvantage, as only a select few could profit from the liquidated collateral.

ORCA also allowed users to profit during market downturns, as liquidation occurs more often during a fall in the price of the underlying collateral. Successful bidders received assets at reduced prices, with many using ORCA as a DCA tool to buy cheap bLUNA and bATOM during market downturns.

**ORCA Commissions** (thanks to @vladimir\_g\_g for [clarification](https://t.me/kujira\_ru/1385))

* Commission for all successful (executed) liquidation applications:

is 0.5% of the total amount of the withdrawn assets, (i.e. this fee is not withdrawn immediately, but when the Liquidator withdraws assets from Orca, which he received through his executed application for liquidation).

100% of all commissions generated in this way at ORCA are paid to KUJI's stackers, and are paid in the assets that are withdrawn by the liquidators.

* Network Commissions:

Placement, cancellation and withdrawal of liquidation orders require a contract to be signed, which means commissions for transactions on the network. Usually such commissions are only a couple of cents.

* Liquidator's fees:

Liquidators (those whose application for liquidation is successful) are usually paid 1% of the loan amount - this percentage is determined by the lending market. These fees are paid by the lending markets and are NOT deducted from the collateral that is purchased on ORCA (by the liquidator at a discount). In other words, lending platforms (e.g. Karura) that use Orca as a liquidity return tool pay additional 1% of the collateral amount to the Liquidator, as an incentive to its performance.

It's quiet on the ORCA website today so far. We can only say that they want to interact with Polkadot:

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption><p><a href="https://orca.kujira.app/">https://orca.kujira.app/</a></p></figcaption></figure>

I'll say more. Judging by this [tweet](https://twitter.com/TeamKujira/status/1551545612205785092?s=20\&t=QlYZDdSZv663HhQ3rKKDRA), the upcoming launch is being prepared on [@KaruraNetwork](https://twitter.com/KaruraNetwork) (it's the DeFi network in Kusama, Polkadot's Acala counterpart).

### **BLUE by Kujira** <a href="#uttd" id="uttd"></a>

BLUE is the core of the Kujira ecosystem and contains the ecosystem dashboard, a wallet, a simple swap user interface, an IBC bridge, and a management portal.

The Kujira wallet on the Blue dApp has advanced functionality, allowing users to send tokens to multiple recipients with vesting periods (at predefined times). This can be used by protocols, DAOs or anyone who wants to make payments with custom sending periods without having to develop their own vesting contract.

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

The Swap interface on BLUE does not differ from the basic swap user interface found on AMM DEX. However, trades made through Swap are routed through Kujira's own CLOB DEX, FIN. This represents an alternative frontend for users who are not used to the more advanced trading interface that FIN offers.

### Mobile wallet **by Kujira** <a href="#b9i3" id="b9i3"></a>

on July 4, 2022, Kujira [announced](https://twitter.com/TeamKujira/status/1543908579878518784) Its mobile wallet. While not many details have been given, we see this as a possible catalyst for the Kujira ecosystem, as such a wallet facilitates user connectivity and provides potential utility for everyday transactions.

### **Team** <a href="#iiei" id="iiei"></a>

The team operates anonymously, but enjoys a reputation in the Terra and Cosmos communities for their ability to create useful products with much needed utility and excellent UX.

### **$KUJI** <a href="#fqbo" id="fqbo"></a>

Kujira network's native token is $KUJI. The total supply of $ KUJI is 122.4 million tokens.

Purpose of the token: payment for gas in the network. All fees collected are distributed among participants steaming $KUJI. It is important to note here that $KUJI is not an inflationary token.

Issuance: token generation started in November 2021 with the following issuance schedule:

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

### **Roadmap** <a href="#cxhk" id="cxhk"></a>

Naturally it is worth watching from the beginning of the network's new life - the launch of Kujira on L1 Cosmos:

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

Plans for the near future

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

### **Summary** <a href="#pxqx" id="pxqx"></a>

Many believe in Kujira. A very interesting feature is that the interest from the commission is poured rewards in the same coin in which they trade.

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

After the launch of ORCA, when the number of participants increases, steakers are entitled to expect good rewards with a very small % (0.47% at the start) for steaking. Today the picture looks like this:

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

In addition, protocol interaction rates and site traffic [growing](https://twitter.com/TeamKujira/status/1553716395136909318?s=20\&t=y-fzq\_GXiIxLbkNtObkxjw). These numbers, although small, indicate that Kujira is in a healthy growth state, especially considering the unfavorable market at the moment.

And then you just need to understand the perspective of the project) DYOR!

### **Bonus (stablecoin)**

In [an article in Medium](https://medium.com/team-kujira/kujira-usk-stablecoin-launch-kickstarting-grown-up-defi-26b4372d7aef), Kujira announced that it is ready to launch its own stablecoin.

Kujira $USK will be an SDK-native stablecoin Cosmos with excess collateral, with a soft US dollar peg mechanism initially backed by $ATOM. Some users will pledge to mine $USK, while other users will burn $USK to repay their pledge. In addition, if the value of a user's pledge falls too low, it will be liquidated. The $USK is intentionally integrated into ORCA to ensure a smooth democratic liquidation that will be publicly available to all users. Kujira will not allow collateral against the USK from centralised issuers (e.g. USDC) so as not to be dependent on their pledged lock-up in the smart contract.

It is planned that the set parameters such as mint fee, loan interest rate, liquidation fee, ORCA withdrawal fee and maximum LTV will be conservative and then monitored by the community management as part of the natural policy. As part of this setting, the following metrics are assumed:

**0.5%** APR for min;\
**5%** APR on loan;\
**1%** liquidation fee;\
**0.5%** ORCA withdrawal fee;\
**60%** maximum LTV $ATOM (i.e., 67% with excess collateral). (A little background Lifetime **Value(LTV**) is all the profit from the client over the period you work with them.)\
These numbers can be discussed by the community later, once everything is in place.

**What's interesting about KUJIRA's $USK Stablecoin**\
\- Experience creating a first-class liquidation queue for Anchor Protocol #3 DeFi TVL dApp.\
\- Experience of $UST collapse at the zero level.\
\- Robust, theoretically sound system applied by Maker DAO.\
\- As the Cosmos native Stablecoin, $USK gives $ATOM another use case that promotes value accumulation.\
\- Rust is an expressive codebase for $USK and easily allows for greater technical complexity compared to JavaScript or Solidity. It is also inherently more secure (error tolerant) and is increasingly used for financial applications due to the level of security guarantees.\
\- $USK, a key infrastructure, is sovereign, uncensorable and revenue generating.

Are you satisfied with these arguments? I have not let go of the UST story yet. The cosmos really needs Stablecoin, a lot of people are about to head into that water. Let's see what happens next...

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

$USK and ORCA are moving to TestNet starting Wednesday (August 10, 2022) for testing and QA with the prospect of launching about 2 weeks after that date. LTV on credits will initially be made good and safe to ensure maximum stability and will be adjusted as the system grows.

### **Useful links and notes** <a href="#460x" id="460x"></a>

* [Gitbook;](https://docs.kujira.app/introduction/grown-up-defi)
* [Review](https://kujira.explorers.guru/) the polls by proposal;
* [Block Explorer;](https://finder.kujira.app/kaiyo-1/)
* [Medium;](https://medium.com/team-kujira)
* [Discord;](https://discord.com/invite/teamkujira)
* [Twitter;](https://twitter.com/TeamKujira)
* [Telegram;](https://discord.com/invite/teamkujira)
* [Telegram](https://t.me/kujira\_ru) (Russian speaking community);
* Where to buy $Kuji: [https://fin](https://fin.kujira.app/trade).kujira.app/trade;
* A useful bot in working with Kujira ( @KujiraNotification\_bot );
* Get USDC to and from the Kujira network:\
  bridge -> http://satellite.money
* How to buy axlUSDC:

```
🔗 Avalanche: Change USDC.e to axlUSDC: https://avax.curve.fi/factory/59
```

```
🔗 Polygon: Change USDC to axlUSDC: https://polygon.curve.fi/factory/221
```

```
🔗 Fantom: Change USDC to axlUSDC: https://ftm.curve.fi/factory/85
```

If interested in validators from the Ru-speaking community, here they are:

\- [cyberG](https://blue.kujira.app/stake/kujiravaloper1tharcgrfu6j0dcwpe5y6ez3s904rhq2kmccm4k)

\- [MMS](https://blue.kujira.app/stake/kujiravaloper1hn4za2pm8fnkgk3cjw9az9z7q9p4qg3yayh74l)

\- [vbloher](https://blue.kujira.app/stake/kujiravaloper1yafsywsluqdvlhtp30tcdhw496vg6ey3zs4u84)

\- [AM Solutions ](https://blue.kujira.app/stake/kujiravaloper1ly6xufjfuylky42ggcf79nvw5jmqzlkgq5drsg)🐋

**Transfer via IBC Transfer from Keplr's addresses to Kujira(Keplr):**

Only works with native network tokens - from Secret network only SCRT, from Cosmos Hub only ATOM, from OSMOSIS only OSMO, etc.

\- Secret Network --> Kujira: channel-22

\- Stargaze --> Kujira: channel-49

\- CosmosHub --> Kujira: channel-343

\- Osmosis --> Kujira: channel-259

\- Evmos --> Kujira: channel-18

\- Juno --> Kujira: channel-87

Important: In addition to USDC, it is better to use:

https://blue.kujira.app/ibc

and for the USDC from osmosis to kujira

[https://satellite.money/?source=osmosis\&asset\_denom=uusdc\&destination=kujira](https://satellite.money/?source=osmosis\&asset\_denom=uusdc\&destination=kujira)
