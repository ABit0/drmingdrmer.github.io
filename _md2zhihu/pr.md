
原文: [Art of Pull Requests](https://hackernoon.com/the-art-of-pull-requests-6f0f099850f9)

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/cb73d713d92c35af-1*KlreYtsrnlfVdAfyjZjNgw.jpeg)

[正如我之前写的](http://blog.viacom.tech/2017/04/07/effective-remote-teams/)，
我们是一个远程团队，团队成员遍布世界各地。
这意味着code reviews 和 [pull requests](https://hackernoon.com/tagged/pull-requests)必须远程完成。

最近，我们[团队](https://twitter.com/_west_on)的一位成员提出了这样的宣言:

> *作为 PR writer 我会:*
> 
> -   保持PR够小
> -   使用标签表明PR是许多部分之一
> -   发布PR后在Slack上也提一下


> *作为 PR reviewer 我会:*
> 
> -   一有空就review。
> -   只要比以前好就批准吧.
> -   尽量不要reject一个PR, 有时可以发一个tiket来作为这个PR的补充, 或要求下一个PR来补充这个PR.
> -   建议而不是拒绝，特别是当用标签来标识多个部分的时候.


我们来看看这个。 本质是:**PR需要小而快**!

<!--more-->

这也符合[程序员的誓言](http://blog.cleancoder.com/uncle-bob/2015/11/18/TheProgrammersOath.html):

> *我会发布频繁和小的release，这样我就不会妨碍他人工作的推进*。


但是，我们都知道，PR的问题是通常它们要在review状态下持续一段时间。

## 请求越大，review时间越长

我们希望尽可能地接近**head开发方法**，在这种方法中，代码很容易进入master/develop。
我们应该致力于连续的产生好的代码。

我们需要与长期存在的feature分支作斗争，因为它们是所有邪恶的根源!

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/40a532ad9a35e926-0*H1oFzCkF0Qo3RCku.png)

因此，PR需要能够快速地查看，以便快速地合并代码。 但这只适用于小的PR!
你不会在一个大的PR上得到一个好的review，它要花很长时间才能把它merge。
因此，一些公司对每一份PR的行数都有限制。一般来说，它们的长度应该少于300行，否则它们就不适合被review了。

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/53431dbdb471e764-0*hMIZJvQxEDOK0H1k.png)

## PR越长，review的人就越累

如果review很累，开发人员就不想review了。
但是我们需要团队尽可能频繁地检查代码，所以不要让他们感到困难!

## 给出上下文

让review人员更容易理解您的更改。 他们可能不会像你一样熟悉你正在做的事情。
添加一个好的[描述和一些截图](https://hackernoon.com/no-description-provided-8d9e0f3a3abb):

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/3079f56d76c52cbf-0*m1nk8pj1XtuU3ect.png)

## 防止上下文切换

让PR提交者尽早收到review评论，这样他就不需要从他已经在处理的下一个任务，切换回上一个任务.
review花费的时间越长，开发者就越难以从其他任务中切换回来并进行更改。
所以，让你的PR尽可能小，并尽可能频繁地创建它们:至少一天一次! 或者更频繁!

## 审稿人也需要帮助

如果您一天只review一次PR，那么每天打开多个PR的想法对您的团队来说是行不通的。

所以审查经常!

在每一次休息之后，在你开始一张新ticket之前，在每一次[番茄工作法](https://en.wikipedia.org/wiki/Pomodoro_Technique)
之后，或者每次你自己打开一个pull request之后。

我们的团队引入了打开的PR上限, 与看[板中的WIP限制](http://kanbantool.com/kanban-wip-limits)类似。
如果达到限制, 任何人都不允许打开一个PR，首先review别人PR来清空队列!

## 专注于重要的事情

所有的代码样式都应该首先由一些自动化的任务来检查—这不是一个人的任务。
CI应该帮助处理大量的代码检查(静态分析:反模式、复杂性、潜在的内存泄漏)，
这样review可以很容易地集中在逻辑和体系结构上。

## 不要太严肃

PR是与团队成员的讨论。 不要把它当成教学课程。 提出建议不要要求他们。
友好。 使用表情符号和动图让读者对你的建议会心一笑:

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/59b011ca05f92e90-0*MkccokzNveEgWzcL.png)

评论是对同事的反馈，也有积极的反馈，如果某件事做得很好，你应该心存感激。

![img](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/84f6f5e8ab67c27f-0*NY4ftERy14vj7nWc.png)

## PR不适合进行长时间的架构讨论

不要过度使用PR讨论。 反正也太迟了，代码已经写好了!
使用其他渠道，如每日/每周的开发者会议。
PR的作用在于，确保质量水平提高，并发现潜在的bug和副作用。
如果你的团队中有下级，试着使用[结对编程](https://hackernoon.com/tagged/programming)，
不要通过PR来教，否则会令人沮丧。

## 如果代码比以前更好，那么批准它

如果发现有什么东西可以变得更好，打开一个issue或ticket。
当然，这需要一种持续处理技术债务的工作文化，这样ticket就不会被积压淹没。
如果PR只是部分ticket，则它更容易被优先处理。
另一个PR肯定会很快到来，可以立即解决这个问题。

## 不要害怕

在像我们这样的远程工作环境中，当PR可能在一夜之间被合并时可能会很可怕——您甚至没有机会看到或评论请求。
当一个团队成长时，这是正常的。 您不能控制、检查或知道任何一行代码。
接受这一点需要勇气和信任!

原文: [Art of Pull Requests](https://hackernoon.com/the-art-of-pull-requests-6f0f099850f9)

![openacid](https://cdn.jsdelivr.net/gh/drmingdrmer/drmingdrmer.github.io@master-md2zhihu-asset/pr/a6ce5c783e584559-qrcode-text.png)



Reference:

