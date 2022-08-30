# Nym Network

![](https://img2.teletype.in/files/90/be/90be1283-ddff-49ca-bbe1-ed32730189cd.png)

## Nym Network

Based on the team's own definition - "Nym is a decentralized and tokenized infrastructure that provides users with full privacy at both the network and application levels. Current data encryption models can protect/hide the content of a user's network activity, but they cannot do the same with metadata about who the user interacted with and when. In turn, Nym protects both content and metadata, making it impossible for a third party to associate a specific network activity with any user device.

Nym includes two main components:

1\. Decentralized mixnet, is used to protect users' network traffic and is an improved version of models such as VPN and Tor.

2\. A system of tokenized credentials, provides privacy at the application level and allows users to access the mixnet.

NYM's native network token serves a utility function and is used to pay for conducting various network transactions, as well as to reward mix-node operators, validators and service providers.

### **Nym network architecture**

![](https://telegra.ph/file/575d48c671a4a3c33e742.png)

Users (in the figure Alice, Bob and Carol) access the services they want securely and privately through the client software (in the figure client app(js)). This software allows users to create credentials and then send packets of information to the Nym mixnet.

Validators distribute partial credentials ( _described in more detail in the next section_) to users, generate new blocks, and maintain synchronization with other blockchains that require privacy.

Mixnet is a network of mixnodes where information packets are "mixed" and thus privacy at network level is provided (i.e. third parties will not be able to identify who is communicating with whom).

Gateways (in the figure gateways) - act as a buffer to store client messages in case the client temporarily goes offline.

Service providers (in the figure service providers) are applications that use Mixnet. Service providers can run on their own third-party blockchain.

Nyx Blockchain (aka Nym Blockchain) was originally only used to run CosmWasm smart contracts that track the topology of the Nym network, as well as vesting contracts and the NYM token itself.

However, right now, Nyx Blockchain is an open smart contract platform, and any user or developer can run their CosmWasm smart contracts on it.

Identity providers (not shown in the figure) are providers that can verify attributes encoded in Nym credentials at the user's request.

Security guards (mix guards, not shown) verify that clients have valid credentials to use the Nym network and provide additional protection for the network against attack and censorship.

### **Nym Mixnet operating principle**

1\. A user contacts a service provider to perform a certain task. The service can be either paid (the user pays the service provider) or free, but in either case a small commission is charged to reward validators and mix-node operators.

2\. The user collects attributes required by the service provider (e.g., the user's age or nationality). If the service provider requires more "secure" verification of the user, this can be done through various identity verification services (such as when registering on coinlist). The user then passes these attributes in encrypted form to the validators. The validators generate and sign partial credentials and pass them back to the user. The client software collects the received partial credentials and generates the credentials required by the service provider and the mixnet guards. Because the client software re-randomizes the credentials, they cannot be associated with the validators that signed the credentials and hence the user remains anonymous_(at least that's my understanding_).

3\. The user then presents credentials to the Guards. Guards direct user traffic to the mixnet (while checking the current network bandwidth and protecting users from denial of service attacks). Thus through mixnet, user credentials reach the service providers while failing to associate the data with its sender because mixnet reflects the data with a random delay and hides the traffic.

4\. Next, according to the mix-mining algorithm, rewards are distributed to members of the Nym network.

### **Mix-mining awards**

Mix-mining is an algorithm that is a mixture of PoW and PoS. Mix-nodes are rewarded for doing computational work related to providing privacy (a kind of PoW). And at the same time, both mix-node operators and validators stack their Nym tokens, and if they perform improperly, some of those tokens will be withdrawn (PoS). They also receive rewards for stacking. Any user can delegate his tokens to a certain node and get rewards for that.

Full Whitepaper [https://nymtech.net/nym-whitepaper.pdf](https://nymtech.net/nym-whitepaper.pdf)

A simplified version of [https://nymtech.net/nym-litepaper.pdf.](https://nymtech.net/nym-litepaper.pdf)
