# 第一章：为什么需要函数式编程？

> 函数式程序员： (名词)命名变量"x"，命名函数"f"，然后命名代码模式"zygohistomorphic prepromorphism"

> James Iry ‏@jamesiry 5/13/15  
> https://twitter.com/jamesiry/status/598547781515485184

函数式编程并不是一个新的概念，它几乎伴随着编程的整个历史。然而——我知道我这样说并不公平，但是！——它并不是过去几年在开发者的世界中的一个主流概念，我认为它更多的是在学术领域发光发热。

但是这一切都在改变，对FP感兴趣的人越来越多，在它周围已经形成了一种风潮，而且并不仅仅是在语言层面，还在于它的相关库和框架。你阅读这个文本的原因很可能就是因为你终于意识到FP并不是你能够忽略的东西。或者你也许也像我一样，试图学习了很多次函数式编程，但是总是在和各种术语和数学符号做斗争。

无论你因为什么来阅读这本书，欢迎来到聚会！

## 自信心

我有个非常简单的前提，那就是我作为软件开发（在JavaScript中）老师所做的一切：你不能信任任何你不明白的代码；此外，如果你不能信任或者理解你的代码，那么你可以不相信你编写的代码是适合你的业务的。你只能运行你的代码，然后祈求上天给你好运吧。

信任是什么意思？我的意思是你可以通过阅读来校阅你的代码，而不只是运行。你知道一段代码**将会**做什么，而不仅仅是依靠它**应该**做什么来验证。“也许”比“我们应该”使用的更频繁，我们倾向于依靠通过单元测试来验证我们程序的正确性。我并不是说单元测试是不好的，但是我认为，我们应该更深刻的理解我们所写的代码，这样在运行单元测试之前我们就能肯定它能够通过测试。

我相信构成函数式编程的基础技术来源于这样一种心态，那就是仅仅通过阅读代码就能让我们得到足够的自信心。对于理解了函数式编程，并且勤勉的在程序中运用它们的人，他们写下的代码是很容易阅读和验证的，通过那些他们已经证明过是正确的原则，得到他们想要的运行结果。

我希望从现在开始你将有更多的信心去编写你的代码，轻量级函数式编程原则将会指引你前往正确的方向。

## 交流

为什么函数式编程很重要？为了回答这个问题，我们需要先退一步，我们先来谈谈为什么编程本身很重要。

你听到这个可能会很惊讶，但是我并不认为代码是一组计算机的操作说明。事实上，我认为代码能够操作计算机几乎是个美丽的事故。

我深信，代码有一项更为重要的作用，那就是作为一种与其他人沟通的手段。

你好好回想一下你的经历吧，在你编码的绝大部分时间里，其实你都是在阅读现有的代码。花费所有或者是绝大部分时间来敲出所有全新的代码，而从来不去理别人的（或者我们自己过去）的代码，这是我们很少有的特权。

你知道吗，有一项研究表明，在维护代码的时候，其中70%的时间其实我们都是在阅读并理解它们。我觉得非常震惊，70%！难怪全球程序员平均每天的代码量是5行。然后又我们花了一天中另外的7小时30分钟，来思考这5行代码应该写在哪里！

我想我们应该更多的去关注我们代码本身的可读性。顺带说一下，可读性可不是指最少的字符数。可读性很大程度上受到了熟悉程度的影响（是的，这玩意儿也被研究过）。

因此，如果我们要花更多的时间来让代码变得更加易读易懂，那么函数式编程就是个非常方便的模式。而函数式编程的规范已经进行过了深入的研究并最终确立了起来，它也被证明是可行的。

如果我们使用函数式编程的规范，我相信我们所编写的代码将会更容易理解。一旦我们理解这些规范，它们在代码里将会是熟悉和可识别的，意思就是说当我们阅读代码时我们将会花更少的时间去理解这部分的用意。我们的注意力将会转移到我们都很熟悉的部分，如何建立组装乐高积木，而不是乐高模块本身的意义。

函数式编程（至少，没有很多的专业术语让它更容易接受）是一种很高效的工具用于编写可读性很高的代码。这也是它如此重要的原因。

### 可读性曲线

在这里我想特别提一件非常重要的事情，这件事情已经困扰我很多年了，并且在我写这本书的时候更为明显。

我想这可能也是很多开发者都有的倾向。你，亲爱的读者，通过这里的文章你可能也会发现你也在同样的船上。放宽心，只要你坚持下去，曲线终究会回来的。

<p align="center">
	<img src="https://github.com/getify/Functional-Light-JS/blob/master/fig17.png" width="600">
</p>

我们将会在下一章详细的解释这个问题，对于命令行代码而言，想必你已经写过很多了，比如`if`语句和`for`循环。它们擅长于精确的指导计算机如何去做某件事情。但是对于声明式的代码，以及我们马上就要开始努力学习的函数式代码，它们更加专注于描述代码运行的结果。

让我告诉你一个痛苦的事实，我在编写这本书的时候，有件事情占据了我的绝大部分时间：我付出了很多很多的努力以及编写了很多很多代码，就为了能提高代码的可读性，并最大限度的减少或消除大多数你可能会写错的地方。

希望函数式编程的代码重构能够立即让你的代码变得更加优美优雅、简洁明快，这是不切实际的——至少在一开始这是不现实的。

对于思考如何结构化代码，使数据流更加明显，并帮助阅读你代码的人遵循你的想法，函数式编程是一种非常不同的方式。这个努力是非常值得的，但这也确实是个艰巨的旅程，你最终得到的代码可能看起来并不会具有更多的可读性，直到你花费了大量的时间来练习你的函数式编程。

此外，我的经验告诉我，在我足够理解某段代码的作用之前，我大约需要尝试6次，来把一个命令式的代码片段转换为声明式的函数代码。对我来说，编写函数式的代码更像是一个持续的过程，而不是一个范式到另一个范式的二元转换。

我常常使用“稍后阅读”的方法来测试我写的每一段函数式代码。就是说，我写完代码之后，然后把它晾在一旁几小时或者一整天，然后再尝试用全新的眼光来阅读它。通常而言，它都是非常混乱的，所以我又不断的对它进行调整。