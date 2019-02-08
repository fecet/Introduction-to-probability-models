## Random Variables

> [TOC]



### Jointly Distributed Random Variables

#### Joint Distribution Functions

For any two random variables $X$ and $Y$, we define the *joint cumulative probability distribution function* of  $X$ and $Y$ by
$$
F(a, b)=P\{X \leqslant a, Y \leqslant b\}, \quad-\infty<a, b<\infty
$$
The distribution of $X​$ can be obtained from the joint distribution of $X​$ and $Y​$ as follows:
$$
\begin{aligned} F_{X}(a) &=P\{X \leqslant a\} \\ &=P\{X \leqslant a, Y<\infty\} \\ &=F(a, \infty) \end{aligned}
$$
Similarly, the cumulative distribution function of $Y$ is given by:
$$
F_{Y}(b)=P\{Y \leqslant b\}=F(\infty, b)
$$
In the case where $X​$ and $Y​$ are both discrete random variables, define the *the joint probability mass function* of $X​$ and $Y​$ by:
$$
p(x, y)=P\{X=x, Y=y\}
$$
The probability mass function of $X​$ and $Y​$ may be obtained from $p(x, y)​$ by:
$$
p_{X}(x)=\sum_{y : p(x, y)>0} p(x, y)\\
p_{Y}(y)=\sum_{x : p(x, y)>0} p(x, y)
$$
We say that $X​$ and $Y​$ are **jointly continuous** if there exists a function $f(x, y)​$, defined for all real $x​$ and $y​$, having the property that for all sets $A​$ and $B​$ of real numbers
$$
P\{X \in A, Y \in B\}=\int_{B} \int_{A} f(x, y) d x d y
$$
The function $f(x, y)$ is called the joint probability density function of $X$ and $Y$. The probability density of X can be obtained as the following:
$$
\begin{aligned} P\{X \in A\} &=P\{X \in A, Y \in(-\infty, \infty)\} \\ &=\int_{-\infty}^{\infty} \int_{A} f(x, y) d x d y \\ &=\int_{A} f_{X}(x) d x \end{aligned}
$$
where
$$
f_{X}(x)=\int_{-\infty}^{\infty} f(x, y) d y
$$
is thus the probability density function of $X$. Similarly, the probability density function of $Y$ is given by
$$
f_{Y}(y)=\int_{-\infty}^{\infty} f(x, y) d x
$$

Then
$$
\begin{aligned} E[g(X, Y)] &=\sum_{y} \sum_{x} g(x, y) p(x, y)\quad \quad \quad \quad\text { in the discrete case } \\ &=\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y) f(x, y) d x d y \quad \text { in the continuous case } \end{aligned}
$$

####  Independent Random Variables

The random variables $X$ and $Y$ are said to be **independent** if, for all $a$, $b$
$$
P\{X \leqslant a, Y \leqslant b\}=P\{X \leqslant a\} P\{Y \leqslant b\}
$$
In terms of the  joint distribution function $F$, we have that $X$ and $Y​$ are independent if
$$
F(a, b)=F_{X}(a) F_{Y}(b)
$$
When $X​$ and $Y​$ are discrete, the condition reduces to
$$
p(x, y)=p_{X}(x) p_{Y}(y)
$$
while if $X​$ and $Y​$ are jointly continuous, independence reduces to
$$
f(x, y)=f_{X}(x) f_{Y}(y)
$$
An important result concerning independence is the following:

>  If $X$ and $Y$ are independent, then for any functions $h$ and $g​$
> $$
> E[g(X) h(Y)]=E[g(X)] E[h(Y)]
> $$

####  Covariance and Variance of Sums of Random Variables

The covariance of any two random variables $X​$ and $Y​$, denoted by  $\operatorname{Cov}(X,Y)​$, is defined by
$$
\begin{aligned} \operatorname{Cov}(X, Y) &=E[(X-E[X])(Y-E[Y])] \\ &=E[X Y-Y E[X]-X E[Y]+E[X] E[Y]] \\ &=E[X Y]-E[Y] E[X]-E[X] E[Y]+E[X] E[Y] \\ &=E[X Y]-E[X] E[Y] \end{aligned}
$$
Note that if $X​$ and $Y​$ are independent, then it follows that $\operatorname{Cov}(X,Y)=0​$.

