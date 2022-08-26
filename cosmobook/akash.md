# Akash

****

![](https://img2.teletype.in/files/93/1f/931fd987-b8cd-47a0-a37f-88ae3edf47a6.png)

## Akash

The first thing I want to say at once is that Akash has [a brilliant website](https://akash.network/ru). All the information is beautifully presented in several languages. To find out about the project, you just go to the official website where you can get all the information you need. But we dug a little deeper.

What is Akash? The official website tells us: Akash Network, the world's first decentralized open source cloud that accelerates deployment, scales, efficiency and lowers prices for high-growth industries such as blockchain and machine learning/AI.

This is essentially nothing new, but the key word here is decentralization. Decentralization of the Akash Network is necessary so that users can rent, for example, their server or part of its unused capacity without third-party censorship and intermediaries. And another important feature is auctionability, hence lower rental prices due to landlord competition.

Technically, Akash uses the core [Tendermint](https://tendermint.com/docs/introduction/what-is-tendermint.html); the deployment framework, [Kuberneters](https://ru.wikipedia.org/wiki/Kubernetes); the authentication framework, [SPIFFE](https://spiffe.io/); and the Linux distribution for the server agent, [CoreOS](https://ru.wikipedia.org/wiki/CoreOS). With Kuberneters, applications will be hosted in Docker containers for easier management and migration from other platforms.

### **Introduction to Akash** <a href="#hlj3" id="hlj3"></a>

Akash means "open space" or "sky" in ancient Sanskrit.\
The Akash network is a decentralized cloud marketplace where tenants buy cloud-class computing from providers without any permission.\
To understand how this is organized, I'll give you the answers to the questions from the off-site. A lot of things immediately fall into place:\
**How to use Akash?**\
You can get started directly from the site [command line](https://docs.akash.network/guides/cli) or from [the GUI](https://docs.akash.network/guides/deploy).\
Define your Docker image, CPU, memory and storage in the [deploy.yalm](https://docs.akash.network/readme/stack-definition-language) file. Set your price, get bids from vendors in seconds and choose the lowest price. Deploy your application without the need to install, configure or manage servers. The ability to scale your application with one to hundreds of containers is provided.\
**What is Akash Deployment Marketplace?**\
[Akash Marketplace](https://docs.akash.network/other-resources/marketplace) is where users rent computing resources from cloud providers before deploying a Docker container to the Akash container platform. Marketplace stores online records of requests, applications, rentals, and payments using the Akash Token (AKT).\
**What is the Akash container platform?**\
[The Akash Container Platform](https://docs.akash.network/other-resources/platform) is a deployment platform for hosting and managing [containers](https://docs.akash.network/other-resources/platform#containers) on which users can run any Cloud-Native application. Akash is built using a set of cloud management services, including [Kubernetes](https://kubernetes.io/) for orchestration and container management.\
**What is the cost of using Akash?**\
The cost of hosting an application using Akash is about one-third the cost of Amazon AWS, Google Cloud Platform (GCP), and Microsoft Azure. You can check real-time pricing using [the Akashlitics.com price comparison tool](https://akashlytics.com/price-compare).\
**How to use Akash?**\
If you're new to Akash, start with [the deployment guides](https://docs.akash.network/guides) and follow along. The Akash community has written several more advanced guides for learning Akash: [a guide for node operators](https://docs.akash.network/akash-nodes), [a guide for validators](https://docs.akash.network/validating/validator), [a guide for cloud providers](https://docs.akash.network/other-resources/archived-resources/build-a-cloud-provider), and several [guides for deploying various applications](https://docs.akash.network/guides) on Akash.\
**How is Akash different from other cloud platforms?**\
Decentralized cloud is a shift from owning and managing computing resources by the three big cloud companies (Amazon, Google and Microsoft) to a decentralized network of cloud providers using open source software developed by the community and creating open market competition with more providers.\
Similar to Airbnb, Akash is a marketplace for server hosting that gives you control over the price you pay and the included amenities (Akash calls them attributes). Akash provides application developers with a command line tool to lease and deploy applications right from the terminal. Akash leverages a huge market of underutilized resources sitting idle in 8.4 million data centers worldwide. Any cloud and container applications running in the centralized cloud can run faster and at lower cost in Akash's decentralized cloud.\
**Why is Akash different from other decentralized platforms?**\
Akash hosts [containers](https://docs.akash.network/other-resources/platform) where users can run any cloud application. There's no need to rewrite the entire internet in a new proprietary language, and there's no tethering that won't let you switch cloud providers. The deployment file is transmitted over a private peer-to-peer network isolated from the blockchain. Asset transfers occur outside the network over mTLS to ensure the security and performance needed by critical applications running in the cloud.\
**What is Stack Definition Language (SDL)?**\
You can define deployment services, data centers, requirements, and pricing parameters in a "manifest" file (deploy.yaml). This file is written in a declarative language called [Stack Definition Language (SDL)](https://docs.akash.network/other-resources/platform). SDL is a human-friendly data standard for declaring deployment attributes. The SDL file is a "form" for requesting resources from the network. SDL is compatible with the YAML standard and is similar to Docker Compose files.\
**How do I set up Networking for a container?**\
Networking - ensuring communication with and between workloads - can be configured using the Stack Definition Language[(SDL](https://docs.akash.network/readme/stack-definition-language)) file for deployment. By default, workloads in the deployment group are isolated - nothing else is allowed to connect to them. You can relax this restriction.\
**Do I have to close and recreate my deployment if I want to update it?**\
No. You can update a deployment. However, only some fields in the Akash stack definition file are modifiable. Image, command, args, env, and open ports can be changed, but compute resources and placement criteria cannot.

You also need to understand that Akash is the kind of project that is already aiming for mass-adoption. See how they prepare the user for their product from the ground up, starting with the basics: what a cryptocurrency wallet is and how to buy the platform's token[(here)](https://docs.akash.network/tokens-and-wallets/keplr).

### Incorporating AKT into the DPoS protocol <a href="#staking-akt-in-a-dpos-protocol" id="staking-akt-in-a-dpos-protocol"></a>

Validators manage nodes to secure AKT transactions on the network. However, only someone with the computing resources and technical expertise to [run](https://docs.akash.network/validating/node) an Akash node can become a validator.

The minimum system requirements that Akash [recommends](https://docs.akash.network/validating/validator) for authentication nodes include a 4-core processor, 16GB of RAM (storage), 256GB of SSD (storage) and Linux Ubuntu OS. Of course, better specs will equal better performance; these are relatively modest minimum requirements compared to blockchains like Solana, for example. In [Solana](https://docs.solana.com/running-validator/validator-reqs), validators require a 12-core / 24-thread processor, at least 128GB of RAM (256GB of RAM is recommended) and three separate stores (recommended) totaling 2TB (500GB for accounts, 1TB for book, 500GB for OS).

The frequency with which the consensus algorithm selects [validators](https://akash.bigdipper.live/validators?sort=votingPower\&dir=-1) to approve network transactions - and hence receive rewards - is proportional to the amount of AKT a validator steams. This creates a competitive environment among validators to acquire AKT on their own or from delegates.

Delegates delegate their right to receive rewards to a node operator (validator). This validator then shares the rewards with the delegators (in proportion to how much they delegated) and takes a commission on top. AKT token holders can delegate via the Keplr desktop wallet.

### The lack of decentralization in Web3 or why Akash <a href="#otsutstvie-decentralizacii-v-web3" id="otsutstvie-decentralizacii-v-web3"></a>

I decided to cover the problem of decentralization for the reader here, taking [Messari's article](https://messari.io/report/akash-solving-web3-s-centralization-problems) as a basis. It seems to me that this valuable material should be placed here.

There are two major issues affecting the sustainability and decentralization of Web3 projects:

1. Most of the underlying blockchain infrastructure, including nodes and validators, is hosted on cloud servers by several large technology companies.
2. The protocol interfaces and middleware are also typically hosted by the same cloud service providers.

Reliance on large cloud providers to host Web3 infrastructure has resulted in Web3 getting the same centralization issues as Web2. This seriously reduces the anti-fragility and censorship resilience of the protocols and creates numerous vulnerabilities and risks.

A closer look at the breakdown of nodes across the two main protocols reveals a lack of decentralization. In Ethereum, [65%](https://www.ethernodes.org/network-types) of all nodes are hosted in data centers. Of those nodes, [63%](https://www.ethernodes.org/networkType/Hosting) are hosted by just three major cloud providers (AWS, Hetzner and OVH) and 43% are hosted only by AWS. This means that Amazon could shut down nearly a third of Ethereum's nodes within minutes. For Solana, the exact breakdown of nodes by network type is unknown, but it is estimated that more than 95% of all nodes are hosted in data centers. That being said, [67%](https://www.validators.app/data-centers?locale=en\&network=mainnet\&sort\_by=asn) of the nodes are hosted by the same top three cloud providers as Ethereum. The services of these three cloud providers are also used by [64%](https://www.validators.app/data-centers?locale=en\&network=mainnet\&sort\_by=asn) of the active SOL stackers on the network.

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

In addition, many projects use large cloud providers to host their middleware and interfaces for websites and applications, creating another centralized point of vulnerability. If a project's interface, in which most users interact with network contracts, is hosted by AWS, it does not matter how decentralized the back-end protocol is, because AWS can simply disable the interface. A centralized interface also allows the project team to control how the user interacts with the protocol. Finally, using a centralized cloud provider exposes the protocol to the risk of failures depending on the provider's uptime, as was the case with dYdX last December.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

As much of the Web3 infrastructure resides on a few cloud providers' servers, the ability of large technology companies and governments to censor these protocols increases. In addition, this concentration increases the likelihood that regulators will seize [the opportunity](https://twitter.com/collins\_belton/status/1478120309332987905) to take the industry under their regulatory umbrella. This is why so many lawyers [are emphasizing](https://twitter.com/jchervinsky/status/1427652238101684231) the importance of decentralizing Web3 front-ends, as they represent a major attack vector...

Developers need access to a distributed, full-featured Web3 solution to deploy truly decentralized Web applications. The stack must include infrastructure projects that can provide a decentralized domain name system (DNS), computation for middleware and hosting interfaces, and data storage for backups.

Through multiple technology partnerships, Akash can provide access to [a full-stack decentralized solution](https://docs.akash.network/integrations/unstoppable-web-2.0). Akash collaborates and integrates with the blockchain-based DNS system, [Handshake;](https://handshake.org/) [Filebase](https://filebase.com/blog/filebase-and-akash-announce-partnership/), an S3-compliant object storage platform based on multiple decentralized storage networks; [Skynet](https://akash.network/blog/akash-network-and-skynet-labs-provide-a-full-stack-for-the-unstoppable-web), a hosting platform that provides decentralized storage and interfaces via Sia.

Akash gives users the ability to easily choose from a list of 60 (the number is steadily growing) [active providers](https://www.akashlytics.com/) the one they want.

Akash is not the only blockchain project trying to change the nearly half-a-trillion-dollar cloud computing market. Its other decentralized competitors include Dfinity (Internet Computer), Ankr and Cudos. Ankr and Internet Computer have a different approach to cloud computing than Akash. Meanwhile, Cudos almost completely replicates Akash.

### **Akash use options** <a href="#v3w5" id="v3w5"></a>

**Nodes**\
Akash is a great solution for hosting Proof-of-Stake (PoS) validator nodes, and currently hosts nodes for Helium, Osmosis, KYVE and many other projects. As a native Cosmos project, Akash has focused on streamlining the deployment of validator nodes for blockchain in the Cosmos ecosystem by releasing Cosmos Omnibus. Cosmos Omnibus is a standardized Docker image package that simplifies and standardizes node deployment for any Cosmos SDK-based blockchain on Akash.

In April, Akash unlocked persistent storage, which allows data to remain available for the duration of the lease, even after a power reset. Persistent storage is a feature available in most public cloud environments and is ideal for data-intensive workloads. With persistent storage, Akash can now host full blockchain nodes and database-driven applications. Support for more complex nodes, including THORChain and Solana nodes, is underway.

**Dashboards and middleware**\
Dashboards act as a bridge between users, developers, and applications. It allows users to interact with the blockchain and developers to create applications. The middleware also provides a friendly user interface and improves the overall user experience for decentralized applications and web applications. Akash can be used to host middleware such as API and RPC nodes, dashboards and blockchain explorers. In addition, each application and website requires a front-end, which can also be hosted on Akash.

**Miners**\
Considering the low price of Akash compared to mainstream cloud providers, it provides a good opportunity for miners to use it. While some traditional cloud platforms limit mining, miners use Akash to mine projects such as Monero, Chia and PKT Cash.

**DAOs**\
Akash provides an ideal hosting solution for DAOs. If a DAO has a website or application in need of hosting, it needs to designate one person to register with the centralized cloud provider. This will require the person's identity and credit card information. In addition to the loss of anonymity, this also leads to a human-key risk where one person can control the deployment for the entire DAO. With Akash, it is possible to create a multi-sig wallet so that multiple people can control the deployment, all without any KYC.

**GPUs**\
Akash plans to add a GPU market in the second quarter of 2022. This will enable the network to handle large amounts of data such as machine learning, artificial intelligence, rendering and cloud gaming. The new use cases opened up by GPUs in Akash will generate additional demand for the network.

A detailed draft of the roadmap update [_is here_](https://akash.network/ru/roadmap).

Akash network was launched in March 2021. In April 2022 there was a big update of Mainnet 3.0 (version [0.16)](https://github.com/ovrclk/akash/releases), which:

* Opened access to persistent storage. This functionality fully mimics the storage capabilities of public cloud environments.
* The ability to keep data available for the duration of their lease is a huge step forward for many deployment use cases. Future versions will look at the ability to retain data during a lease, which will add even more features. Check out the documentation [here](https://docs.akash.network/features/persistent-storage).

### **Akash Ecosystem** <a href="#z5ar" id="z5ar"></a>

Look at how many dappos are going to Akash, I was impressed:

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### **$AKT** <a href="#13hx" id="13hx"></a>

**Akash Token (AKT)** is a native platform token used as the primary means to manage, secure the blockchain, incentivize participants and a mechanism to store and exchange funds.

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption><p><a href="https://messari.io/report/akash-a-decentralized-approach-to-cloud-computing?referrer=grid-view">https://messari.io/report/akash-a-decentralized-approach-to-cloud-computing?referrer=grid-view</a></p></figcaption></figure>

At the time of genesis, 100 million AKTs were distributed in accordance with the distribution shown in the chart above, while approximately 289 million AKTs were scheduled for issuance as inflationary awards for stakers, originally set at 100% APR, which was to be halved every two years. The governance vote changed the halving to about every 3.7 months. According to Akash founder Greg Osuri, the protocol plans to reward cloud providers with issuances, though the feature will be implemented at a later date.

News not yet realized, but mentioned in the whitepaper: Akash plans to charge an "acceptance fee" for each successful lease. It will then channel this fee into a pool of rental revenues for distribution to holders. The fee is planned to be 10% for AKT transactions and 20% for other cryptocurrencies. Akash also plans to reward AKT steakers. Holders who steak for a long time will be eligible for larger rewards.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

### **Conclusions** <a href="#4vsq" id="4vsq"></a>

Akash is not intended to replace the centralized cloud computing industry, it will simply complement it. Cloud computing and Akash's entry into that industry are different things. Just as Airbnb is not destroying hotels, Akash is not destroying centralized data providers. Both Airbnb and Akash simply allow individuals to rent out unused capacity.

Akash may be able to attract cloud customers by offering pricing at times lower than the big three providers, as well as providing flexibility, no vendor lock-in, and control over the resources used for deployment. At a time when traditional enterprises are building crypto-environments and becoming more Web3 technology literate, Akash will be at the forefront of decentralized cloud computing with a functioning mainnet and a business model that eliminates inefficiencies on the supply side.

### **Links** <a href="#ixdt" id="ixdt"></a>

Website - [https://akash.network/ru](https://akash.network/ru)\
Twitter (ru) - [https://twitter.com/akash\_ru](https://twitter.com/akash\_ru)\
Forum - [https://forum.akash.network](https://forum.akash.network)\
Discord - [https://discord.gg/ewVh3mss](https://discord.gg/ewVh3mss)\
Vkontakte - [https://vk.com/akash\_ru](https://vk.com/akash\_ru)
