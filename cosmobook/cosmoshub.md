# CosmosHub

## Cosmos ecosystem and Cosmos Hub

### **What is Cosmos?** <a href="#jkzn" id="jkzn"></a>

Cosmos is not a blockchain. It is decentralized network of independent and interacting blockchains called zones in the ecosystem. These zones run on Tendermint and communicate with each other through IBCs using hubs.

#### **Concept**

The Cosmos network operates on three different levels.

1\. Network layer. It allows transaction confirmations and other consensus messages to interact with the hub's blockchains.

2\. Consensus layer. It arranges nodes according to validators' decisions to add new transactions.

3\. Application layer: responsible for updating the state given a set of transactions, i.e. processing transactions..

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
All levels is combined by toolkits and applications with opensource code. For example, Tendermint connects the network layer and the consensus layer in a ready-to-use scheme that works automatically. This saves developers time and resources because they only work with app promotions.

### **Tendermint**

Tendermint is a solution that combines the network and consensus layers of the blockchain into a common engine, allowing developers to focus on application development rather than the complex underlying protocol.

Technically Tendermint can be described as a low-level protocol that performs the functions of a peer-to-peer network protocol and is responsible for the consensus algorithm. At the same time, it is optimized to solve the problem of fault tolerance of Byzantine generals (i.e. to find consensus) in distributed applications and for processing data in a large number of nodes (nodes).

\*_Byzantine fault-tolerance problem (hereinafter referred to as BFT) - in simplified form, this is the problem of finding consensus between network nodes, provided that a certain number of nodes are “fraudsters”_

Jae Kwon began working on the creation of a BFT protocol in 2014. On it could run a system of hundreds of nodes with trustless access and PoS as a protective mechanism. After all the necessary settings were made by 2018, the launch of the Cosmos network took place.

Validators in the network are chosen randomly in proportion to their stack share of the total number of coins cloned (i.e., in a perfectly standard way).

