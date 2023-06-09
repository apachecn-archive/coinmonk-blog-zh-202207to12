# TipStampers.com 最新更新:Git 推送 7155 个插入和 3005 个删除

> 原文：<https://medium.com/coinmonks/tipstampers-com-latest-update-git-push-7-155-insertions-and-3-005-deletions-98b298c7184d?source=collection_archive---------32----------------------->

![](img/c71ddebe15394ff9be94fad5e6b45a12.png)

7155 个插入和 3005 个删除绝对是我在一个分支中推送到 Github 的最多修改的记录。考虑到标准的做法是分解任务，一次完成一项，我并不应该夸耀这一点，但是我自己在工作，我从来没有比过去一个月工作得更努力或更长，所以看到这些数据如此之高是一件很酷的事情。我想当你背靠着墙时，你会表现得最好。至少在这件事上感觉是这样的。

为什么？因为我的财务状况变得越来越严峻，最后死神来了。因此，在改变方向和寻找创收工作之前，我必须用 TipStampers 完成一些重要的事情，然后编码才能自动运行。或者换句话说，在我把 TipStampers 变成一个副业之前，入职和晋升可以用更少的时间更轻松地完成。

这意味着，向平台添加投票和列表功能，并添加一个在特定时间冻结条目的功能，然后将结果永久发布到区块链上——我们称之为“Stampshots”。

有了这个，我就有了一个人们可以参与的独家、一致的日常活动，我可以根据特定人群的兴趣定制投票或列表或问题，或者驾驭当时任何主题的潮流。由于人们喜欢进行和参与民意调查，我可以看到这种生成活动比平台的其他部分更快地流行起来。所以，这成了我在继续前进之前需要完成的第一件事。

这个庞大的任务从研究未来触发一个功能的最佳方式开始。我不想对超过 24 小时的事情使用 setTimeout，所以我必须做一些调查。由于我使用谷歌云平台(GCP)，我的选择最终是云任务或云调度程序。Cloud Scheduler 是我最初的想法，但是它非常昂贵，所以最明显的选择是云任务。

我看了几个 YouTube 视频进行设置，一旦我看到它工作，我就开始解决这个等式的计时部分。我需要云任务在“太平洋标准时间第二天午夜”启动，这个时候网站和数据库上的活动最少，所以我必须了解日期及其转换。

它需要修补和大量的研究，但最终我得到了我需要的:

1.云任务触发必要的 Stampshot 函数之前的秒数，因为这是云任务本身明确要求的。

2.该功能发生的实际日期和时间，因此我可以将它存储在数据库中，并使用它在任何“Stampshot”投票或列表中创建一个倒计时时钟。

下面是实现这一功能的函数。

![](img/bf5a911b94fcec47483d1d03e08c2b5b.png)

一旦我有了这部分功能，我非常高兴，因为这是这个特殊难题中最令人生畏和不确定的部分。

从那以后，建立投票和名单就被搁置了，因为虽然我知道我需要为此做些什么，但我也知道这需要大量的时间。这是无法避免的。所以我决定先完成清单上的其他事情。虽然清单最初很短，但最终有了很大的发展。

例如，我添加了将苹果播客嵌入帖子的功能。几个月前，我添加了嵌入 Tiktoks、Instagram Reels、FB Watch、YouTube、Vimeo、Spotify 和 Soundcloud 内容的功能，但出于某种原因，我当时没有嵌入苹果播客。可能作为一个 Android 用户，我没有意识到它们有多受欢迎。无论如何，这是你在帖子里嵌入一个的样子。

![](img/31450241c8571bd58d6ad748eb3908d8.png)

我也增加了一些美学上的改进。网站现在更全面了，下拉菜单就是一个例子，它看起来更好了。为了增强视觉效果，图标也被添加到其中。

![](img/69a2a2234a5f809eef3c24aa86af22e0.png)

一个平台成员给我的建设性批评是“创建文章”按钮不容易找到。起初，我被带回去，因为它在每个类别中的相同位置，但后来我意识到那可能不是他在看的地方。登录后，你的主页变成了你的“Feed ”,我没有“创建文章”按钮。请注意，这是有充分理由的，因为我想避免不适当的类别选择，但我意识到他是对的，我也应该在那里包括一个。所以我添加了触发模态的按钮，然后提示用户选择创建文章的类别。结果是这样的。

![](img/ab772fd727694aca3b8803d22b9bd72e.png)![](img/c00ead992f9f4d9f1d36fb82a6521925.png)

除了更大的文本、字体的变化、更大的类别按钮、更微妙的

* * *

换行符和我之前提到的圆形之外，另一个主要的美学变化是取消加载微调器，用骨架替换它们，类似于脸书和 YouTube 的做法。有动画和其他的。这是动画进行到一半时的样子。比装载机更酷更时尚。![](img/35d9434ab3c58df9381dab142b91f15f.png)

我还决定在访问数据库并将其存储在 Redux 中之前，从 localStorage 中存储和检索登录用户的初始数据，以加快感知的加载时间。以前，用户的头像需要额外的时间来显示——以及某些有条件的渲染——但现在，像其他社交媒体网站一样，它是即时的。所有这些都是为了用户甚至不会注意到的几秒钟额外的未更新统计数据。我必须说，这是很小的代价。

