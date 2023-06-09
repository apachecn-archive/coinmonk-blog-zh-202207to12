# 跨链与多链——互操作性之战

> 原文：<https://medium.com/coinmonks/cross-chain-vs-multi-chain-battle-of-interoperability-467c17022fce?source=collection_archive---------10----------------------->

![](img/6c0868703e3667498acd1f5e340a884a.png)

Image from thenounproject.com

想象一下，如果您只能选择联系您的网络提供商的联系人，打电话会有多烦人和令人沮丧。你可能会问，管它呢？那正是我们对它的感觉。不得不翻遍电话簿来确认某人是否订阅了某个网络提供商，或者不得不在记下他们的号码之前不断询问某人的网络提供商是谁，这将是非常可笑的。

嗯，区块链技术的最早形式看起来就像这样。

在加密社区听到的最喜欢的短语之一是“确认你发送到正确的钱包地址。发送到错误地址的加密无法恢复。这个短语并不总是指不把代币放进陌生人的钱包里；这也意味着不要发送与你发出的令牌不兼容的链。只是说，“不要把基于以太网的令牌发送给 BNB 连锁店。”如果你要这么做，你的令牌可能会挂在区块链云中的某个地方——嗯，这是我编的，但你可能已经明白了要点。在很长一段时间里，区块链平台都是如此；创建的不同区块链平台无法相互通信；它们缺乏互操作性。

尽管区块链技术正在被接受，加密技术也很棒，但是一些问题仍然需要解决。

如果区块链技术提供了可以改善人类的解决方案，那么它至少应该是广泛可用的，并且能够无缝互操作。现在，这种互操作性消失了。

为了让这项技术在未来保持相关性，区块链的专家们意识到，他们必须找到缺失的部分，并设计一种方法将一个独立的链连接到其他链上。

当然，一些解决方案已经实现了区块链互操作性，更多的解决方案仍在探索中。然而，区块链技术目前享有的互操作性严重依赖于跨链和多链概念。

**什么是跨链？**

跨链是一个区块链概念，可以实现链之间的通信——这不是火箭科学。在加密货币的背景下，跨链有助于将令牌从一个本地链转移到另一个非该特定令牌本地的本地链。这样，主要由 Solana 链创建的令牌可以传输到 Avax 网络，同时保留其 1:1 的值。

然而，要使跨链可行，需要一个桥。

嘿！不要强调它；这些概念很容易掌握，你可以很容易地找到相关的例子来帮助你更好地理解它们。

> 交易新手？试试[密码交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)或者[复制交易](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)

桥的一个例子是连接不同位置的桥，即典型的现实世界中的桥。你一定知道水上桥梁是如何运作的？当一座桥架设在分隔两个区域的水体上时，就有可能进入以前无法进入的区域。与区块链的互操作性完全相同。

![](img/06e5bd81aff2a570a40a0eaeb5c7c4d2.png)

Bridges connect different parts and make them accessible to each other.