\*\* _Briefly: Tendermint acts as a network layer protocol, allowing nodes to communicate with each other and to come to a consensus. The consensus is based on the BFT model, while security is provided by the PoS mechanism. The principle and peculiarities of Tendermint operation are described in details and not very complicated_ [_here_](https://blog.cosmos.network/tendermint-explained-bringing-bft-based-pos-to-the-public-blockchain-domain-f22e274a0fdb)_._

Key features of Tendermint that make it a competitive blockchain mechanism:

1\. It can be applied to both public and private blockchains. If the application built on the engine determines that validators are elected based on ownership share, then the blockchain will be a PoS. But if developers introduce pre-authorization for validators, the blockchain will become private;

2\. High performance. Tendermint can process up to 1000 transactions per second;

3\. Instant finalization. This means that users can be sure that their transactions will be considered complete and final as soon as a block is created (which is not the case with Proof-of-Work blockchains, where a block is considered final only after a certain number of blocks are confirmed after it);

4\. Security. If a fork does happen, there is a way to determine responsibility. By a fork here we mean the simultaneous creation of several blocks, as a result of which the network is like a "branching". You can read more about this [here].(https://docs.tendermint.com/master/spec/light-client/accountability/)

The Tendermint engine connects to the application layer using a protocol called Application Blockchain Interface (ABCI). The protocol can be built into any programming language, so developers have plenty to choose from.

![](https://telegra.ph/file/c4983df170166b0d67be4.png)

Although Tendermint reduces blockchain development time manifold, creating a secure ABCI application from scratch remains a daunting task. CosmsSDK was developed to simplify this task as much as possible.

### **CosmosSDK**

CosmosSDK is an open-source framework for creating permissionless PoS blockchains like CosmosHub, or permissioned Proof-of-Authority (PoA) blockchains.

![](https://telegra.ph/file/ea2a0fbc8e126123aa744.png)

The Cosmos SDK aims to allow developers to create their own customized blockchains that are compatible by default with other blockchains in the ecosystem, using pre-made modules and toolsets. In doing so, each developer can create a new module and it will be available to all other developers.

Features of the Cosmos SDK

1\. The consensus engine available by default when developing on the Cosmos SDK is Tendermint, currently the best BFT solution.

2\. The use of modules when creating an app-chain (an app-chain is a blockchain created for a separate decentralized application). All modules are in the public domain and their number is only growing.

3\. The Cosmos SDK was created by genuine experts in blockchain technology, is constantly being improved and is a secure environment for blockchain creation.

### **Стейкинг**

Stacking is the process of blocking a token to secure a public blockchain.

A validator is a node that is responsible for creating blocks, thereby protecting the network and processing transactions. Validators are rewarded for their work, which can consist of block finder rewards, transaction fees, and delegator commissions.

A delegator is any user who has sent (delegated) their tokens to any validator. The delegator receives rewards, proportional to their share of tokens, from the total number of tokens of the validator, and pays the validator a small commission for its services (the commission is set by the validator itself and usually does not exceed 5% of the delegator's reward).

To avoid cheating, the Validator that publishes incorrect data to the blockchain is penalized financially, losing some of its tokens. This is called slashing.

_We put liquid steaking in Cosmos network in a separate publication, there is another little sheet =) You can read it here. (russian language)_

### **Slashing**

Slashing is a "punishment" for the validator, which consists of confiscating a portion of his tokens. What percentage of tokens will be "slashed" depends on the breach committed by the validator and the threat to the safety of other network participants. This is not only a financial incentive for the validator to perform his duties in good faith, but also a measure that forces validators to "risk their own skin. At the same time, it's what motivates delegates to choose validators more carefully, since they too risk losing some of their tokens.

There are two types of events that lead to slashing:

**- Slashing 0,01%** can occur if the validator is offline for too long. Idle time is fixed if the validator does not sign at least 500 blocks out of the last 10,000 blocks.

In addition, the validator is dropped from the consensus and does not receive a block reward for at least 10 minutes (the term jail). Once the problems are fixed, the validator can re-join the validator set by sending an unjail transaction.

![](https://telegra.ph/file/f6a5f216f13d513987a2b.png)

\- **Slashing 5%** can happen if the validator signs two different blocks at the same time. This malfunction is harder to predict and results from poor operating practices or outright malicious intent on the part of the node operator. In addition to the 5% token, the validator loses the right to offer blocks and receive remuneration without the possibility of unlocking (effectively being removed from the validator set forever). All delegators of a given node receive their tokens back, the anbond period (i.e., the time to return tokens from stacking) is 21 days.

![](https://telegra.ph/file/97e89b3f303117a84a471.png)

### **IBC**

The Inter-Blockchain Communication Protocol, or IBC, is a framework that allows zones to cross-chain communication without establishing trust assumptions from a third party (i.e., without using bridges, for example), it can be compared to the TCP/IP protocol in traditional networking technologies. Interacting networks agree to trust each other's security model and use a distributed messaging standard to communicate and verify changes in network state. Thus, the IBC model inherits the lowest of the security of the networks involved in the message exchange (\*_ meaning that if, say, the security of one network is 10/10 and the other 8/10, the security of the IBC model will also be 8/10_).

The establishment of such interaction is resource-intensive for both networks. When one network initiates the sending of a message to another network, the public relayer  transmits a proof of request message to the other network. The network receiving the message validates this proof using a light client, which reads the state of the sending network and writes a copy of this state to its own registry. This direct verification process guarantees the receiving network that the request was indeed valid, and only then does the state of the receiving network itself change.

IBC model has several important features (necessary trade-offs) because of the optimization towards security:

The receiving network is forced to assume that the transactional request has been finalized (finalized) in the network sending the message (request). Forks and block reorganization, which are common for probabilistic finality (e.g., the ether network), would destroy the fundamentals of the IBC security model. Therefore, IBC is compatible only with consensus mechanisms that have a guarantee of finality, such as Tendermint. As a solution, so-called "pegzones" can be used to set a finality threshold when interacting with a probabilistic network. But such a solution complicates the system and thus creates additional vectors for an attack on it.

The IBC model is too expensive for blockchains with low bandwidth and expensive blocks. But the Cosmos ecosystem does not have this problem, because IBC was originally developed to work with blockchains built with the Cosmos SDK, where IBC modules work at the network level, not at the smart contract level. In addition, it allows networks within the Cosmos ecosystem to redirect the cost and responsibility of recording the state of other ecosystem networks from applications to network validators.

Transaction costs for messaging between networks are borne by retransmitters, not users. Repeaters are often managed by validators who are motivated to keep both (sending and receiving) networks running. The economic model of IBC makes it rational to coordinate between different repeaters so that at the same time only one repeater serves one IBC channel. If a situation arises where none of the repeaters serves the channel, then the message is "stuck" until there is a serving repeater. Although this fact has no effect on the security of either the receiving or sending network, the viability of an IBC can be temporarily reduced for this reason. In order for IBC messaging to completely break down, one-third of all validators would need to stop working.

A schematic of the IBC is shown in the figure below (source [here])(https://0xpostman.medium.com/part-2-cross-chain-security-models-compared-c4f91107cad4))

\* _The green arrows show the validator check stages of the transaction, and the purple ones show the transaction path (or any other cross-chain message)_

![](https://telegra.ph/file/de18cb6908699b3bf74e9.png)

Essentially, IBC transactions are packets of information that are transferred from one zone to another by publishing Merkle-proofs (more [here](https://ethereum.org/pt/developers/tutorials/merkle-proofs-for-offline-data-integrity/)) as proof that the information was sent and received.

In order for the receiving network to verify this proof, it must be able to keep track of the sender's block headers. This mechanism is similar to that used by [sidechains](https://blockstream.com/technology/sidechains.pdf) (more info [here](https://forklog.com/cryptorium/sidechains-faq/)), which requires that two interacting networks know about each other through a bidirectional flow of existence-validating transactions.

The IBC protocol uses two types of transactions: `IBCBlockCommitTx` , which interact with [hash](https://academy.binance.com/en/glossary/hash) the last block of any zone, and `IBCPacketTx,` which contain data about the legitimacy of the information packet and the sender's application.

For example, to update a "Zone1" block to "Hub" (or "Hub" to "Zone2"), an IBC BlockCommitTx transaction must be placed on "Hub" with a "Zone1" block hash (or on "Zone2" with a "Hub" block hash). (More information on transactions in the whitepaper: [тут](https://v1.cosmos.network/resources/whitepaper#ibcblockcommittx))

![](https://telegra.ph/file/97bd3b1e1bd282435bf2b.png)

To summarize: IBC allows interacting networks to function like read-oracles for each other. The security of such a model is resource-intensive, but allows the networks to interact without the need for a third party trusted party. For this reason, IBC is a very popular model and is always cited as one of the alternatives among some other messaging models.

IBC was launched in March 2021, and as of now (July 2022) it is enabled on 49 networks, and there are currently over 2.5M transactions per month using IBC (you can see [here](https://www.mapofzones.com/?testnet=false\&period=720\&tableOrderBy=ibcVolume\&tableOrderSort=desc)).

### **Peg-зоны**

Peg-зона — это блокчейн на основе учетной записи, который соединяет зоны внутри Cosmos с внешними блокчейнами, такими как Биткоин или Эфириум. Необходимость в них возникает, т.к. Cosmos использует детерменированную финализацию, а, например, Ethereum пробабилистическую.

![](https://telegra.ph/file/1c83c9b2998526787f661.png)

Компоненты, которые используются для взаимодействия внешних блокчейнов и Cosmos:

1. Смарт-контракты Ethereum, выступающие в качестве хранителей активов, способных взять на себя ответственность за собственные токены Ethereum и выпускать собственные токены Cosmos.
2. Witness (свидетель, оракул): Компонент свидетеля свидетельствует о событиях в Ethereum. Он ожидает 100 блоков, порога окончательности, и реализует эту псевдофинальность. Он запускает полную ноду Ethereum, чтобы подтверждать изменения состояния в Ethereum, отправляя `WitnessTX`в peg-зону. Здесь используется общая модель безопасности, валидаторы Cosmos Hub также в качестве свидетелей зоны привязки.
3. Peg-зона представляет собой блокчейн-переводчик, построенный на Tendermint. Она позволяет пользователям выполнять и запрашивать транзакции. Именно таким образом Cosmos соединяется с Ethereum.
4. Авторизующая сторона (signer на схеме) подписывает сообщения, используя схему secp256k1. Компонент signer генерирует подписи secp256k1 через `SignTx`сообщение и отправляет его в зону привязки для ретрансляции транзакций для проверки в смарт-контракте по конвейеру.
5. Relayer : компонент ретранслятора передает массив транзакций, подписанных компонентом Signer, и отправляет их в смарт-контракт Ethereum.

### **Interchain Security (ICS)**

Один из доводов, которые в спорах о том что лучше polkadot или cosmos, в пользу польки — наличие модели shared security (почитать можно [тут](https://wiki.polkadot.network/docs/learn-security)). Кратко: все парачейны (так в польке называют блокчейны) используют общую безопасность, при этом Polkadot гарантирует безопасность всех блокчейнов в сети и что любые взаимодействия между ними выполняются корректно. Различия между традиционной изолированной безопасностью и общей безопасностью хорошо продемонстрирована на схеме. Слева модель с традиционной (изолированной) безопасностью — именно такая сейчас в Cosmos. Справа модель с общей безопасностью, как в Polkadot...и как будет в Cosmos.

![](https://telegra.ph/file/8050d53cf4ef190181ea2.png)

У Cosmos на данный момент за безопасность (создание блоков) отвечают валидаторы каждой зоны по отдельности, но в 3м квартале 2022 планируется к введению технология Interchain Security (межблокчейновая безопасность). Это позволит пулу валидаторов, например, Cosmos Hub создавать блоки для молодой зоны, при этом механизмы наказаний за длительный автономный режим, либо за двойные блоки остаются как для "донорского" хаба, а атака на блокчейн становится экономически нецелесообразной (т.к. выше цена и количество застейканных токенов). Важными особенностями является то, что для расшеривания безопасности используется IBC, а ICS не обязателен для каждой зоны.

Несмотря на то, что введение технологии уже анонсировано, схем и деталей пока нет. Известно лишь то, что в первой версии будут использоваться все валидаторы донорского чейна, а далее включат возможность частичного донорства (https://github.com/cosmos/gaia/blob/main/docs/interchain-security.md).

### **CosmosHub**

Для того, чтобы не соединять каждый новый блокчейн со всеми уже существующими напрямую через IBC, Cosmos предлагает модульную архитектуру, в которой существуют обычные гетерогенные блокчейны – зоны, а также хабы – блокчейны, специально предназначенные для соединения зон друг с другом.

Первым хабом, запущенным в CosmosNetwork, является CosmosHub. CosmosHub — это Proof-of-Stake блокчейн общего назначения, собственный токен которого называется ATOM.

Cosmos Hub является реестром транзакций экосистемы, благодаря чему токены могут напрямую пересылаться между зонами по протоколу IBC. CosmosHub – это центральный блокчейн экосистемы Cosmos. По сути, с него и началась вся экосистема.

![](https://telegra.ph/file/bd28480cc4a5b3e2843e3.png)

Ссылка на рисунок [тут](https://mapofzones.com/?period=720\&testnet=false\&tableOrderBy=ibcVolume\&tableOrderSort=desc\&zone=cosmoshub-4\&fullscreen=true)

Разработка началась аж в 2014 году, концепция Cosmos появилась в 2016 году, а уже 13 марта 2019 года CosmosHub вышел в мэйннет (есть даже запись трансляции запуска [тут).](https://www.youtube.com/watch?v=OALEhpn7ccM)

![](https://telegra.ph/file/79404f91631c8ae87a048.png)

Нативная монета сети Cosmos – Atom.

Она имеет три основных варианта использования:

1\. Оплата пользователями комиссий за транзакции.

2\. Участие в управлении CosmosHub.

3.Стейкинг.

Токены ATOM были распределены на сид-раунде (5%), по 10% досталось Tendermint Inc. и, а 75% разлетелись за 30 минут в рамках первичного предложения монет (ICO) в 2017. Стоимость 1 Atom составила 10 центов, выручили 17 млн. Мы не будем высчитывать сколько и кому досталось токенов (хотя белой завистью радуемся за тех, кто сделал с 10 центов хотя бы 10 баксов и рука не дрогнула).

На данный момент общее предложение составляет 302347059 ATOM, максимальное предложение не ограничено. Это связано с тем, что вознаграждения TendermintCore выплачивается стейкерам новыми монетами. При этом уровень инфляции корректируется в режиме реального времени в зависимости от суммы монет в стейкинге и количества стейкеров. На момент написания этой статьи она составляла 12.4%. Актуальную инфу можно посмотреть в [дашборде](https://monitor.bronbro.io/d/cosmos-stats/cosmos-stats?orgId=2\&refresh=5s) Bro’n’Bro.

### **Ссылки:**

Cosmos whitepaper: [тут](https://v1.cosmos.network/resources/whitepaper)

Tendermint: [тут](https://docs.tendermint.com/)

IBC: [тут](https://ibc.cosmos.network/)

Peg-зоны: [тут](https://blog.cosmos.network/the-internet-of-blockchains-how-cosmos-does-interoperability-starting-with-the-ethereum-peg-zone-8744d4d2bc3f)

Подробнее о слэшинге: [тут ](https://medium.com/p2peconomy/slashing-in-cosmos-network-bbbaff949ee5)и [тут](https://docs.cosmos.network/master/modules/slashing/)

### Кошельки и дашборды экосистемы Cosmos <a href="#yine" id="yine"></a>

\*_Опять же, чтобы не удлинять нашу огромную простыню, полный обзор кошельков мы вынесли в отдельную публикацию, с которой вы можете ознакомиться тут, здесь же будет лишь небольшой обзор самых популярных кошельков - Keplr и CosmoStation._

#### **Кошельки**

Крипто-кошельки хранят ваши личные ключи и предоставляют пользователю доступ к собственным активам. Существует множество различных типов крипто-кошельков - от мобильных приложений и веб-кошельков до аппаратных кошельков.

#### **Keplr**

![](https://telegra.ph/file/83bf46d303d26af59b14a.png)

Keplr быстро стал основным кошельком для экосистемы Cosmos, и стейкать с помощью кошелька и панели мониторинга Keplr очень просто (полное [руководство](https://antropocosmist.medium.com/%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C%D1%81%D1%8F-%D0%BA%D0%BE%D1%88%D0%B5%D0%BB%D1%8C%D0%BA%D0%BE%D0%BC-keplr-462d430615b3)). Keplr предлагает приложение для мобильного кошелька для iOS и Android, а также расширение для браузера, похожее на Metamask, которое является самым простым способом безопасно начать стейкать. В дополнение к браузерному расширению Keplr предоставляет простую [панель мониторинга](https://wallet.keplr.app/) для просмотра доступных токенов, балансов застейканных монет и вознаграждений в более чем 20 сетях, которые он в настоящее время поддерживает. Cosmos chains также может интегрировать дашборд [управления стейкингом](https://wallet.keplr.app/#/dashboard), чтобы пользователи могли стейкать токены в своих собственных экосистемах.

В соответствии с дорожной картой в 2022 году, Keplr планирует несколько улучшений интерфейса, что сделает и без того один самых лучших пользовательских интерфейсов еще лучше. Например, одним из таких предстоящих улучшений является добавление раздела "валидаторы".

Выбор правильных валидаторов очень важен, и новички в Cosmos могут не знать, каких из них выбрать, поэтому Keplr хочет помочь валидаторам, которые активны, получить значительное количество голосов. Команда планирует сделать это, обновив страницу валидатора и предоставив полезные описания, благодаря которым пользователям (потенциальным делегаторам) будет легче определяться с выбором валидатора. Также будет реализована возможность общения между валидаторами и делегаторами, что должно простимулировать их более тесное взаимодействие. Различные ресурсы для стейкинга[ на Keplr можно найти здесь](https://keplr.crunch.help/).

Подключить устройство Ledger можно по этой [инструкции](https://support.ledger.com/hc/ru/articles/4411149814417-%D0%9A%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-Keplr-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81%D0%BE-%D1%81%D1%87%D0%B5%D1%82%D0%B0%D0%BC%D0%B8-Cosmos-ATOM-%D0%B2-Ledger?docs=true) от производителя.

#### **Cosmostation**

![](https://telegra.ph/file/6a6f2c24f559dc9f894ae.png)

Cosmostation - это решение, предоставляющее мобильный кошелек для удобного стейкинга прямо с вашего телефона, а также веб-кошелек, который позволяет подключать и подписывать транзакции с вашего аппаратного кошелька. Как давний инвестор в экосистему Cosmos, Cosmostation заработала прочную репутацию за предоставление отличной поддержки конечных пользователей с помощью таких проверенных продуктов, как Cosmos Explorer [_Mintscan._ ](https://www.mintscan.io/cosmos)Cosmostation также поддерживает более 30 сетей, предоставляя пользователям множество вариантов использования.

Cosmostation также имеет множество [руководств](https://www.cosmostation.io/files/cosmostation\_guide\_web\_en.pdf) и ресурсов поддержки, которые помогут вам, если вы застряли. Видеоруководство по установке мобильного кошелька - [тут](https://www.youtube.com/watch?v=pMzrOypmTOk). Видеоруководство, как стейкать с Cosmostation - [тут](https://www.youtube.com/watch?v=tWQOlDm1i74\&t=43s).

Если вы хотите выбрать различных валидаторов, вы можете увидеть их историю, активность и время безотказной работы прямо из раздела валидаторов на [Mintscan](https://www.mintscan.io/). Есть видеоруководство, как выбрать валидатора -[тут](https://www.youtube.com/watch?v=f44SAnke1hk) и [тут](https://www.youtube.com/watch?v=lX1QY4mFC6E). В конце этого года Cosmostation запустит расширение для браузера. Чтобы начать стейкать через свой мобильный кошелек, скачайте [Cosmostation для Android](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion) или [iOS здесь](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion).
