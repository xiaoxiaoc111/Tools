# 第三章：使用 Todoist 进行任务协作

任务管理不总是一个人记下自己该做的事，我们也会记下别人应该做的事（委托），别人也会记下我们该做的事（指派）。

在这一点上，大多数为个人而设计的工具变得捉襟见肘。使用这些工具的人们不得不退而求其次地使用标签来指定人物，但这依然只是简陋地把他人融入到自己的任务管理工具，并不是真正地实现多人任务。任务情况稍一复杂，很快就不能胜任。

而 Todoist 不仅可以多人共享任务，从实现上看，它为多人共享任务下了不少功夫。

## 亲友间的轻量协作

一般多人任务管理都会从身边的人（伴侣、室友、家人）起步，但是一般来说，它们的频率和密度都并不高，所以这个情境下的协作是**轻量的**，需要的功能只是：**列表共享**和**任务指派**。

### 列表共享

因为任务管理系统最基本的组成部分是列表，所以列表共享是任务协作的最基本条件。在正式介绍 Todoist 的列表共享功能之前，我打算先介绍一下，被共享的列表中的任务如果附有各自的标签，会发生什么情况。

在 Todoist 里，标签理所当然地会随着列表一起共享。所以如果你某天查看标签时发现多了一坨新东西，可以先去看看你和同伴的共享列表里的任务。

不过你大可以放心地把那些不属于你标签系统的标签删掉，因为在你的账户里删掉的标签，在对方的标签系统中依然存在。也就是说，**同步标签是共通的，删除标签是隔离的。**进一步的，也就是说，你把对方的标签在你这儿全部删干净，对方也不会有任何察觉，他那里每个任务带的标签都不会有任何改变。但是，如果对方在共享的项目里的某个任务上又打上了他自己的标签，不管你以前删过没删过这个标签，这个标签都会再出现在你的标签列表里。

### Todoist 分享列表的三个方法

在 Mac 上，最简单的是右键一个项目名，然后选择「分享项目」：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\466559c45c7bc7e116c7fa5de7b8d44e.png)

第二种方法是通过项目的右上角的「+人」按钮：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\fca3e71b818025dda48c409a8d86cae7.png)

在 iOS 上，用项目菜单右上角的按钮呼出下拉菜单，你就能看到「分享项目」了：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\8c2cd247d6c8ffe357a9358f5dd2f0b8.jpg)

#### 邀请他人的两种方式

**第一种邀请方式**是传统的邮件邀请，也就是**填写对方的邮箱**，如果在 iOS 上，你可以直接**从通讯录选联系人**。通过邮件邀请的人，如果在设备上运行着 Todoist，会直接收到通知，错过通知也不要紧。

首先，在 iOS 和 macOS 上，主界面的右上角都有一个小铃铛的标志，这里记录了一切关于你账户的事件，所有的邀请记录都可以在这个位置查看：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\28243e71a58c29e6834f1e0c7f2876d0.png)

如果被邀请人设备上没运行 Todoist，或者他压根没注册 Todoist，他会收到一封这样的邮件：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\3f98350a1547e636ac16aaaa84e9453e.png)

没有注册的人在跳转后要完成注册，注册完成后，被邀请的项目会自动出现在项目界面中。

**第二种邀请方式**是项目内邀请，使用这种方法的前提是你已经和一些人共享了一个项目，现在你想和他们或者其中的几人共享一个新项目，这在团队使用的情况下比较常见。团队账户的情况下，通过项目内邀请，把项目共享给本团队的人时，他们会在被邀请时收到提示，然后直接被拉到项目中来。通过项目内邀请，把项目共享给团队外的人时，需要经过其本人同意才能够加入项目。

#### 结果通知

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\8b203a4b19b757bb69f38f9c8e7443ee.png)

默认情况下：

- 邀请人在对方「接受邀请」「拒绝邀请」「退出」时会收到通知；
- 被邀请人在「被邀请」「被移除」时也会收到通知。

简单来说，几乎所有共享行为都会被通知，如果你不想被通知，Todoist 也提供了自由的设定，你可以随意取消不愿意看到的通知：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\75e936e7710a1d44922d69ddec117578.png)

图中的手机不仅代表移动端，也代表桌面端。

### 指派任务

项目共享出去之后，理所应当的，所有共享者都可以看到该项目之下的任务，也可以对任务进行单人指派。

指派任务的方法首先可以**通过图形界面**来进行：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\08b5a1cc3d772829d9be8c15bded6406.png)

输入任务时，轻触人形图标，就会弹出**所有共享该项目中的人**，然后你可以选人去指定，包括你自己，选择完成后，和时间块一样，任务名后会出现一个人物块：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\34ccb0554d7ead7fd73f9086bcee0296.png)

