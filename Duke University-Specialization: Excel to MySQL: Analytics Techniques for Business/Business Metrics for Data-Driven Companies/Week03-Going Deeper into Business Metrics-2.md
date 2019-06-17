# Week03-Going Deeper into Business Metrics-2
## Financial Services - Money Management
**资金经理（Money managers ）** 就是被雇佣来用其他人的钱产生回报的专业投资人。而对于财务管理行业而言，也有其所特有的指标：**投资总收益和具体投资经理的表现。** 

这一部分中，我们将着重讨论投资收益和收益波动性（returns and volatility of returns）。

资产收益（Asset returns）的主要计算方式有3种。对于一次性投资而言，未来收益以及年绝对收益率和收益，都可以通过持续累加的或者非持续的收益来进行计算（either as a continually compounded, or as a discreet rate of return.）。虽然这两种方式都是正确的方法，但是其计算结果并不相同。因此，为了计算能够对比的数据，需要使用同一种方法。

### 方法1：计算连续累加的收益（The continuously compounded return）
log以e为底，通常写成自然对数ln（最终的价格除以最初的价格），得到绝对收益。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-4.png" height="300">

举例而言，开始时为$100，最终为$130，于是得到26.24%的最终收益率。如果这是两年的收益，简单地将其除以2，得到每年13.12%的最终收益率。

### 方法2：非连续方法（The discreet method）
最终价格除以初始价格，取得相应的比例再减去1，得到非连续的年回报率。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-5.png" height="300">

这样一来，对于上面同样的例子，如果是连续方法得到26.24%的最终收益率，而使用非连续方法得到30%的最终收益率。

如果这样的收益是两年获得的，那么应该对于 最终价格除以初始价格 进行平方（取几何平均值，实际上是开方），对于2年而言，取比例的1/2方（也就是开平方），得到1.1402，之后减去1等于14.02%。

可以看到两种方法得到不同的收益率，两年期分别为13.12%和14.02%。

当投资根本不是一次完成的，而是在几个不同时间点进行的，那么用于衡量全部回报的指标是确定单一固定的非连续的年回报率，并将其带入到每一笔投资中，如果对其进行求和就能够得到最终受益。而这个衡量指标就是 **内部收益率（Internal rate of return, IRR）。**

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-6.png" height="320">

假设在第0年投入了1百万美元，在第1年追加1百万，而在第4年卖出获得了5百万。设收益率为x，代数式如下：(1+x)^4 + (1+x)^3 = 5，大多数计算器都有IRR功能，因此可以计算出x=29.62%。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-7.png" height="240">

接下来我们计算一系列年收益的几何平均值，假设4年的收益分别为+25%、-18%、+10%和-4%。我们想知道如果在一开始我们1$，那么在4年过去之后，我们将拥有多少资金？计算这个数值的方式就是每年依次计算，即1 * (1 + 0.25) * (1 - 0.18) * (1 + 0.10) * (1 - 0.04) = 1.0824。因此，这四年的绝对收益率为8%多一点。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-8.png" height="300">

如果想要将其转化为年化收益率，则将1.0824开4次方，得到2%，也就是说这四年中年化收益率的几何平均值为2%。这能够说明4年的年化收益率为2%，但是无法说明收益率的范围在-18%到+25%之间。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-9.png" height="300">

但是我们非常想知道这四年中收益的分布情况。在金融中有这样的一个基本假设，即当所有其他条件都相同的情况下，如果如果两个投资机会具有相同的长期回报，我们更倾向于不会产生大范围波动而具有持续收益的投资机会。我们将用于计算聚集和分散状况的指标叫做 **标准偏差（standard deviation）** ，在金融学里面，标准偏差称为 **收益浮动率（Volatility of returns）。**

收益浮动率属于风险测量指标，该指标越大，投资风险也就越大。对于像债券这样具有固定回报的投资，是没有机会出现损失的，因此也叫做无风险收益，收益浮动率为0。

## The Equivalence of Different Returns –The Sharpe Ratio
这里有一个非常有趣的事实，那就是对于一定的投资能力而言，一个投资经理可能声称多种的投资回报率，而事实上，他们在管理技巧方面都是一样的。而造成投资回报率不同的原因或许仅仅是由于他们是否使用了 **杠杆（leverage）** ，或者说是否用了借贷了资金来达到他们的投资目标。

在接下来的讨论中，假设投资管理公司能够以1%的利率进行借贷，某个投资经理凭借自己的能力寻找到了一支年回报率9%、预期回报波动率15%的股票。

假设这个经理投资了2千万，并且他已经通过投资产生了收益，最终卖出得到了2千180万，这样计算出收益率就是21.8 / 20 - 1 = 9%，这时候就有了(15%, 9%)的点。

现在假定同一个经理以1%的利率借款，比如他另外借了1千万（50%的杠杆），现在他们有2 + 1 = 3 千万了。他在年初进行投资，在同样的收益率下，最后卖出时会得到3270万，但是在计算收益率之前，他需要偿还1千万美元的贷款并且支付1%的利息，所以他实际拥有的收益是260万。计算收益率时就是(32.7 - 10.1) / 20 - 1 = 13%。

这样一来，仅仅通过借1千万，基金经理就能使同样一支股票上的收益率增长到13%，但是天上不会掉馅儿饼，他们需要支付的代价是：波动率上升了15%，所以此时的波动率变成了22.5%，产生了一个（22.5%, 13%）的点。

同样的，2千万的资金 和2千万的借款（100%的杠杆）会得到一个(30%, 17%)的点。

但是，当画出图之后，你就会发现这些点都在一条直线上！这说明了，如果我们能够以1%的利率借贷，就能够位于这条直线上的任意收益率。这反映了 **在理论上，投资经理如果用足够的杠杆就可以获得任何他们想要的收益率，但同时他们的波动率也会以相同的速度增长。（What that means is that in theory, a money manager could generate any return they wanted if the took enough leverage. But, their volatility of return would increase just as quickly.）**

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-10.png" height="320">

以上的原理正是 **夏普率（Sharpe ratio）** 所涵盖的。








