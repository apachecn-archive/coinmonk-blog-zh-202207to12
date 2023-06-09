# 关于密码学你必须知道的第 1 部分

> 原文：<https://medium.com/coinmonks/what-you-have-to-know-about-cryptography-part-1-e943671710e6?source=collection_archive---------38----------------------->

![](img/fa561583aa9aa14e6d494bd994771911.png)

随着多年来技术的进步，获取信息变得越来越容易。因此，保护此类内容免受未经授权的第三方访问的需求变得更加明显。这就是密码学诞生的原因。

# 什么是密码学？

密码学是保护信息安全的科学。

单词 cryptography 是两个希腊名字的组合；kryptos 的意思是“秘密或隐藏的”，graphein 的意思是“写”。那是秘密写作。

但理想情况下，密码术指的是对信息进行加密和解密以防止未经授权的第三方访问信息的艺术。

这不是最近才出现的，而是一个由来已久的概念，现在已经对电子商务、军事通信、加密电子邮件、[区块链](/coinmonks/what-you-have-to-know-about-blockchain-technology-3a27cc0ebb84?source=user_profile---------10----------------------------)等不同领域产生了广泛的影响。

# 密码术是如何工作的？

为了更好地理解密码学的工作原理，让我们先定义一些常用术语。

**加密:**这是使信息不可读以防止第三方理解其内容的过程。加密是通过加密密钥来完成的，这对接收者理解消息是至关重要的。

**解密:**这就是简单的逆向加密。这是解读加密信息的过程。信息的接收者通常使用密钥来完成这一操作。但是这在很大程度上取决于所使用的加密类型。

今天的现代密码学涉及计算机使用复杂的数学系统和算法进行加密和解密，但这是理解密码学的基础。

例如，让我们考虑一下[凯撒密码](https://www.google.com/url?sa=t&source=web&rct=j&url=https://www.sciencedirect.com/topics/computer-science/caesar-cipher%23:~:text%3DThe%2520Caesar%2520Cipher%2520is%2520a%2520monoalphabetic%2520rotation%2520cipher%2520used%2520by,as%2520shown%2520in%2520Table%25204.6.&ved=2ahUKEwjh5oCInpT7AhWoi_0HHcf0CloQFnoECAsQBQ&usg=AOvVaw3zynF5Zs3GsK6H1wnYvSAP)，这是在古代使用密码术在凯撒和他的官员之间传递信息的最早的例子之一。

凯撒的加密基本上是在他想要的地方写另一封信。如果他打算写字母“B ”,他可以数三班倒，改为写“D ”,这就形成了整个公报。这个概念被称为算法。

对于他的官员来说，要破译这个信息，他们需要了解他们需要多少步才能在字母表上找到原来的字母。这被称为密钥。

凯撒的密码有两个主要的密码元素:密钥和算法，对解密信息都很重要。

# 密码学的目标

虽然古代加密的主要目的是能够进行保密通信，但现代密码学有四个主要目标。

**保密性:**未经授权的人不能理解信息

**完整性:**信息不应被篡改

**不可否认性:**发送者不能在以后否认他们传输数据的意图

**认证:**发送方和接收方必须能够相互确认

# 密码术的类型

有三种主要类型的加密技术。它们是:

# 1.对称密码术

在对称加密中，算法使用秘密密钥创建分组密码，然后使用秘密密钥对信息进行加密。接收者可以用这个密钥解密信息。由于这里密钥的关键性质，它通常也被称为单密钥加密。

# 2.不对称密码术

非对称类型的加密不使用相同的密钥进行加密和解密。加密密钥对网络上的每个用户都是公开的，但用于解密的私钥是保密的。

# 3.散列法

哈希使用一种称为哈希函数的算法来扰乱数据，使其无法识别。这样做是为了即使黑客获得了散列，它也是完全无用的，因为单独使用散列是不可能进行解码的。

> 交易新手？尝试[加密交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)或[复制交易](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)