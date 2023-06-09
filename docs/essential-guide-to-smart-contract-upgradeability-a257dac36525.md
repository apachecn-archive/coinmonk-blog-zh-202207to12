# 智能合同可升级性基本指南

> 原文：<https://medium.com/coinmonks/essential-guide-to-smart-contract-upgradeability-a257dac36525?source=collection_archive---------1----------------------->

本文假设您对以太坊开发工作流有所了解。即智能合同部署、地址和 EVM 等概念。

# 你为什么要在乎？

智能合同是对 EVM 的书面纲领性说明。然后，EVM 会在适当的时候执行它们(例如，在用户进行 RPC 调用时)。向 EVM 发出这些指令的过程称为部署。这些指令是作为区块链交易的一部分给出的，该交易最终被添加到块中并达成共识。智能合约部署是非常必要的，因为没有它，他们将非常不安全，不适合处理用户资金。这样，区块链中块的不可变性质使得契约部署也是不可变的。智能合约一旦部署就不可改变，并且不能进一步修改。以太坊和其他 EVM 兼容的区块链确保每当我们部署智能合约时，都会进行新的部署。即使您再次部署相同的合同，也只会进行新的部署。

![](img/b320019b8d31181465c7c4702d4ac733.png)

Smart contract, fancy name for solidity code

![](img/795258c9fb49ee97b893e5d50723b806.png)

Credits: [me.me](https://me.me/i/its-not-a-bug-its-a-feature-ff25911c48334cc884cef01207cddf48)

智能合约只不过是程序员编写的可靠代码。以太坊的开发工作流程在很多方面与传统的开发工作流程有很大的不同，因为 EVM、区块链和 solidity 的设计方式不同。通常要特别注意抵消智能合约部署的不变性。尽管如此，bug 确实会像在传统的 web2 项目中一样悄悄出现。可以肯定地说，web3 项目中的错误会比 web2 项目中的错误造成更大的损失。

当在智能合约部署之后识别出这样的错误时，项目背后的团队需要一种方法来修复它。该团队可能会在将来提出一个新的特性，为此他们需要更改智能合同。在这种情况下，我们需要一种升级智能合约部署的方法，这种方法在设计上是不可变的。(请注意，像 Uniswap 这样的一些备受推崇的项目并不使用可升级的智能合约作为向其用户保证其协议的当前版本将继续以相同的方式运行直到永远的方式。即使他们发布了新版本的协议，旧版本仍在使用，并且升级对用户来说是可选的。)在升级智能合约时，我们需要确保只有合约的逻辑发生变化，但存储中的信息保持不变。将一个智能合约的存储迁移到另一个智能合约本身就是一场噩梦。我们将通过一些花哨的稳固步法来避免这种情况，在下一节我们将看到如何避免。

升级智能合约的另一个原因是保持已部署智能合约的地址不变。一旦你的项目变大，那么多的第三方客户连接到你的智能合同，改变每个人的地址将是一个挑战。

# 代理模式挽救了局面

代理模式是广泛用于构建可升级智能契约的模式。在代理模式中，有一个代理智能契约和一个实现智能契约。代理智能协定是用户对其进行所有 RPC 调用的协定。代理契约只是存储实现契约的地址，并将所有调用中继给它。

# 委派电话📞:救生帮助热线

代理模式的核心是 DELEGATECALL EVM 操作码。当协定 A 使用 DELEGATECALL 调用协定 B 时，调用的函数在 A 的上下文中执行。由函数调用完成的对智能协定存储的读取和写入会影响 A 的存储，而不会影响 B。全局变量(如 msg.sender)将与 B 中函数内的 A 的调用方相同。与调用 EVM 操作码相比，这更容易理解。当契约 A 使用 CALL EVM 操作码调用 B 时，在 B 中调用的函数中的读取和写入会影响 B 的存储。契约 B 中的函数调用内的全局变量 msg.sender 将是契约 A 的地址。将 DELEGATECALL 视为契约 A 完全信任契约 B，并将一切委托给它。

![](img/b7283c8b7c857dee194d0ddbdf839492.png)

Version 2 is the active implementation here and it can be changed

委托调用对于代理模式是非常必要的，因为它允许我们使用实现契约的部署代码和代理契约的存储。当我们需要升级我们的智能合约时，我们只需将代理合约中的实现合约的地址更改为新智能合约部署的地址。一旦完成，代理契约将开始将所有 RPC 调用转发给新的实现，同时将所有内容保存在其存储中。

# ERC1976:代理标准

随着代理成为智能合约开发中的一个常用名称，围绕它开发了一些标准来保持事物的互操作性。ABI 是智能合约如何让其他人知道它实现了什么功能，以便任何其他方可以使用这些信息来调用这些功能。在使用代理模式的情况下，我们将与 ABI 对我们没有用的代理契约进行交互。我们需要实现契约的 ABI 来进行函数调用。如果不同的代理契约以不同的方式存储实现地址，则检索实现地址可能是一个挑战。ERC1967 引入了在代理契约地址中存储实现契约地址的标准。仅知道您正在与代理交互就足以找出实现契约地址并获得它的 ABI。Etherscan 可以让您使用代理模式与智能合约进行交互，只要它遵循这个标准。Open Zeppelin 实现了这个代理标准，他们的一些代理契约也继承了这个标准。我强烈建议在你的代理合同中遵循这个标准。

# 代理管理员:负责的典狱长

如您所见，任何人都不能更改代理契约的实现地址。一个恶意者可以简单地把它变成一个将所有资金转移给他的实现🤑。有一个代理管理员的概念，这是唯一允许更改实施合同地址的帐户。在 Open Zeppelin 的代理部署插件实现中，默认情况下，管理员是部署代理契约的地址。管理员可以更改，但只能通过管理员帐户。

# 透明代理模式:更安全的选择

当代理和实现契约之间的函数签名存在冲突时，代理模式会遇到一个漏洞。代理契约需要有自己的功能来升级实现智能契约地址和一些其他目的。如果代理契约中的函数也包含在实现智能契约中，用户将无法调用实现契约函数。为了解决函数冲突问题，引入了透明代理模式。

在透明代理模式中，只有当调用来自非 admin 帐户时，函数调用才被委托给实现契约。如果调用来自 admin 帐户，它永远不会委托给实现契约，而总是调用代理契约的功能。这样，即使在代理契约和实现契约之间发生功能冲突的情况下，代理模式也可以继续快速工作。

编写可升级的智能合约有很多注意事项。有许多该做和不该做的事情要遵循。我不会在这里一一介绍。请在这里阅读来自 Zeppelin 公开文档[的警告。](https://docs.openzeppelin.com/upgrades-plugins/1.x/writing-upgradeable)

一篇关于如何使用透明代理模式编写和部署可升级智能契约的实践文章在[这里](/@HashHaran/how-to-create-a-transparent-proxy-1683d21468bf)发布。UUPS 上同样的代理模式在[这里](/@HashHaran/how-to-create-an-uups-proxy-66eca257b2f9)发布。信标代理模式也是如此，在这里[发布](/@HashHaran/how-to-create-a-beacon-proxy-3d55335f7353)。

感谢阅读。

# 我是谁？

我是一名全栈区块链开发者，对构建一个去中心化的、潜在的更具包容性的未来充满热情。有区块链发展的需求吗？

取得联系:📧hariharan @ aluminum . iitm . AC . in

[Github](https://github.com/HashHaran)

> 交易新手？试试[加密交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)或者[复制交易](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)