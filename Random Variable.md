## Random Variable

在做试验时，我们关心的往往是实验结果的函数，即定义在样本空间上的实值函数，称为**随机变量**。

如果随机变量取可数个可能值，它称为是**离散的** *(discrete)*。否则，它称为是**连续的**(*continuous*)。

随机变量 $X$ 的**累计分布函数**，简称分布函数，记为：
$$
F(b)=P(X\leq b)
$$

### 离散随机变量

对于离散随机变量，定义**概率质量函数$p(a)$**:
$$
p(a)=P\{X=a\}
$$
它的**期望**为：
$$
E[X]=\sum_{x : p(x)>0} x p(x)
$$
期望可以作用于关于随机变量 $X$ 的函数, 
$$
\mathrm{E}[g(X)]=\sum_{x : p(x)>0} g(x) p(x)
$$
所以
$$
\mathrm{E}[a X+b]=a \mathrm{E}[X]+b
$$
随机变量 $X$ 的期望值也成为**均值**或 $X$ 的一阶矩. $E[X^n]$ 称为 $X$ 的 **$n$ 阶矩**.

我们还关心随机变量的方差, 它定义为
$$
\operatorname{Var}(X)=\mathrm{E}\left[(X-\mathrm{E}[X])^{2}\right]
$$
假设 $X$ 连续, 具有密度 $f$, 并记 $E[X]=\mu$, 那么:
$$
\begin{aligned} \operatorname{Var}(X) &=\mathrm{E}\left[(X-\mu)^{2}\right]=\mathrm{E}\left[X^{2}-2 \mu X+\mu^{2}\right] \\ &=\int_{-\infty}^{\infty}\left(x^{2}-2 \mu x+\mu^{2}\right) f(x) \mathrm{d} x \\ &=\int_{-\infty}^{\infty} x^{2} f(x) \mathrm{d} x-2 \mu \int_{-\infty}^{\infty} x f(x) \mathrm{d} x+\mu^{2} \int_{-\infty}^{\infty} f(x) \mathrm{d} x \\ &=\mathrm{E}\left[X^{2}\right]-2 \mu \mu+\mu^{2}=\mathrm{E}\left[X^{2}\right]-\mu^{2} \end{aligned}
$$
这样我们得到:
$$
\operatorname{Var}(X)=\mathrm{E}\left[X^{2}\right]-(\mathrm{E}[X])^{2}
$$
下面介绍一些常见的随机变量：

#### 伯努利随机变量

假定一个试验只能有 $0​$ 和 $1​$ 两种状态，那么$X​$的概率质量函数为：
$$
\begin{array}{l}{p(0)=\mathrm{P}\{X=0\}=1-p} \\ {p(1)=\mathrm{P}\{X=1\}=p}\end{array}
$$
这样的 $X$ 称为伯努利随机变量

容易计算伯努利随机变量的期望：
$$
\mathrm{E}[\mathrm{X}]=0(1-p)+1(p)=p
$$


#### 二项随机变量

假设有 $n​$ 个参数为 $p​$ 的伯努利随机变量，以 $X​$ 记为它们的和，那么 $X​$ 称为具有参数 $(n,p)​$ 的二项随机变量。它的概率质量函数为：
$$
p(i)=\left( \begin{array}{c}{n} \\ {i}\end{array}\right) p^{i}(1-p)^{n-i}, \quad i=0,1, \cdots, n
$$

它的期望为：
$$
\begin{aligned} \mathrm{E}[X] &=\sum_{i=0}^{n} i p(i)=\sum_{i=0}^{n} i \left( \begin{array}{c}{n} \\ {i}\end{array}\right) p^{i}(1-p)^{n-i}=\sum_{i=1}^{n} \frac{i n !}{(n-i) ! i !} p^{i}(1-p)^{n-i} \\ &=\sum_{i=1}^{n} \frac{n !}{(n-i) !(i-1) !} p^{i}(1-p)^{n-i}=n p \sum_{i=1}^{n} \frac{(n-1) !}{(n-i) !(i-1) !} p^{i-1}(1-p)^{n-i} \\ &=n p \sum_{k=0}^{n-1} \left( \begin{array}{c}{n-1} \\ {k}\end{array}\right) p^{k}(1-p)^{n-1-k}=n p[p+(1-p)]^{n-1} \\ &=n p \end{aligned}
$$


#### 几何随机变量

