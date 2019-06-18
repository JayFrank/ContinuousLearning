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

夏普率就是在无风险收益率的情况下，投资资产的超额收益率除以投资资产收益率的波动率。夏普率非常有趣，它是收益指标除以风险指标，其代表了多少单位的风险能够带来多少单位的收益。在投资收益率为9%，而收益波动指标为15%的情况下，夏普率就是(9% - 1%)  / 15% = 0.533，其中 9% - 1%代表投资组合收益率。而对于收益率13%，波动率为22.5%的情况下，计算其夏普率为(13% - 1%) / 22.5% = 0.553，得到了相同的夏普率。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-11.png" height="320">

从逻辑上来讲，这也是合理的，因为所有的点都落在这条斜率不变的线上，因此这条线上的任意一点都代表了相同的投资能力，因此如果你想确定哪个投资经理能力更强，分析其夏普率即可。

## Four Types of Money Managers and Their Performance Metrics
不同的衡量标准适用于不同的投资经理，而我们将投资经理分成以下四种：
* 指数基金经理（Index fund managers）
* 共同基金经理（Mutual fund managers）
* 风险投资和私募股权经理（Venture capital and private equity investors）
* 对冲基金经理（Hedge fund managers）

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-12.png" height="320">

股票指数是帮助投资者追踪整个股票市场的，而不是用来评估某一只股票的表现的。距离而言，标准普尔500指数（The S&P 500 index）代表了美国 **市值（Market capitalization）** 最高的500个公司的股票市场整体情况。这里需要解释一下，**市场价值是等于一股公司普通股的股价乘以公司潜在的可购买和出售的股份总额（Market capitalization is the current market price of one share of a companies common stock multiplied by the total number of shares of stock of that company that potentially could be bought and sold. ）。**

举个例子，一个公司每股的股价是52美元，有500万可被交易的股份，因此这个公司的市场价值是52美元乘以500万即2.6亿。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-13.png" height="240">

标准普尔500指数不只是简单的500个股票的平均值。每个股票价值取五百分之一或者是2%，这是等权重指数，然而标准普尔500指数是市值加权指数，每个公司股价占比的变化是由他们的市场价值占总体的比重计算得来的。打个比方，苹果公司现在的市场价值是6660亿，五百强企业总共的市场价值是十五万亿，所以苹果公司股价变化对于指数的影响是用666除以15,000，即4.44%。

当前一个很流行的投资策略叫做 **被动投资（Passive investing）** ，也叫做指数投资（Index investing），就是购买并持有长期投资，这种投资尽可能刺激指数的表现。如果想要在标准普尔500指数中进行被动投资，可以购买道富银行(State Street) 旗下的SPDR S&P 500 ETF（查找符号SPY）。SPY创建于1993年，目前是世界上最为活跃的交易资产之一。

指数基金经理不需要选择股票，而是管理被动投资。但他们也面对具有挑战的工作，他们需要致力于长期保持平衡，使得每只股票的持有比例与指数市场中的比例相同，同时尽量减少 **交易成本（Transaction costs）** 。

指数基金经理的表现由两个因素来评定，即他们所管理的基金的表现与指数的关系有多紧密以及他们的费用率有多低。大多数指数基金会非常紧密地追随相应的指数，一年之内千分之一的差异往往都是不可接受的，因此评定被动投资经理的主要因素是他们的 **费用率（Expense ratio）** 。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-14.png" height="220">

费用率等于花在运营基金的费用除以基金资产的市场价值，运营费用包括市场营销的综合的和管理的费用，但最主要的是基金经理收入产生的费用，但是费用率不包括购买和卖出基金资产时的费用。SPY当前的费用率仅仅为0.0945%，这听起来很不错，然而每年的费用支出是1.27亿。

根据发行SBY的道富银行(State Street)在过去几年中的数据统计来看，80%的专业投资经理会从标准普尔500指数中选择股票。而且如果投资经理随机选择组合，也就是他们只计算股票在总市值中的比重，那么也能够跑赢50%的基金经理。