仔细看上上一张图的话，你会发现，在时间块后面有一个加号「+」，这个加号是指派人的快速输入符，也就是说，你并不用每次都使用图形界面，尤其是在用键盘添加任务的时候，你可以直接输入加号「+」，然后输一两个字母，当 Todoist 剩下唯一正确的候选人时，再按回车：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\90c8168b615f058d937ed43ac304cf6a.gif)

被指派的人会马上收到一个提示：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\71eccd93d24897efdc472a742ae0ac4a.jpg)

当指派的任务完成，被指派人勾选掉任务后，任务的指派人会收到一则提示，通知他任务已经完成：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\84d317b138ded8849d3fc75e4100adfe.png)

结果通知和相互提示这两个功能是我觉得 Todoist 里最舒服的功能之一。我不再需要打个电话或者发个短信告诉他「嘿，回家的时候买个 xxx 吧，我都加到你任务管理软件里了。」他也不需要告诉我他到底干没干这件事。如果我估摸着到时间了，还没收到通知，就说明他可能是因为还不习惯任务管理工具1 或是什么原因忘了这件事，我可以直接打电话提醒一下。

## 小型团队使用 Todoist 工作

当任务协作从身边的人转为团队工作，任务指派的频率以及系统的复杂度就会发生质变。这时候除了**列表共享**和**任务指派**之外，会有更多需求进来，事情也会变得复杂。

### 指派一人，通知多人

首先来看一个职场上经常会发生的情况：一个任务的执行者不是一个人，而是一组人。在这种情况下，关于这个任务的调整、追加信息，都要通知到整个团队。但是 Todoist 只能把任务指派给一个人，如何让这个任务的状态变化和信息追加通知到所有相关的人呢？

在 Todoist 里有一个设定，是你可以在分享出的项目里添加任务时，选择「评论」的被提醒人。「评论」可以被视为 Todoist 中的备注2 ，但它的内容要比备注广泛得多。在多人协作的情境下，这里可以被视为关于任务的讨论场所，iOS 上它的入口在任务的菜单里，macOS 上它在每个任务名的后面：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\3b081547b3019b65be3806ecef59d4f9.jpg)

在评论界面的底部，有「通知 xxx 我的评论信息」的字样。这个 xxx 是任务在 Todoist 中被指派的人，有新评论产生时，这个人是必然被通知的。轻触右下角的铃铛标志，可以选择当评论发出时其他接受提示的人：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\96bdabf1298935d3f6762fc174690273.png)

所以在 Todoist 中，我们可以设定一个任务的负责人，把任务指派给他，团队领导想知道任务进行的状态时候，可以找这个人沟通。但当这个任务有状态变化或者追加信息需要通知给多个人的时候，可以由这个项目下的**任何成员**发送通知给**指定的成员**或者**全员**。

### 专用于协作的语法：Assigned

在多人协作情况下，任务的指派状况会变得复杂。对于成员来说，他们需要知道自己当前要做什么工作；对于团队的领导来说，他们要知道哪些任务没有被指派，哪些任务添加了很久却没被执行等。

这些需求都要借助过滤来实现。而在 Todoist 里，有一个专门用于协作的语法——`Assigned`

它有以下几个形式：

- `Assigned`：所有进行指派的任务
- `!Assigned`：所有未进行指派的任务
- `Assigned to: me`：所有指派给我的任务
- `Assigned to: xxx`：所有指派给 xxx 的任务
- `Assigned to: others`：所有指派给其它人的任务

除此之外还有一个语法可以对 `Assigned` 进行辅助，它是 `shared` 意为「所有共享中的任务」。

接下来我们看如何使用这些语法，再结合之前文章里提到的语法，来满足团队成员和领导的需求。

#### 「我」今天的工作任务

语法：`##工作 & assigned to: me & !@hold & today`

要从 Todoist 中提取「我」在今天的所有任务，要考虑的点是：

1. 属于我「工作」这个大项目下的所有任务，包括其所有子项目中的所有任务，所以用 `##`而不用 `#`3
2. 是指派给我的任务，所以用 `assigned to: me`
3. 不要那些现在因为不可控原因无法执行的任务，所以用 `!@hold`
4. 时间要是今天，所以用 `today`
5. 以上所有条件都要共存，所有用 `&` 来连接

#### 团队中没有被指派的任务

语法：`##工作 & shared & !assigned`

在团队协作中，让人注意到一个任务的方式就是把它安在那个人的头上。团队任务那么多，不可能指望每个成员都去任务坑里扒任务自己做，所以我个人认为，一个团队任务系统的健康状态，就是每个任务都有负责人。起码，这个团队今天要执行的任务都该有它的负责人。所以团队的领导就要常核查哪些团队任务还没指派到人。