假设存在一串连续的伯努利随机变量，记为$X_1,X_2, \ldots,X_n​$, 令$X​$为：
$$
X=\min \left\{n>0 : X_{n}=1\right\}
$$
这样的 $X​$ 称为几何随机变量，它的概率质量函数为:
$$
p(n)=\mathrm{P}\{X=n\}=(1-p)^{n-1} p, \quad n=1,2, \cdots
$$
容易验证：
$$
\sum_{n=1}^{\infty} p(n)=p \sum_{n=1}^{\infty}(1-p)^{n-1}=1
$$

下面计算它的期望：
$$
E[x]=\sum_{n=1}^{\infty} n p(1-p)^{n-1}=p \sum_{n=1}^{\infty} n q^{n-1}
$$
其中 $q=1-p$，注意到
$$
n q^{n-1}=\frac{\mathrm{d}}{\mathrm{d} q}\left(q^{n}\right)
$$
结合导数的可加性：
$$
E[X]=p \sum_{n=1}^{\infty} \frac{\mathrm{d}}{\mathrm{d} q}\left(q^{n}\right)=p \frac{\mathrm{d}}{\mathrm{d} q}\left(\sum_{n=1}^{\infty} q^{n}\right)=p \frac{\mathrm{d}}{\mathrm{d} q}\left(\frac{q}{1-q}\right)=\frac{p}{(1-q)^{2}}=\frac{1}{p}
$$


#### 泊松随机变量

假设 $X^*​$ 为具有参数 $(n,p)​$ 的二项随机变量。当 $n​$ 趋近于无穷大：
$$
p(k)=\lim_{n\rightarrow \infty} \left( \begin{array}{c}{n} \\ {k}\end{array}\right) p^{k}(1-p)^{n-k}
$$
令$\lambda=np$，则：
$$
\lim_{n\rightarrow \infty} \left( \begin{array}{c}{n} \\ {k}\end{array}\right) p^{k}(1-p)^{n-k}=\lim_{n\rightarrow \infty} \left( \begin{array}{c}{n} \\ {k}\end{array}\right) （\frac{\mu}{n}）^{k}(1-\frac{\mu}{n})^{n-k}
$$
注意到：
$$
\left( \begin{array}{c}{n} \\ {k}\end{array}\right) （\frac{\mu}{n}）^{k}(1-\frac{\mu}{n})^{n-k}=\frac{n(n-1) \cdots(n-i+1)}{n^{i}} \frac{\lambda^{i}}{i !} \frac{(1-\lambda / n)^{n}}{(1-\lambda / n)^{i}}
$$
且：
$$
\lim_{n\rightarrow \infty} \left(1-\frac{\lambda}{n}\right)^{n} = \mathrm{e}^{-\lambda}\\
\lim_{n\rightarrow \infty} \frac{n(n-1) \cdots(n-i+1)}{n^{i}}=1\\
\lim_{n\rightarrow \infty} \left(1-\frac{\lambda}{n}\right)^{i} = 1
$$
于是
$$
P\{X=i\}\approx \mathrm{e}^{-\lambda} \frac{\lambda^{i}}{i !}
$$
将其中的约等号换成等号，这样的$X$称为泊松随机变量。

我们可以如下地计算它的期望：
$$
E[X]=\sum_{i=0}^{\infty} \frac{i \mathrm{e}^{-\lambda} \lambda^{i}}{i !}=\sum_{i=1}^{\infty} \frac{\mathrm{e}^{-\lambda} \lambda^{i}}{(i-1) !}=\lambda \mathrm{e}^{-\lambda} \sum_{i=1}^{\infty} \frac{\lambda^{i-1}}{(i-1) !}
$$
替换哑变量：
$$
E(X)=\lambda e^{-\lambda} \sum_{k=0}^{\infty} \frac{\lambda^{k}}{k !}
$$
注意到，$\sum_{k=0}^{\infty} \lambda^{k} / k !=\mathrm{e}^{\lambda}$，所以
$$
E[x]=\lambda
$$


### 连续随机变量

对于连续的随机变量，如果我们也同样地定义它的概率质量函数，它的质量往往为$0​$，为此，定义它的概率密度函数。
$$
f(a)=\lim_{x\rightarrow a}\frac{P(a\leq X\leq x)}{x-a}
$$
由累计分布函数知：
$$
P(a\leq X\leq x)=F(x)-F(a)
$$
这就是说
$$
\frac{\mathrm{d}}{\mathrm{d} a} F(a)=f(a)
$$
从而对于任意集合$B$:
$$
\mathrm{P}\{X \in B\}=\int_{B} f(x) \mathrm{d} x
$$
由此可以定义连续随机变量 $X$ 的期望值：
$$
\mathrm{E}[X]=\int_{-\infty}^{\infty} x f(x) \mathrm{d} x
$$
下面介绍一些常见的随机变量：

