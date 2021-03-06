# Week01-Introducing Business Metrics
## 0 Introduction
未来，如果不将商业数据分析的最佳实践应用于企业运营，任何一家以盈利为目的的公司都无法在竞争激烈的市场上盈利甚至根本无法存活。

而如果要想有效地利用这些大数据，就必须要了解数据问题的整个生命周期。而数据问题的生命周期包括了数据的收集、清洗、分析以及将数据含义传达给其他人。整个生命周期或许需要从程序员到统计学家、沟通专家再到业务领域专家等各种角色。但是，一个人也可以掌握全部的所有知识，成为个人大数据独角兽（personal big data unicorn）。

## 1 What are business metrics?

### Metrics Help Us Ask the Right Questions
**原文：**

Question: What is the highest and best use of a business analyst or a business data analyst?

Answer: To find out the right question to ask.Then, find the best answer you possibly can in the time, and with the resources available.

**译文：**

**问题：** 什么才是对于商业分析或者商业数据分析的最大程度利用呢？

**回答：** 找出需要提出的正确问题。然后找出能够在时间和资源有限的情况下能给出的最佳解决方案。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week01-1.png"  height="240">

那么什么才是正确的问题呢？其实，就是需要在企业流程里面，做出相应的改变，这个改变应该能够满足以下三点中的至少一点：**增加收益、最大化利润或者减少风险。（
To increase revenues, maximize profitability, or reduce our risk.）**

指标(Metrics)就是能够帮助我们提出并且回答正确商业问题的特殊数字。指标也是我们针对商业流程做出改变时能够影响的数字。因此，像某个州的营业税这样固定的数字自然就是商业指标，但是浏览网站广告产生的点击量却是商业指标。

## 2 Distinguishing Revenue, Profitability, and Risk Metrics
所有的商业指标大致可以分为三大类型：
* 收入指标(Revenue metrics)
* 盈利率指标(Profitability metrics)
* 风险指标(Risk metrics)

那么问题来了，当我们拿到一个指标，如何判断其属于以上三类中的哪一类呢？或许有很多种不同的方法，其中一种就是通过分析公司中哪些人员需要依赖这个指标来进行分类。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week01-3.png"  height="240">

**收入指标与销售和市场活动相关；盈利率指标和效率、物流、生产以及运作相关；而风险指标与风险管理相关，并被公司债权人和外部投资者们广泛使用。**

### 收入指标(Revenue metrics)
收入指标是针对外部活动的，它表明该公司在市场营销和销售产品方面到底做的是好是坏，一般而言由市场部VP负责。在销售方面，比如某一时间段内各类产品的销售量以及和去年或前年同期相比的情况、不同地区、不同产品以及新客户和重复购买客户的销量对比情况、以及销售漏斗情况等。在营销方面，包括任何一场市场营销活动的有效性，比如某一个广告到底有多少人看过，或者对于某个营销活动的电子邮件接收者的反馈率等。**总之，每一项和销售直接或间接相关的数据都属于收入指标。**

### 盈利率指标(Profitability metrics)
盈利率指标与公司创造产品、向客户提供服务的流程有效性有关，而这些都是公司负责生产的人员所关心的运营指标，一般而言COO比较关注。举例而言，未销售库存占用了多少现金、由于损坏浪费造成多少产品不能销售。比如因为没有及时销售掉芒果造成它们最后腐烂掉，或者因为产品库存不足而无法满足客户的紧急需求导致失去了销售机会。产品线上有多大比例的产品属于残次品，以及在可变成本，比如原材料、人力、每单位产品上的成本多少等，这些都属于效率指标(Efficiency metrics)。

**需要特别注意的是：即使是一家收入迅速大量增长的公司也可能会因为运作效率低下而导致无法盈利，而成立已久的大型公司虽然收入可增长的空间相对已经很小了，但也可以通过关注并改进运营效率而显著提高其盈利率。**

### 风险指标(Risk metrics)
风险指标与如何监控并降低一家公司所面临的诸多潜在风险有关。如果一家公司每个月在其负债的利息上花费了大部分的净现金流（net cash flow），随后一旦遇到经济不景气等极端情况，即使收入只是小幅减少都有可能造成该公司破产，因此净现金流永远是需要被监控的最重要指标。

风险指标的另一个例子是客户流失率。如果一家基于订阅收入模式的公司客户流失率过高，即新的订阅者在一年中减少，那么长期以往就会带来风险，即潜在的新客户会越来越少，那么就很难带来收入的增长，甚至无法维持收入。一家公司越多的依赖长期重复购买的客户，而更少地依靠转化新的潜在客户，这样从很大程度上降低了风险。关于风险指标的其他例子主要是存在于财务领域，比如发行信用卡的银行要追踪在任何时刻有可能欠款不还的客户的数量以及目前或者未来6个月多大比例的客户可能会欠款不还。

## 3 Distinguishing Traditional and Dynamic Metrics
传统的商业指标最早起源于使用纸笔形式的事实报告，这些指标中的某些指标曾经也是很有创新性的，就如500年前意大利佛伦伦萨的银行家就创造了复式记账的方法。基于这些商业指标做出的商业决策通常是经过数月甚至数年的深思熟虑才做出的，这样的做法是非常重要的并且值得我们去学习，但是我们往往没有时间来这样做。因此需要清晰地定义动态的商业指标，以便在时间紧急的情况下进行沟通。

动态商业指标需要能够正确地指出商业问题，并指出在目前的商业流程中，我们可以 **立刻** 做出哪些改变来增加收入、提高利润或者降低风险。

<img src="https://github.com/JayFrank/ContinuousLearning/blob/master/Duke%20University-Specialization:%20Excel%20to%20MySQL:%20Analytics%20Techniques%20for%20Business/Business%20Metrics%20for%20Data-Driven%20Companies/Link/Week01-2.png"  height="240">

动态商业指标有两个特点：
* 该项指标能否在一个月甚至更短的周期内发生显著的变化？
* 公司所采取的具体措施能否在短期内显著且可见地影响该指标？

如果不能，那么就不是动态指标。

而对于传统指标而言，例如季度收益率会被许多不同的因素影响，并且其中许多因素完全不受业务的控制。
