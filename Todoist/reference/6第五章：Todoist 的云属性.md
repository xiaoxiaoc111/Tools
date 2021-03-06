# 第五章：Todoist 的云属性

在使用 Pocket 时，我发现了一个特殊的需求和一种特殊的体验。

这个特殊的需求是：对于我这样的人来说，稍后读服务中会存有一些软件教程类文章，它们操作性较强，不适合纯粹阅读，而是需要我们抽出时间，对照着文章中的步骤学习和执行。这种文章，我需要把它们放在任务管理软件中。

特殊的体验是：通过 Pocket 中内置的 Evernote 动作，我们可以带着 Pocket 中的标签，发送全文到 Evernote。这个发送的过程不需要特殊界面，也不需要跳转到 Evernote 的应用，它通过 Pocket 这个服务与 Evernote 这个服务之间的联接来实现。在 Pocket 中选择「发送」之后就可以继续阅读剩下的文章，而当我们打开 Evernote 并同步，就能看到这篇发送过去的文章。

当时我在用的是其它的任务管理软件，我发现这种没有「服务」属性的本地应用无法同时满足上述的需求和体验。

在 iOS 上，把 Pocket 的文章发送到基于本地的任务管理应用有两种方法，第一种是通过 Share Sheets，第二种是通过 URL Schemes。当我们通过 Share Sheets 实现时，目前必须保证任务管理应用在后台运行，否则只有再次打开该应用时才会发生同步，你才能从其它设备上看到通过 Share Sheets 添加的任务。而通过 URL Schemes 的话，当时就要中断阅读，跳转到其它应用。两种方法，都不能完成发送文章到 Evernote 的那种体验。

那时，我意识到，任务管理工具已经不能只是在本地应用层面来做一些记录与呈现之类的事了，任务管理工具的未来，需要实现服务与服务之间的联接，来进一步地简化操作、拓展可能性。也是在那时，Todoist 才真正进入到了我的视野。

作为一项比较开放的服务，Todoist 可以与其它服务**直接整合**，也可以通过 Zapier 和 IFTTT 联结其它服务，**进行间接却而又复杂的自动化**行为。在本章中，我们将各取几个例子，来熟悉这种特性的优势。对于进阶用户和开发者，我们还可以直接通过 Todoist 的 API，来实现它目前没有做到的事。

## Todoist 与其它服务的直接整合

