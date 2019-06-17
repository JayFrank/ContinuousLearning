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