我在评论中添加的另一个功能是嵌入媒体内容的能力，比如抖音视频和我之前提到的其他内容。为了保持整洁，我最初只希望允许在帖子中嵌入内容，但我改变了主意，将额外的逻辑编程到所有三个评论层中。到目前为止，TikToks，Reels，YouTube 视频等都可以包含在任何评论中。下面是通过编辑器添加抖音视频时的样子。

![](img/6697cc9c7b62f16b09b3b9651d8da917.png)

说到这个话题，我关于成功入职的另一个最重要的更新是关于社交媒体的。具体来说，这与最受欢迎的社交媒体平台抖音有关。

我决定将“有趣”部分换成“#TipTok”部分，以突出和强调人们可以在这里发布他们的 TikToks 并从中赚钱的事实。通过将举报人与抖音联系起来，该平台对年轻一代以及主流受众都有吸引力。它否定了任何加密的感觉，把平台变成了我想要的人群所熟悉的东西。你在 TipStampers.com 上发布 TikToks 并从中赚钱。简单。

![](img/59279d93d02a4ecbb234d7196ae6f986.png)

因此，在#TipTok 类别部分，我头脑风暴了主流受众最感兴趣的内容类型，以及什么最有可能促使用户向创作者发送自愿提示。类别类型包括:教学，烹饪，健身，游戏，表演，喜剧，自然，艺术，动物，体育和音乐。然后，“抖音播放列表”被列为一个包罗万象的类别，用于所有没有家的 TikToks。人们可以在那里分享他们感兴趣的任何 TikToks。

注意:所有媒体嵌入类型都可以添加到#TipTok 部分的帖子和评论中。抖音被特别强调，因为它对入职最重要。它描绘了需要描绘的画面。

现在，对于投票和名单。让我们从列表开始，因为它更容易编码。基本上，它需要较小的条件渲染更新和视觉变化。

在下面的截图中，你会看到一个列表帖子和一个列表条目。你应该注意到它有点模糊，那是因为条目的一部分被隐藏了，以保持它尽可能的“列表式”。在未来，我可能会添加选项，以查看它在纯，一行列表格式了。目前，这是唯一的选择。

![](img/3abbd6a76daef5151ca575c55a30e44d.png)

当它膨胀时。

![](img/2a2be4740844369ddf4b48709e9b2de1.png)

现在开始投票……由于许多条件渲染更新、额外的输入和逻辑、额外的集合、要在多个位置显示的额外数据、修改 chartjs NPM 软件包中的饼状图和条形图，以及确保一切在移动设备上看起来也不错，这才是真正的精彩。哦，我还必须确保 Stampshot 的逻辑工作正常，显示正确。就像我说的，巨大的任务。但是，这是可以实现的。

因此，让我们进行一次投票，投票从编辑器页面开始，可以在下面的屏幕截图中找到。

![](img/23788d838b6df7d176862d0ef9a7c011.png)

编辑器从必需的 2 个投票选项开始，最多 6 个。太多的选择会让我们的大脑变得混乱，所以我选择了 6。

在底部，你会看到“添加 Stampshot？”按钮和旁边的问号。这仅适用于平台成员，但如果您是成员，并且您单击或悬停在问号上，将显示带有以下文本的工具提示。

![](img/edfe204bacb1889202887f0dfc445dd6.png)

创建投票后，页面看起来与您的典型帖子略有不同。这里有一个例子。

![](img/84b2a7013c60aafb014b8a25faab5faf.png)

并且为了更好的测量，在光模式下。

![](img/0df48970cce137ae90dbc34990172a2f.png)

当用户点击“查看投票者”时，将显示一个投票者列表，以及他们的投票。无限滚动分页也被实现到这个特定的投票者数组中。

此外，如果还没有投票，图表也不会显示。如果有投票，并且有人是第一次浏览这个页面，结果是模糊的，需要点击才能取消模糊。因此，如果这个人想在知道结果之前投票，他们完全可以这样做。除非需要，这里不允许剧透。

转到用户的个人资料页面，我必须为每个用户添加基于投票的统计数据和投票信息。这相对容易，因为我为投票设置的模式类似于我为付费墙、拇指或共享设置的其他模式。

![](img/7315dbe9955d79aec3a6ea586d3bfb76.png)

如你所见，我在这里投了 3 次 Happy，但那是因为我在测试的时候允许它。现在，你只能投票一次。

我想这篇博文到此为止了。如果你想看看实际的 Stampshots，以及它在生产中的样子，你必须到实际的平台上去检查一下。我相信会有一个活跃的 Stampshot 投票给你。

希望得到您的投票，感谢您的时间。

萨姆（男子名）

> 交易新手？试试[加密交易机器人](/coinmonks/crypto-trading-bot-c2ffce8acb2a)或者[复制交易](/coinmonks/top-10-crypto-copy-trading-platforms-for-beginners-d0c37c7d698c)