![img](https://cdn.sspai.com/2017/07/14/46bdf735821718ff49dc37a0cd4cd501.png)

所谓直接整合是指双方在 API 层面实现互通，不需要通过 Zapier 或 IFTTT 来做联结。它的好处是由两个服务官方实现，规范、稳定。但不足是两者之间一般会有一套固定的整合方式，我们难以进一步地自定义。

### 关联时间追踪服务

时间追踪也是效率话题中的一个热门，而任务管理软件和时间追踪软件一般都会分处于两个工具。那些著名的任务管理软件没有时间追踪的功能，而知名的时间追踪工具也不能像进阶工具一样满足任务管理的 LTF 系统。

很多人因为对时间追踪的信仰，坚持手动记录。与任务管理工具结合时，就不得不把要追踪的任务从任务管理工具中复制到时间追踪工具，当任务完成时，又不得不两边都做停止/完成任务的处理。

虽然是为了效率，但整个过程看起来着实不效率。

好在 Todoist 的本质是一个服务，好在有不少时间追踪工具的本质也是服务，好在它们早就有意识地进行了互相整合。

Todoist 支持了 9 个时间追踪服务，其中也有番茄工作法的服务：

![Todoist 支持的时间追踪服务](https://cdn.sspai.com/2017/07/14/28b18beaa4bef0655f0d99c15e5f9905.png)Todoist 支持的时间追踪服务

其中 Toggl 的实现方式我觉得最为聪明，并且我也曾经用过一段时间 Toggl，所以准备以 Toggl 为例来介绍 Todoist 与时间追踪服务如何结合。

首先我们需要安装 Toggl 在 Chrome 中的插件，然后在插件设置界面的「Url Permissions」中，搜索「Todoist」并勾选出现了的结果：

![Toggl Chrome 插件的设置界面](https://cdn.sspai.com/2017/07/14/b5a240d78b342183ea87305b8bfeba10.png)Toggl Chrome 插件的设置界面

这时候用 Chrome 打开 [todoist.com/app](https://todoist.com/app)，会发现当我们把鼠标悬停在任务上时，任务名后会出现 Toggl 的标志，后面有「Start Timer」的字样：

![Toggl 在 Todoist 中的效果](https://cdn.sspai.com/2017/07/14/cafd889327706eaf17a206a40ed7410b.png)Toggl 在 Todoist 中的效果

点击「Start Timer」，Toggl 就会开始计时，并会弹出一个窗口让我们填补任务细节：

![在弹出窗口中填补任务细节](https://cdn.sspai.com/2017/07/14/56653f44b173fae0541e3c35f53cc174.png)在弹出窗口中填补任务细节

其中任务名是预设好的，就是 Todoist 的任务名，而任务所属的项目则视情况而定，如果 Todoist 中的项目与 Toggl 中已有的项目同名，它就会自动匹配这个项目名。这样的话，你就不需要填任何东西，直接确认即可。

虽然这种方法的限制很大，只能在桌面系统以及必须用 Chrome 打开 Todoist 才行，但是相对于需要提前导入任务到时间追踪服务的做法，Toggl 这种实现方式在选择任务和项目时灵活度更好。

### 关联 Google 日历

在这部教程开始时，Todoist 和日历的整合还非常基础。它只能通过上一篇教程中提到的那种订阅日历的方式，而这种方式两个问题：一是无法自定义日历事件的持续时间，二是无法双向同步任务。通过关联 Google 日历，Todoist 一定程度上解决了这两个问题。

关联 Google 日历的选项和关联日历的选项是同一个界面，都在：Settings（设置）—— Integrations（整合） 里。

关联完 Google 日历后，它会让你进行一个简单的初始设定：

![Google 日历关联后的初始设定](https://cdn.sspai.com/2017/07/14/ab737ec9811a4b0871dbadc240ceb7ff.png)Google 日历关联后的初始设定

我们首先来看它如何解决了事件的持续时间问题。

在添加任务时，只要在任务名后加上 `[30m]`，就代表这个任务的持续时间是 30 分钟，Google 日历中的事件的持续时间就会是 30 分钟。同步完成后这个 `30m` 会在任务名中自动消失。

事件持续时间的起始点是这个任务的提醒时间，也就是说如果一个任务没有提醒时间，那它在谷歌日历里只会是个全天事件，不会有持续时间。

目前持续时间这个功能实现得比较基础，原因有两个：首先，这个持续时间必须是在添加任务时加的。也就是会说我们不能通过修改已有任务的任务名来给它设定持续时间，除非把已有任务删掉，重新输入一遍。其次，目前这个语法只支持 `m` 也就是「分钟」这个单位。

然后是双向同步。

首先对所有已有内容的改动都是双向同步的，比如事件的日期和标题，在一方修改后自动在另一方修改。

其次，当我们在 Google 日历中添加事件时，它也会成为一个任务，被添加到 Todoist 中，这个任务会带有 @gcal 的标签，这个标签可以在 Integrations （整合）这个界面修改。

### 关联邮件

邮件和任务的关联对于一些人来说也是刚需，在某些特定的时候我们会需要把邮件作为任务放到任务管理系统中。需要回复或者处理这封邮件的时候，能从任务管理工具直接跳转到对应的那封邮件。Todoist 可以通过多种方式满足这种需求。

#### Outlook 与 Gmail

Todoist 为 Windows 平台的 Outlook 软件制作了一个 [插件](https://todoist.com/outlook)，也在 Chrome 中制作了一个 [插件](https://todoist.com/gmail) 用于服务 Gmail。两者实现的方式比较类似，所以我只介绍相对比较复杂的 Outlook 插件。

当安装完 Todoist 插件你会发现在 Outlook 界面的工具栏右侧增加一个 Todoist 按钮，最右侧会出现 Todoist 的区域，这个区域拉开以后是一个完整的 Todoist 界面。

![Outlook 界面](https://cdn.sspai.com/2017/07/14/df14a2f5755134b8662d8944775093b9.png)Outlook 界面

在打开一封邮件后，点击「Create Task」这个图标会直接在 Todoist 中创建一个任务，任务名为打开了的邮件的标题，标题前会有一个邮件的特殊标记，而且标题是一个可点链接。

![添加邮件到 Todoist](https://cdn.sspai.com/2017/07/14/e878ac3407d8bdab1306572264239e43.png)添加邮件到 Todoist

添加任务成功后，不论你在 Outlook 中的 Todoist，还是在桌面端的 Todoist，点击这个任务名，都会直接通过 Outlook 打开这封邮件。

#### Airmail 和其它第三方邮件客户端

苹果环境的朋友也有一些方法去实现邮件与 Todoist 的关联，但是操作上最省事的方法是通过一些特定的第三方客户端。

![可以直接发送邮件至 Todoist 的第三方邮件客户端](https://cdn.sspai.com/2017/07/14/9d39cc36b5c730b211223457b58f5403.png)可以直接发送邮件至 Todoist 的第三方邮件客户端

在这之中我选择了 Airmail，所以会以它为范例来进行介绍。

首先在 Airmail 的设置你可以找到「Services」这个选项，在这里有各种第三方应用与服务，其中就有 Todoist：

![Airmail 的设置选项](https://cdn.sspai.com/2017/07/14/bd6c9ddba710f9b997e7f8db34c0c6e6.png)Airmail 的设置选项

在这里将 Todoist 的开关打开，关联账户以后，就可以在邮件界面发送邮件到 Todoist 了。发送的位置是 Inbox，任务名是邮件标题和该邮件的 URL 的组合：

![从 Airmail 发送邮件到 Todoist](https://cdn.sspai.com/2017/07/14/02250662eb7a750939967d874e139792.png)从 Airmail 发送邮件到 Todoist

跳转的话和 Outlook 的体验一样，当我们在 Todoist 中轻触这个任务的链接部分，就会直接在 Airmail 中打开这封邮件，不论用的是 iOS 还是 macOS。

### 关联 Slack

Slack 是一款西方的团队通讯工具，非常适合团队内部交流，也适合一些简单的用户运营（虽然它并不是以这个目的设计的）。它也有非常开放的 API 系统，可以让其它服务接入其中。

Slack 与 Todoist 有直接的整合——从 Slack 直接发送任务到 Todoist。但是我在使用中，也用到了通过 Zapier 联结，借以实现直接整合中没有实现的东西。我们将在这一小节分别来谈这两种情况，并过渡到通过 Zapier 实现 Todoist 与更多服务间的自动化。

#### Slack 与 Todoist 的直接整合

Slack 与 Todoist 的直接整合是 Todoist 服务属性的一个标志，也体现了在任务管理工具中使用自然语义来决定任务各个元素的优越性。

在 Slack 中，当我们做好关联，可以通过输入 `/todoist` 告诉 Slack 我们接下来要往 Todoist 添加任务了。

在 `/todoist` 之后，我们要写的是任务的具体内容。我们不仅可以写任务名，把它发送到收件箱，我们还可以用之前提过的语法，来指定项目、标签、任务的时间、重复，甚至委托人：

![通过 Slack 向 Todoist 加任务](https://cdn.sspai.com/2017/07/14/f9b552a31ab86cee62f5fce029a98b53.png)通过 Slack 向 Todoist 加任务

想必大家都有沟通工作时想到一些新任务的情况，通过 Slack 和 Todoist 的整合，我们完全不必脱离那个交流的情境，就能把任务抛到它该去的位置。

### 通过 Zapier 联结 Slack 与 Todoist

在录制播客的时候，我时而会念听众群里听众的一些发言。在第一次做这件事的时候，我就在想怎么样能效率地把这些发言放到我录播客的这个项目下，让我录制时打开 Todoist 就能看到它们，而不会忘掉，或者临时搜索，又或者一段一段地复制粘贴。

当时我就想到了 IFTTT。但是我发现对于普通用户来说，Slack 不能作为一个 「If this then that」中的 「This」，而只能作为一个「That」。也就是说 Slack 不能触发一个行为，只能作为结果被触发。所以这时候就只有借助 Zapier 了。

Zapier 完美地实现了这个需求，我通过 Zapier，做了「当我在 Slack 中星标一个发言，就将它自动地发送到 Todoist 中的指定项目」这么一个流程。

前面的步骤都很简单：关联 Slack 账户，设定星标一个信息为 Trigger（触发点），然后就到了 Todoist 的部分。在 Todoist 的设置部分，我们可以充分利用 Todoist 标题支持 Markdown 这个特性，去把各个元素以 Markdown 的语法来组合：

![Todoist 部分的设置](https://cdn.sspai.com/2017/07/14/260d78fdf973591b430f44f0ee232b29.png)Todoist 部分的设置

通过这样设置，我可以知道是哪个听众的发言。如果有必要，也可以跳转到 Slack 去查询上下文。

### 通过 Zapier/IFTTT 联结 Todoist 与其它服务

![img](https://cdn.sspai.com/2017/07/14/6c6ff9b310237dd4e1635dded443d664.png)

IFTTT 和 Zapier 这两个服务在联结其它服务的领域各有所长。在本教程中我将取适合的工具来实现需求。比如从免费账户可用的次数方面考虑，如果一个想法两个工具都能实现，那我倾向于先泽 IFTTT。但 Zapier 支持在创建新任务的时候**添加标签**，这直接导致有些需求必须通过 Zapier 来完成。

Zapier 和 IFTTT 从功能、实现方式以及价格上都有较多区别，如果有兴趣，可以看《[Zapier vs. IFTTT](https://sspai.com/post/39258)》这篇文章，作出自己的选择。

### 通过 Zapier 做重复任务

其实，通过 Zapier 或者 IFTTT 这样的服务不但能联结多个服务，也可以针对同一个服务实现它原本不能实现的功能。比如 Todoist 就没有「完成后重复」这么一个功能，而我们可以借助 Zapier 或者 IFTTT 来实现。恰巧有一位读者在反馈邮件中提出了这么一个需求：

相机电池总是忘了充电，想实现这样的效果：

1. Todoist 里一直有一个「相机电池充电」的任务
2. 如果在外面用完了电池，只要把这个任务的日期改在今天，到家的时候就会通知我充电
3. 充上电以后勾选完成，这个任务会回到「1」的状态

这个需求，我们要通过 Zapier 来完成。

**首先是准备工作：**在进行之前，要先建立一个「相机电池充电」的任务，放到一个合适的项目里，比如说「生活」这个项目，再给它打上一个任意的标签，比如说「重复」或者「recurring」1 。然后把这个任务给 Check 掉，也就是完成它。这么做的原因是因为 Zapier 的检查机制，我们后面会提到。

**接下来我们来进行 Zapier 的设置。**

**触发部分：**在选择 Todoist Trigger 的界面，我们要选那一行蓝色的字：「show less common options」，里面有一项「New Complete Task With Label」，我们要选这一项为 Trigger。

![选择 「show less common options」](https://cdn.sspai.com/2017/07/14/a16cd162961b5bf512843815c370f994.png)选择 「show less common options」

在选择项目和标签的部分，我们要选择刚才我们在准备工作中为那个任务设定好的项目和标签（我设置的是「EasyDo」这个项目和「recurring」这个标签）：

![设置项目和标签](https://cdn.sspai.com/2017/07/14/9e4d70fa726eea944cf532d8521bc643.png)设置项目和标签

接下来 Zapier 会进行检测，来看看「EasyDo」这个项目里有没有带有「recurring」的并且是已完成状态的任务，这就是为什么我们要事先做好一个带有标签的任务，并把它完成。如果不做这一步，检测就会失败。

**执行部分：**在执行部分，我们的动作要选择「Create Task」。然后我们要选择这个要被创建的任务的细节，这个要被创建的任务的细节是什么呢？

1. 标题是「相机电池充电」；
2. 存在于项目「EasyDo」中；
3. 标签是「recurring」。

三者缺一不可，缺了第一项，这个任务本身就没意义了；缺了后两项，就无法做到完成后重复。所以在设置的时候，要把每一个部分都考虑到：

![Zapier 执行部分的设置](https://cdn.sspai.com/2017/07/14/0a47e4d7f48e1bddafb30a740eed0704.png)Zapier 执行部分的设置

*注意在 Zapier 中，标签在这个界面的最末尾，而不是上图的这个位置。*

标题的位置没有直接填「相机电池充电」而是填了变量「Step 1 (Content)」（Zapier 在步骤一中检测到任务名称）的原因是让这个动作更灵活，不再只适用于「相机电池充电」这个例子，只要是放在项目「EasyDo」下，并打上了「recurring」标签的任务，都会自动变成重复任务。

这里选择 Zapier 的原因是 IFTTT 不支持创建带有标签的任务，这样就没有办法满足循环的第三项条件，也就不能达到最初的目的。

### 从稍后读服务中发文章到 Todoist

接下来，让我们回到最初的那个需求——如何能够在不跳转、不打断阅读的情况下，把任务发送到任务管理工具？这首先需要阅读工具和任务管理工具都有服务的属性，即可以通过 API 获取和发送数据；其次，它们两个之间要么互相有直接整合，要么可以通过 Zapier 这样的服务去联结。

Pocket 与 Todoist 都是服务，第一点已经满足，但互相没有整合，所以需要通过 Zapier 或者 IFTTT 这样的服务来联结。这项工作 IFTTT 就可以胜任，同时因为 IFTTT 的免费账户不限制使用次数，所以这次我们来通过 IFTTT 实现这个需求。

![IFTTT 设置部分](https://cdn.sspai.com/2017/07/14/7def3b3d03b10f0f3e901f83f78bb52c.png)IFTTT 设置部分

通过图片很容易看明白整个机制：

1. 触发的条件式 Pocket 的文章标上了 「0-5 Download」这个标签；
2. 任务将会被添加到 Download 这个项目中
3. 任务名利用了 Todoist 支持 Markdown 语法这一特点
4. 备注（评论）中是文章的摘要

## 利用 API，归档已完成任务

![img](https://cdn.sspai.com/2017/07/14/08d97dc003f2814fd80e2646ef07f12d.png)

一个开放的服务会提供开放透明的 API，这会让那些有能力的开发者或 Power User 能够定制满足自己需求的工具。

比如说「查看已完成任务」是许多读者在反馈中提到的一个需求，我也在上一章中提到了两种查看的方法。

但是如果我们想把已完成的任务提取出来，该怎么办呢？我之前的方法是通过 IFTTT，把 Todoist 中已完成的任务按照格式自动添加到 Dropbox 的一个文档中。但是这样做的问题是它是纯粹地按照完成时间排列所有已完成的任务的，所有项目中的已完成任务会按照时间线交叉在一起，不会自动按照 项目-时间 的模式去归档；如果我想提取某个特定项目的已完成任务，就需要再做匹配。

Checked 听众群中有两位开发者，基于他们自己写周报的需求，通过 Todoist 的 API 做了一个小工具（todoist reporter：<http://www.z2n.tech/>）。

![Todoist 完成任务导出工具的网页](https://cdn.sspai.com/2017/07/14/5dee0648ae1d253fe0cd708516f731b5.png)Todoist 完成任务导出工具的网页

目前该工具仍在测试阶段，已经可以做到根据项目来导出已完成任务。导出的格式支持 Markdown、CSV 和 TXT，下图为导出为 Markdown 时的预览图：

![将已完成任务按项目导出为 Markdown 文件](https://cdn.sspai.com/2017/07/14/893b046694fd1768328f11e26f335f4e.png)将已完成任务按项目导出为 Markdown 文件

如果在使用这个小工具过程中有问题或者功能需求，可以给 neneam 的团队 ZeroToN 发邮件（zeroton.2017@gmail.com）

如果你在授权，或者链接过程中发现弹出了错误，请尝试把链接前的 `https` 改为 `http`。

## 用 Workflow 批量添加任务

当别人指派多项任务给我们、或是我们自己整理手头的任务时，我们都会有批量添加任务的需求。从输入效率方面考虑我更习惯直接打开备忘录、Drafts 等工具先以列表的形式把任务记下来，再把这些先记下来的任务批量发到任务管理工具。

![左：Drafts 中批量记录的任务；右：发送到 Todoist 后的效果](https://cdn.sspai.com/2017/07/14/e979103e677f6c728cef26add8112160.png)左：Drafts 中批量记录的任务；右：发送到 Todoist 后的效果

通过利用 Workflow 内置的 Todoist 动作，就可以做到给 Todoist 批量添加任务。这个 Workflow 的制作方法也非常简单，总共只需要 3 + 1 步：

### 第一步：选择文字接收方式

![Workflow 步骤图](https://cdn.sspai.com/2017/07/14/3de5ab4d7e940ed7b5fe7a215b6d47ed.png)Workflow 步骤图

在 iOS 上，Workflow 接收文本的方式一般有三种：

1. 我们直接在 Workflow 中输入
2. 获取剪切板文字
3. 将选中文字作为要接收的文本

这三种方式都可以利用在这个 Workflow 里，但考虑到实用性，我在这里只以第三种作为示范2 。

![选择 Workflow 的类型和接收的对象](https://cdn.sspai.com/2017/07/14/3329d15a4fd90c3b51bed30d88fc4952.png)选择 Workflow 的类型和接收的对象

我们把 Workflow 的类型设为 `Action Extension`，接收对象设为 `Text`。

### 第二步：以行分项，作为任务名

因为录入任务的时候我们一般是每一行写一个任务，所以这时候，我们就应该告诉 Workflow 这一点，也就是分行，不然 Workflow 会把所有文字当成一个任务放到 Todoist 中去。

在 Workflow 里做到将文本分项的动作是 `Split Text`，在 `Separator` 的部分，因为我们是以「行」为单位，所以我们要选择 `New Lines`。

![左：Split Text；右：分项方式设为 New Lines](https://cdn.sspai.com/2017/07/14/bf69f365947aa435ebd0097ad3a3f33d.png)左：Split Text；右：分项方式设为 New Lines

### 第三步：把每项都发送到 Todoist

把每行的文字提取为任务后，就可以把它们发送到 Todoist 了。Workflow 里有内置的 Todoist 动作，但是如果你在 `Split Text` 下直接接 Todoist 的动作的话，这个 Workflow 只会运行一次。也就是说它只会把第一行的文字取出来，生成一个任务，然后 Workflow 就停止了，达不到我们想要的每一行文字生成一个任务的效果。要想做到每行文字生成一个 ，就要用到重复，在 Workflow 中，这次要用的是 `Repeat with Each` 这个动作：

![用 Repeat with Each 包住 Todoist 动作](https://cdn.sspai.com/2017/07/14/0ac4f05e46fa74a56d211975830029bc.png)用 Repeat with Each 包住 Todoist 动作

我们用 `Repeat with Each` 包住 Todoist 的动作，就能达到每一行文字都重复执行一次添加到 Todoist 的效果。

而在 Workflow 内置的 Todoist 动作里，`Content` 是任务标题，任务标题应该是原文本中每一行的文字。这一点可以用 `Repeat Index` 来完成，这个变量会自动把 `Split Text` 输出的每一行都填入到`Content`，直到每一行的内容填写完毕。

接下来你就可以在 Drafts 里分行写下一组任务，然后选中它们，通过分享菜单，一下全部发送到 Todoist 了。

因为 Todoist 是服务属性的任务管理工具，这些任务不需要发送到本地而只发送到云端就可以自动同步回所有客户端，所以即使是在 iOS 平台上，我们在执行这种批量操作时，也不需要借助 URL Schemes，也就避免了多次跳转的体验。

### 第 3 + 1 步：不接受文本文档作为附件

如果只用前三步做一个 Workflow，你会发现发送到 Todoist 的每一个任务里都有一个附件，这个附件是 Workflow 将接收到的原始文本生成出的文本文档。

![左：含有文本文档附件的任务；右：文本文档附件](https://cdn.sspai.com/2017/07/14/024cc7424e9a8afca7bbd96914ac06ce.png)左：含有文本文档附件的任务；右：文本文档附件

如果不想要这个东西，可以在 `Repeat with Each` 下先加一个 `Nothing`，确保文本文档本身不会传输下来。同时因为我们用了 `Repeat Index`，所以每一行文本还是会按计划生成一个新的任务。

如果不想自己动手制作，这里有成品的动作，你可以直接拿去使用：[Workflow 下载](https://workflow.is/workflows/571b62d8f701404c8c8b59ba5cdb4014)

### 进阶：更自由地批量添加任务

但问题是这样做的话任务只能进入收件箱。而有时候我们已经想好了这些任务的细节，想把它们直接发到具体的项目，甚至添加标签等需要的元素。这时候就要借助 Todoist 的 API 来完成了。

少数派有一篇文章《[利用 API 在 Workflow 内调用更多 Todoist 的功能](https://sspai.com/post/38823)》，出自 [@Se7en_YXS](https://twitter.com/Se7en_YXS)，里面详细介绍了在批量添加任务时为每条任务指定项目、标签，有兴趣完全掌握这一技巧的读者可以参考学习。

如果不想学习具体思路，文章中也提供了 Workflow 下载。只要下载了文章中的 Workflow，按照教程开篇的提示填入自己的 Todoist 令牌，就可以直接使用该 Workflow 了。

1. 项目名和标签是什么不重要，只要和后面设置 Zapier 规则的时候保持一致即可。 ↩
2. 如果你想要将三种方式都利用起来，可以参照我曾经写过的《Workflow 思路教程》中，「如何判断上一步有没有结果」这一部分。 ↩