例如，以太坊以其高昂的汽油费而闻名(至少在它迁移到 [Eth 2.0](https://www.forbes.com/advisor/investing/cryptocurrency/ethereum-2/) 之前是如此)，任何希望在用代币进行交易时降低汽油费的人都可以通过一座桥，在那里汽油费被降至最低。这是可能的，因为桥使得以更少的气体供给移动到另一个链成为可能。

与过去相比，这是一个重大的进步，不仅对以太坊，而且对整个区块链技术来说都是如此。

关于桥梁对于区块链的互操作性是否必要，一直有[的争论](https://twitter.com/VitalikButerin/status/1479501366192132099?t=mJFN7TOGjNXL-EqcvxRrdA&s=19)。

人们发现，桥梁容易受到黑客攻击，此前已经有过无数次成功尝试。然而，说桥梁是失败的努力是不够的，因为事实并非如此。一个概念并不是完全不相关的，因为它有两个缺点。考虑到它是基于区块链技术，有很大的改进空间。

尽管桥使得从几个链的转移成为可能，但它们在某种程度上否定了 DeFi 背后的主要思想。这是因为大多数已知的网桥通常由监督网桥池的集中实体维护，这解释了为什么在这些平台上报告的攻击越来越多。

**什么是多链？**

多链是另一个支持互操作性并使多个区块链平台能够交互和通信的概念。就像跨链一样，它打算让任何区块链平台都可以从其他区块链平台访问。

![](img/88d357fc3b21cb8ba22d5cc283289bf4.png)

Multi-chain means a blockchain project can exist on multiple chains.

建立在多个链上的区块链项目称为多链。

多链支持跨多个链同时部署加密项目。这表明一个项目可能来自不同的区块链网络。

像 Arbitrum 和 Polkadot 这样的第 0 层网络允许许多[第 1 层](https://coinmarketcap.com/alexandria/glossary/layer-1-blockchain)链在其上发展并相互作用，从而使多链自然成为可能。

在加密项目中，多链令牌可能意味着它同时在 Sol 链、Eth 链、BNB 链和 Avax 链上构建/运行。该令牌可以存在于这些多个链中，同时在所有链中保持单个最大供应。

当前的多链加密项目是那些在 [EVM 兼容](https://support.token.im/hc/en-us/articles/4414713036313-What-is-EVM-compatible-chain-)链上的项目。这种 EVM 兼容性使得开发人员可以轻松地跨链构建可以轻松共存的项目。

支持多个链(多链)的令牌可以在不使用网桥的情况下跨所支持的链进行传输。

虽然本文中的大部分讨论已经解释了与 DeFi 的互操作性，但是互操作性是一个与整个区块链技术发展相关的概念。

**了解跨链和多链**

让我们通过这个假设性的比较来理解跨链和多链是如何工作的。

假设你在 A 银行开了一个账户，把钱存进去，然后收到一张借记卡，可以随时存取你的钱。但是，有一个限制，您只能使用 A 银行创建的 ATM。您的卡只能在 A 银行的 ATM 上使用；因此，如果你遇到 B 银行和 C 银行的自动取款机，你将永远无法使用它们。这说明了区块链最初是如何独立开发的，只打算与具有相同属性的链进行通信。

![](img/4590aa687c441d8f5e8e920ad5273018.png)

gif by giphy

随着时间的推移，有人决定设计一种可以与 A 银行、B 银行和 c 银行互操作的 ATM。然而，这些银行和各种借记卡之间的所有交互将只能通过专门构造的 ATM 来实现。这些自动取款机现在可以放置在关键区域。任何需要从 B 银行取钱的人都不需要寻找通常为 B 银行建造的 ATM，只要他们能够找到这些支持互操作性的专门设计的 ATM。持卡人现在可以做的不仅仅是使用银行的自动取款机，这是一个显著的进步。这是跨链背后的想法，也是为什么这种交易需要跨链桥来完成。

有些人已经意识到这种方法需要一些升级，并决定给它一个。他们可能会发现，在使用他们喜欢的银行卡之前，人们必须找到特殊的自动取款机。然后，他们开发了一个系统，使任何人只要有银行卡，就可以使用任何银行自动取款机存取钱。这意味着 A 银行的持卡人可以从 B 银行和 C 银行的自动取款机上取钱。B 银行或 C 银行的持卡人也可以这样做。银行之间内部检查和完成交易的能力使得处理取款变得非常简单和快速。这就是多链系统的功能。

我们走了多远？

传统上，创建 dex 是为了服务单个链(一个例子是 [Pancakeswap](https://pancakeswap.finance/) ，用于交换 BNB 链上的令牌)。由于最近的进展，我们现在有跨链指数，提供跨几个链的交易/互换。

这些跨链互换在分散的桥梁上成为可能，因为流动性提供者的存款形成了流动性池；就像普通的 DEX 一样。如果没有为跨链桥梁形成的流动性池，跨链桥梁将是不可能的，因为资产彼此之间将完全缺乏流动性。

雪崩桥、多链(以前称为 anyswap)和虫洞门户是众所周知的跨链平台和桥。当然还有 Xpollinate 跨越不同链的稳定硬币和其他代币的桥梁。

跨链桥可以加快链之间的交易，尽管有时交易可能需要一段时间才能完成。如果没有足够的流动性来完成互换，就可能出现这种情况。

多链是 cross-chain bridge 提供的更广泛的进步，但是它要求开发人员建立在 Evm 兼容的链上。

互操作性对区块链来说是一个胜利，因为这意味着数据可以无缝地跨多个链共享，这与过去的现实相去甚远。

目前，我们正在接受这项技术提供的东西，而且可以肯定的是，还会有更多的发展要跟进。

你现在可能会用不同的眼光看待 ATM 和桥梁，但这意味着你做了一些学习！