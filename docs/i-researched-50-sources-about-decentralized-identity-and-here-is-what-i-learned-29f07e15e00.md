# 我研究了 50 多份关于分散身份的资料，以下是我所学到的

> 原文：<https://medium.com/coinmonks/i-researched-50-sources-about-decentralized-identity-and-here-is-what-i-learned-29f07e15e00?source=collection_archive---------18----------------------->

我们现代生活的很大一部分发生在网上。因此，你需要一个身份在虚拟世界中代表你。如果你的虚拟身份是去中心化的呢？

![](img/220199fb531da2fb34cbd546d5b2479d.png)

Everything you need to know about Decentralized Identity — The next big thing in web3

**大家好，我是 Linh，Dreamerly(Twitter:**[**@ DreamerlyHQ**](https://twitter.com/DreamerlyHQ)**)的业务拓展。**

**这是我在 Twitter 上最初帖子的延伸:**

**Twitter 版本简短而甜蜜，而这篇文章则更深入地探讨了这个话题。如果你喜欢这篇文章，请考虑关注我们的推特(**[**@ DreamerlyHQ**](https://twitter.com/DreamerlyHQ)**)。这真的激励我在未来写更多酷和有趣的东西，所以谢谢你的关注！**

让我们开始吧！

# 你为什么要关心分散的身份？

我们现代生活的很大一部分发生在网上。因此，你需要一个身份在虚拟世界中代表你。当我们谈论身份，尤其是在线身份时，我们想到的是用户名、头像、关注者数量、你在网上分享的内容或任何将你与其他人区分开来的东西。这些信息实际上是存储在 Meta、Google 和 Twitter 数据库中的条目。

问题是:你并不拥有它。Meta，Google 和 Twitter 都有。

现在，大多数人已经知道了这个事实，但是不拥有你的数据有什么错呢？毕竟，我们需要工具来运行我们的日常生活，这些平台对我们来说仍然很好(大部分时间)。抱怨什么？

可能没什么，除了当我们被禁止访问该服务时(如果你曾经在 Reddit 上被暂停，欢迎加入！)，当他们的算法变得更不利于我们的利益时，或者当平台关闭时(你认为脸书会持续你的一生吗？).

我知道，我很极端。我们大多数人只是普通用户。我们遵守规则，我们不是机器人，我们不做违反政策的事情。但也是因为我们只是普通用户，当我们不拥有自己的数据时，我们会感到无能为力。大多数时候，我们是合规的用户，但偶尔，我们可能会无意中做一些可能会意外让那些平台认为我们有害的事情。而且由于你是普通用户，和平台打交道极其困难。正是因为有被平台意外伤害的风险，不拥有你的数据才成为一个问题。

这只是不拥有数据的第一件不愉快的事情。当然，这只是一种可能性，但接下来令人不愉快的事情不是概率，而是确定无疑的事情:那些平台(以及第三方)会利用你的数据来为他们的服务加油。我们不得不同意放弃我们的数据，尽管我们实际上并不想这样做！

接下来是安全问题。那些用户数据库太有价值了，成了黑客的蜜罐。在这一点上，我真的相信我的数据已经在某个地方被泄露了，只是不确定在哪里。还记得脸书-剑桥分析公司丑闻吗？数百万用户的数据被泄露，被黑客攻击的数据被用来向用户发送政治广告。

这还不是全部。该数据库不仅是集中式的，而且被每个网络孤立起来。脸书有一个版本的你，推特有另一个版本，Instagram 有另一个版本。虽然我在每个平台上都有不同的自己，这很酷，但我厌倦了一次又一次地重建我的个人资料和声誉。如果这些平台关闭或者我被封禁，我将失去我在那个平台上的所有东西。(事实上，我可以下载我在脸书的数据，但我能做什么呢？把这样的数据导入 Twitter？埃隆，我们能做到吗？)

好了，吼够了。是解决问题的时候了。

# 输入分散身份

我们能做些什么来解决这些问题？分散身份可能是一个很好的答案。

那么什么是去中心化身份呢？在深入研究去中心化身份在引擎盖下的工作机制之前，让我们对去中心化身份有一个高层次的了解。

web2 身份和 web3 身份的主要区别集中在两件事上:身份所有权和可移植性(另一个词是互操作性)。

身份所有权是分散身份最重要的特征。“分散”一词意味着所有权从集中的身份中分散出来，重新回到用户手中。

分散身份的第二个有趣的特点是可移植性，这意味着您可以使用您的身份无缝地访问不同的平台。

现在，让我们了解一下分散标识符(DID)是如何工作的。

目前，最被接受的 DID 标准是由万维网联盟(W3C)制定的。按照 W3C 的标准，DID 是一个 URI(类似于 URL ),可以解析(即查找)一个 DID 文档。让我们稍微停顿一下，仔细看看每个元素。

- URI: URI 和 URL 非常相似。它用于标识互联网上的逻辑或物理资源。

- DID 文档是包含与 DID 引用的主题(DID 主题)相关联的信息的文档。

- DID 文件存储在可验证的数据注册表中，该注册表可以是区块链或分散存储(如陶瓷网络)

-DID 基础设施中的最后一个组件是 DID 控制器，它控制(更改或更新)DID。DID 控制器有时可以做主语。

下图显示了 DID 的基础设施(来源:W3C)

![](img/f131de8ad44f0c88af7175081e8764d4.png)

The infrastructure of DID (source: W3C)

另一个分散的身份标准是可验证的凭证。DID 代表你的身份，VC 代表你的成就、证书和参与。例如，VC 可以是一个徽章，帮助 DAO 的成员证明他们对社区的贡献，从而获得更多的投票权。

除了使用 DID 和 VC 来创建分散身份之外，另一种创建分散身份的方法是将身份包装在一个令牌中，例如 NFT 或灵魂绑定令牌。该令牌将包含构成其所有者身份的数据。由于用户拥有这个令牌，他们可以使用它访问 web3 上的任何平台(可移植性)。

# 分散身份中的顶级项目

够理论了。让我们来探索致力于使分散身份成为现实的顶级项目。

**1/迪厅(**[**【disco.xyz/】**](https://disco.xyz/)**)**

虽然仍处于测试阶段，但 Disco 已经吸引了很多关注。它帮助用户在 web3 中创建他们的身份，他们可以带着这个身份访问生态系统中的任何应用程序和空间，所有这些都在一个“背包”中。

目前，Disco 将用户数据存储在陶瓷网络上，这是一种分散的存储方式，但随着时间的推移，将集成更多的存储解决方案。

最近，Disco 与 Guild 集成，允许使用 VCs 进行门控访问和定制角色。

**2/云杉(**[**spruceid.com/**](https://www.spruceid.com/)**)**

Spruce 正在为分散身份构建基础设施。它的 DIDKit 帮助开发者为他们跨平台的项目构建 did 和 VCs 功能。

Spruce 还提供了 Kepler，这是一个分散存储，是 DID 系统的重要组成部分。

该公司由 Y Combinator 和 a16z 出资。

**3/镜头协议(**[](https://lens.xyz/)****)****

**Lens Protocol 是一个去中心化的社交网络。透镜协议的核心有两个组成部分:**

**-简介 NFT**

**-项目建立在镜头之上**

**轮廓 NFT 是透镜协议中的主要对象。把这个 NFT 想象成你的便携式个人资料。这个 NFT 的特别之处在于能够向其发布出版物(内容)。它还包含您生成的所有帖子、评论和其他内容。**

**既然你拥有这个 NFT，你也就拥有了你在这个平台上生成的所有数据和内容(又名社交图),并把它带到新的平台上。**

**更重要的是，Lens 允许构建者在其上创建平台，从而创建一个丰富而充满活力的生态系统。在 Lens 上，用户可以上传他们在 Lenstube(一个 Web3 YouTube)上的视频，更新在 Lenster(一个 Web3 Twitter)上发生的事情，以及未来更多的事情。**

****4/Sismo(**[**【sismo.io/】**](https://www.sismo.io/)**)****

**Sismo 以灵魂绑定令牌(SBT)的形式帮助用户申领徽章。例如，徽章可以“捐赠给 Gitcoin grants”或“在 ENS DAO 中投票 2 次”。这些徽章可以帮助用户获得门禁服务或证明他们在社区中的声誉。**

****感谢您阅读至此。希望你学到了很多关于分散身份的知识。感谢任何评论和反馈。****

****如果你喜欢这个帖子，请考虑关注我的推特(**[**@ dreamerlyHQ**](https://twitter.com/DreamerlyHQ)**)****

> **交易新手？试试[加密交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)或者[复制交易](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)**