做这个过滤的语法很简单，就是「工作」项目下的所有任务和「未指派」这两个状态的结合，再加上一个 `shared`。因为未被指派的任务，包括没有共享的任务，只有把 `shared` 和 `!assigned` 结合，才是共享状态中的，未被指派的任务，才符合这个情境。

团队中创建过久且未被执行的任务

语法：`##工作 & shared & created before: -15 days & !recurring`

这是第二篇文章中 `created before: -15 days & !recurring` 语法的延伸，这里的 `-15` 要根据具体的情况设定。在第二篇文章里它只适用于个人情况，我们现在赋予它团队协作的场景。

首先还是 `##工作`，这个不必多说了。另一个加进来的元素是 `shared`，意为已被共享的任务。它包括共享任务中，已指派的任务和未指派的任务。

要加入 `shared` 是因为在 Todoist 的过滤中，如果不指明指派状态，Todoist 会默认这个过滤不包括指派给别人的任务。换句话说，这个过滤只会出现指派给自己的任务和没指派的任务。

显然，对于一个团队的领导来说这是不够的。比起这些他更需要知道哪个员工连很久之前加的任务都没有完成。所以要用到 `shared` 把所有分享出的任务都过滤出来。

### 协作任务在「今天」的显示

协作的任务只要**不是指派给别人的**，也就是说**没指派的**和**指派给自己的**，截止日期是今天的话，就都会显示在「今天」这个界面中。

从上一篇我们已经知道 Todoist 中的「今天」并不只是个简单的聚合所有完成日期在「今天」的任务。我们可以看出来，它是「Today」和「Overdue」这两个过滤语法的结合体。

结合任务协作的语法，我们可以发现，它还有 `!assigned to: others` 的属性。

## 团队任务共享与个人任务共享并存

多人协作的情境并非只是纯粹的亲友之间或工作同事之间，它们很有可能是并存的关系。拿我个人来说：作为主业，我要和同事共享任务；同时我有个副业，需要和我的伙伴们共享相关任务；并且，我还需要和一些特定的亲友共享任务。在 Todoist 应该如何实现这一点？

同时，因为前文提到的 Todoist 的一些特性，就算在团队任务中，也有一些只属于个人的项目没必要共享，这种情况又该怎么用 Todoist 处理?

### 团队拥有者可以开放权限

使用免费方案的 Todoist 用户也能和 5 个人共享任务，足以满足和身边的人简单共享任务的需求；使用高级方案的用户每个任务的共享人数提高到 25 人；升级到团队方案后，每个任务的共享人数可以提高到 50 人4 。

但是在升级为 Todoist 团队账户后，一些用户可能发现会出现不允许在**非团队项目**里添加其他人的提示，或者其他人无法把自己邀请到他的项目中的情况。这大概是出于保密的考虑，毕竟当 Todoist 可以通过跨项目地邀请共享人，而且邀请完就直接把对方加入到了项目中。如果员工有问题的话，这种机制会导致情报泄漏。但是如果团队的员工信得过，Todoist 也有机制可以让他们在和团队协作的同时，与亲友协作。

只要团队的拥有者在共享项目设置中把相关权限放开即可：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\f22e184865fba7cea5ba161079b6cec6.jpg)

### 「工作」中的个人项目

「工作」这个大项目里的任务，一般是那种常规的任务，模式比较固定。比如我给少数派编辑部设计的工作项目里，有「约稿」、「审稿 & 修改」、「发稿」这三个子项目，这是一个非常常规的流程。然后，再来看我的这个 Todoist 教程：

1. 它放不到这个传统的流程里
2. 和团队中其他人几乎没关系
3. 我本人还没有把整个内容完全设计好，里面内容会随时调整5

好在，Todoist 中对于项目共享的设定不带有层级：顶级项目分享给同事后，其下的子项目也需要被分享，否则它依然会被视为是个人项目。同理，如果一个顶级项目分配给了团队所有人，而子项目只分配给了其中三个人，那么除了这三个人，没有人能看到这个子项目。

因为有这种机制，我们可以把我们的子项目放到工作的顶级项目之下。比如我有一个小的列表组，就叫做「My Shits」，是属于工作范围的，但不需要和别人共享的任务。它的下面有两个子项目「Others」和「Todoist 教程」：

![img](E:\Inbox_cache\Todoist Learning Notes\reference\assets\759cb4f5b7c1b5c11fb5f39b2703175f.png)

「Others」里是我要写的其它文章，「Todoist 教程」不用说就是这一套文章。

1. 新人经常出现这种事。 ↩
2. 关于评论会在以后的文章中再详细介绍。 ↩
3. 两者的区别请看第二篇文章。 ↩
4. 具体有什么区别可以看 Todoist 的付费方案页面。 ↩
5. 比如相信大家都知道的，最近 Todoist 要和谷歌日历联合的事，就会对我内容安排有影响。 ↩