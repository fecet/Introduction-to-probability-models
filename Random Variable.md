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
下面介绍一些常见的随机变量：

#### 伯努利随机变量

假定一个试验只能有 $0​$ 和 $1​$ 两种状态，那么$X​$的概率质量函数为：
$$
\begin{array}{l}{p(0)=\mathrm{P}\{X=0\}=1-p} \\ {p(1)=\mathrm{P}\{X=1\}=p}\end{array}
$$
这样的 $X$ 称为伯努利随机变量

#### 二项随机变量

假设有 $n​$ 个参数为 $p​$ 的伯努利随机变量，以 $X​$ 记为它们的和，那么 $X​$ 称为具有参数 $(n,p)​$ 的二项随机变量。它的概率质量函数为：
$$
p(i)=\left( \begin{array}{c}{n} \\ {i}\end{array}\right) p^{i}(1-p)^{n-i}, \quad i=0,1, \cdots, n
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

#### 泊松随机变量

假设 $X^*$ 为具有参数 $(n,p)$ 的二项随机变量。当 $n$ 趋近于无穷大：
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

### 连续随机变量

对于连续的随机变量，如果我们也同样地定义它的概率质量函数，它的质量往往为$0$，为此，定义它的概率密度函数。
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
下面介绍一些常见的随机变量：

#### 均匀随机变量

一个变量称为均匀分布在区间$(a,b)$上，如果它的概率密度函数给定为
$$
F(x)=\left\{\begin{array}{c}{\frac{1}{b-a},}&{a<x<b} \\ {0,} & {其他}\end{array}\right.
$$

#### 指数随机变量