In general it can be shown that a positive value of $\operatorname{Cov}(X,Y)$ is an indication that $Y$ tends to increase as $X$ does, whereas a negative value indicates that $Y$ tends
to decrease as $X$ increases.

##### Properties of Covariance

For any random variables $X,Y,Z$ and constant $C$

1. $\operatorname{Cov}(X, X)=\operatorname{Var}(X)​$
2. $\operatorname{Cov}(X, Y)=\operatorname{Cov}(Y,X)​$
3. $\operatorname{Cov}(cX, Y)=c\operatorname{Cov}(X,Y)​$
4. $\operatorname{Cov}(X, Y+Z)=\operatorname{Cov}(X,Y)+\operatorname{Cov}(X,Z)​$

Whereas the first three properties are immediate, the final one is easily proven as follows:
$$
\begin{aligned} \operatorname{Cov}(X, Y+Z) &=E[X(Y+Z)]-E[X] E[Y+Z] \\ &=E[X Y]-E[X] E[Y]+E[X Z]-E[X] E[Z] \\ &=\operatorname{Cov}(X, Y)+\operatorname{Cov}(X, Z) \end{aligned}
$$
The fourth property listed easily generalizes to give the following result:
$$
\operatorname{Cov}\left(\sum_{i=1}^{n} X_{i}, \sum_{j=1}^{m} Y_{j}\right)=\sum_{i=1}^{n} \sum_{j=1}^{m} \operatorname{Cov}\left(X_{i}, Y_{j}\right)
$$
A useful expression for the variance of the **sum of random variables** can be obtained from Equation above as follows:
$$
\begin{aligned} \operatorname{Var}\left(\sum_{i=1}^{n} X_{i}\right) &=\operatorname{Cov}\left(\sum_{i=1}^{n} X_{i}, \sum_{j=1}^{n} X_{j}\right) \\ &=\sum_{i=1}^{n} \sum_{j=1}^{n} \operatorname{Cov}\left(X_{i}, X_{j}\right) \\ &=\sum_{i=1}^{n} \operatorname{Cov}\left(X_{i}, X_{i}\right)+\sum_{i=1}^{n} \sum_{j \neq i} \operatorname{Cov}\left(X_{i}, X_{j}\right) \\ &=\sum_{i=1}^{n} \operatorname{Var}\left(X_{i}\right)+2 \sum_{i=1}^{n} \sum_{j=i} \operatorname{Cov}\left(X_{i}, X_{j}\right) \end{aligned}
$$
If $X_i,\quad i=1,\cdots,n$ are independent random variables, the above formula reduces to:
$$
\operatorname{Var}\left(\sum_{i=1}^{n} X_{i}\right)=\sum_{i=1}^{n} \operatorname{Var}\left(X_{i}\right)
$$

> **Definition**:
>
> If $X_{1}, \dots, X_{n}​$ are independent and identically distributed, then the random variable $\overline{X}=\sum_{i=1}^{n} X_{i} / n​$ is called the **Sample mean**

The following are important properties of sample mean.

1. $E[\overline{X}]=\mu$
2. $\operatorname{Var}(\overline{X})=\sigma^{2} / n$
3. $\operatorname{Cov}\left(\overline{X}, X_{i}-\overline{X}\right)=0, i=1, \ldots, n$

##### Variance of a Binomial Random Variable

Compute the variance of a binomial random variable $X$ with parameters $n$ and $p$.
$$
X=X_{1}+\dots+X_{n}
$$
where the $X_i$ are independent binomial random variables such that:
$$
X_{i}=\left\{\begin{array}{ll}{1,} & {\text { if the } i \text { th trial is a success }} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$
Hence,
$$
\operatorname{Var}(X)=\operatorname{Var}\left(X_{1}\right)+\cdots+\operatorname{Var}\left(X_{n}\right)=n(p-p^2)=np(1-p)
$$

##### Sampling from a Finite Population: The Hypergeometric