#### 均匀随机变量

一个变量称为均匀分布在区间$(a,b)$上，如果它的概率密度函数给定为
$$
F(x)=\left\{\begin{array}{c}{\frac{1}{b-a},}&{a<x<b} \\ {0,} & {其他}\end{array}\right.
$$

它的期望为：
$$
E[x]=\int_{\alpha}^{\beta} \frac{x}{\beta-\alpha} \mathrm{d} x=\frac{\beta+\alpha}{2}
$$


#### 指数随机变量

假设 $X^*$ 为以 $\lambda t$ 为参数的泊松随机变量，则 $\lambda$ 表示该事件发生的*频率*。令 $X$ 表示该事件发生的间隔，则若$X>t$，意味着 $t$ 时间内，$X=0$。
$$
P(X>t)=P(X^*=0)=\frac{(\lambda t)^{0} e^{-\lambda t}}{0 !}=e^{-\lambda t}
$$
所以它的累计分布函数为：
$$
F(a)=1-P(X>a)=1-e^{-\lambda a}
$$
求导可得它的概率密度函数：
$$
f(x)=\left\{\begin{array}{l}{\lambda \mathrm{e}^{-\lambda x}}&x\ge0 \\ {0}&x<0\end{array}\right.
$$
计算它的期望：
$$
\mathrm{E}[X]=\int_{0}^{\infty} x \lambda \mathrm{e}^{-\lambda x} \mathrm{d} x
$$
利用分部积分，我们有：
$$
\int \lambda  x e^{-\lambda  x} \, dx=-xe^{-\lambda x}-\frac{e^{-\lambda x }}{\lambda }
$$
所以：
$$
\mathrm{E}[X]=-x\left.\mathrm{e}^{-\lambda x}\right|_{0} ^{\infty}-\left.\frac{\mathrm{e}^{-\lambda x}}{\lambda}\right|_{0} ^{\infty}=\frac{1}{\lambda}
$$

#### 伽马随机变量

伽马随机变量是$n$个以$\lambda$ 为参数的指数随机变量的和的分布。概率密度函数为：
$$
f(x)=\left\{\begin{array}{l}{\frac{\lambda \mathrm{e}^{-\lambda x}(\lambda x)^{\alpha-1}}{\Gamma(\alpha)}}&x\ge0 \\ {0}&x<0\end{array}\right.
$$
其中
$$
\Gamma(\alpha)=\int_{0}^{\infty} \mathrm{e}^{-x} x^{\alpha-1} \mathrm{d} x
$$

#### 正态随机变量

如果 $X$ 的密度由：
$$
f(x)=\frac{1}{\sqrt{2 \pi} \sigma} \mathrm{e}^{-(x-\mu)^{2} / 2 \sigma^{2}}, \quad-\infty<x<\infty
$$
给出，则称 $X​$ 是具有参数 $ \mu​$ 和 $\sigma^2​$ 的正态随机变量。

如果 $X$ 以参数 $ \mu$ 和 $\sigma^2$ 的正态地分布，那么 $Y=\alpha X+ \beta$ 以参数 $\alpha \mu+\beta$ 和 $\alpha ^2 \sigma^2$ 正态地分布。这是由于：
$$
F_{Y}(a)=\mathrm{P}\{\hat{Y} \leqslant a\}=\mathrm{P}\{\alpha X+\beta \leqslant a\}=\mathrm{P}\left\{X \leqslant \frac{a-\beta}{\alpha}\right\}=F_{X}\left(\frac{a-\beta}{\alpha}\right)
$$
代入CDF：
$$
F_Y(a)=\int_{-\infty}^{(a-\beta) / \alpha} \frac{1}{\sqrt{2 \pi} \sigma} \mathrm{e}^{-(x-\mu)^{2} / 2 \sigma^{2}} \mathrm{d} x
$$
作换元 $y=\alpha x+\beta$:
$$
\frac{dy}{dx}=\alpha
$$

$$
F_Y(a)=\int_{-\infty}^{(a-\beta) / \alpha} \frac{1}{\sqrt{2 \pi} \sigma}\frac{1}{a} \mathrm{e}^{-\frac{\left(\frac{y-b}{a}-\mu \right)^2}{2 \sigma ^2}} \mathrm{d} x
$$

整理得：
$$
f_{Y}(v)=\frac{1}{\sqrt{2 \pi} \alpha \sigma} \exp \left\{\frac{-(y-(\alpha \mu+\beta))^{2}}{2(\alpha \sigma)^{2}}\right\}
$$