然而，大多数人仍然选择和所谓的共同基金经理合作来进行投资。共同基金经理会从众多股票中选择一些股票，一种方式是购买特定公司规模的股票，靠市值来区分大、小、微三种类型企业，或者在特定市场、行业以及特定的国家或者国家集团（如金砖四国）的市场中选取一些股票组合成为股票池，这样股票池里的所有股票平均收益就可以用来衡量基金经理的表现。

**评价共同基金经理表现的方式主要有三种：**

1. 超额收益（Excess returns）：如果以标准普尔500指数作为他们的基准，当标普500指数上涨了8%，而一个经理从标准普尔500指数中所选的30支股票上涨了12%，那么这个经理基于这个基准的超额收益就是4%。对于超额收益方法而言，其中存在的一个问题是如果标准普尔500指数下跌了20%，一个有4%超额收益的基金经理基于这个基准仍然下跌了16%。因此，除了获得高于基准的超额收益之外，经理还被期望于不要偏离基准太远。 
2. 跟踪误差（Tracking error）：其代表超额收益的标准差，属于风险指标，跟踪误差越小越好。跟踪误差是基金经理投资组合收益和基准指数收益差值的标准差，也就是超额收益的标准差。
3. 信息比率（Information ratio）：信息比率是一种结合了超额收益和跟踪误差的测量方法，信息比率等于超额收益除以跟踪误差。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-15.png" height="200">

举个例子计算信息比率情况：

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week03-16.png" height="300”>

## Venture Capital and Private Equity Investors
风险资本投资和私募股权投资不同于基金和对冲基金，他们有几个显著的不同点，基金管理人并不会让投资者提前付清所有投资资金，相反，投资者会作出承诺将投资资金分期分批投入。一个期限为五至七年的典型基金里，所投资的资金会按照基金管理人的需求分批流入，一个大的机构型的投资者可能会对一个风险资本基金做出两千万的投资承诺，再将投资额分为八份，每份为250万，在四到五年时间内分批投资。投资者们之所以这样做是因为风险资本投资和私募股权投资需要较长的时间来寻找发展和规划投资项目。此外，一个投资公司通常会有多个投资项目，这些项目时长横跨多年，在投资者真正需要这些投资款之前，外部的资金来源并不想将他们的钱放在这个静止的资金池里，他们更想把这些钱投资在其他的可以快速变现的短期投资。因为投资者们为基金分批分期地投入现金，几年内衡量基金表现的最佳标准就是基金的内部收益率，这个不连续的复合收益率，也是是基于基金实际收到的投资额得出的。

对冲基金对于它们可投资项目限制没有共同投资基金那么多。对冲基金可以卖空，这意味着它们可以通过组合交易，在股票价格下跌时盈利。对冲基金也可以对多种资产进行投资，其中包括期权及衍生产品（options and derivatives），对冲基金的投资并不限于某个产业，所以用产业基准来衡量对冲基金是不准确的。实际上，为了最大化的分散投资，对冲基金的投资者们常常期望该基金能够尽量少受主要资本市场表现的影响。一个成功的对冲基金在牛市的时候表现出色，而在熊市的时候表现也不俗。

当然，基金表现的好不好关键指标还是主要体现于多年来的较高的年收益率，此外，夏普指数也是衡量基金表现的标准。而且对冲基金的操作和所持有的投资比起共同投资基金来说没有那么明显，但是对冲基金的投资人们对于大幅度跌落非常敏感，因此，对冲基金另一个主要的衡量标准是最大跌幅。

即便一个对冲基金可能表现不错，从2005年到2015年，该对冲基金的年回报率为 15%。但如果期间有一个30%的跌幅，假设是在2007年和2009年的熊市，那么投资者会认为如果我不幸在这段时间投入资金，那么我的投资就会减少30%！投资者们即会立马开始抽回他们的投资，然后对冲基金就会瓦解。与最大跌幅相关的衡量标准是收支平衡所需年份，我们可以将其理解为了弥补最大跌幅的时间段。最大跌幅的绝对值除以年收益率得到的即为收支平衡所需年份。这个数字告诉我们投资者需要多久时间来收回所失去的资金。
