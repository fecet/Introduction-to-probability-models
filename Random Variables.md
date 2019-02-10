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
is thus the probability density function of $X​$. Similarly, the probability density function of $Y​$ is given by
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

The concept of independence may, of course, be defined for more than two random variables. In general, the $n$ random variables $X_1,X_2,...,X_n$ are said to be independent if, for all values $a_1,a_2,...,a_n$,
$$
P\left\{X_{1} \leqslant a_{1}, X_{2} \leqslant a_{2}, \ldots, X_{n} \leqslant a_{n}\right\}=P\left\{X_{1} \leqslant a_{1}\right\} P\left\{X_{2} \leqslant a_{2}\right\} \cdots P\left\{X_{n} \leqslant a_{n}\right\}
$$

#####  Convolution

It is often important to be able to calculate the distribution of $X + Y$ from the distributions of $X$ and $Y$ when $X$ and $Y$ are independent. 

Suppose first that $X$ and $Y$ are continuous, $X$ having probability density $f$ and $Y$ having probability density $g$. Then, letting $F_{X+Y}(a)$ be the cumulative distribution function of $X$ and $Y$, we have
$$
\begin{aligned} F_{X+Y}(a) &=P\{X+Y \leqslant a\} \\ &=\iint_{x+y \leqslant a} f(x) g(y) d x d y \\ &=\int_{-\infty}^{\infty} \int_{-\infty}^{a-y} f(x) g(y) d x d y \\ &=\int_{-\infty}^{\infty}\left(\int_{-\infty}^{a-y} f(x) d x\right) g(y) d y \\ &=\int_{-\infty}^{\infty} F_{X}(a-y) g(y) d y \end{aligned}
$$
The cumulative distribution function $F_{X+Y}$ is called the **convolution** of the distribution $F_X$ and $F_Y$(the cumulative distribution function of $X$ and $Y$, respectively).

By differentiating Equation above, we obtain that the probabiliy density function $f_{X+Y}(a)$ for $X+Y$ is given by
$$
\begin{aligned} f_{X+Y}(a) &=\frac{d}{d a} \int_{-\infty}^{\infty} F_{X}(a-y) g(y) d y \\ &=\int_{-\infty}^{\infty} \frac{d}{d a}\left(F_{X}(a-y)\right) g(y) d y \\ &=\int_{-\infty}^{\infty} f(a-y) g(y) d y \end{aligned}
$$

#### Covariance and Variance of Sums of Random Variables

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
where the $X_i​$ are independent binomial random variables such that:
$$
X_{i}=\left\{\begin{array}{ll}{1,} & {\text { if the } i \text { th trial is a success }} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$
Hence,
$$
\operatorname{Var}(X)=\operatorname{Var}\left(X_{1}\right)+\cdots+\operatorname{Var}\left(X_{n}\right)=n(p-p^2)=np(1-p)
$$

##### Sampling from a Finite Population: The Hypergeometric

Consider a population of $N$ individuals, some of whom are in favor of a certain proposition. In particular suppose that $Np$ of them are in favor and $N −Np$ are opposed, where $p​$ is assumed to be unknown. 

We are interested in estimating $p$, the fraction of the population that is for the proposition, by randomly choosing and then determining the positions of n members of the population. 

In such situations as described in the preceding, it is common to use the fraction of the sampled population that is in favor of the proposition as an estimator of $p​$. Hence, if we let
$$
X_{i}=\left\{\begin{array}{ll}{1,} & {\text { if the } i \text { th person chosen is in favor }} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$
then the usual estimator of $p$ is $\sum_{i=1}^{n} X_{i} / n$. Let us now compute its mean and variance. 
$$
E\left[\sum_{i=1}^{n} X_{i}\right]=\sum_{i=1}^{n} E\left[X_{i}\right]=np
$$

$$
\operatorname{Var}\left(\sum_{i=1}^{n} X_{i}\right)=\sum_{i=1}^{n} \operatorname{Var}\left(X_{i}\right)+2 \sum_{i<j} \operatorname{Cov}\left(X_{i}, X_{j}\right)
$$

Now, since $X_i$ is a Bernoulli random variable with mean $p$, it follows that:
$$
\operatorname{Var}\left(X_{i}\right)=p(1-p)
$$
For $i \neq j​$,
$$
\begin{aligned} \operatorname{Cov}\left(X_{i}, X_{j}\right) &=E\left[X_{i} X_{j}\right]-E\left[X_{i}\right] E\left[X_{j}\right] \\ &=P\left\{X_{i}=1, X_{j}=1\right\}-p^{2} \\ &=P\left\{X_{i}=1\right\} P\left\{X_{j}=1 | X_{i}=1\right\}-p^{2} \\ &=\frac{N p}{N} \frac{(N p-1)}{N-1}-p^{2} \end{aligned}
$$
Thus, we see that
$$
\begin{aligned} \operatorname{Var}\left(\sum_{i=1}^{n} X_{i}\right) &=n p(1-p)+2 \left( \begin{array}{c}{n} \\ {2}\end{array}\right)\left[\frac{p(N p-1)}{N-1}-p^{2}\right] \\ &=n p(1-p)-\frac{n(n-1) p(1-p)}{N-1} \end{aligned}
$$
and so the mean and variance of our estimator are given by
$$
\begin{aligned} E\left[\sum_{i=1}^{n} \frac{X_{i}}{n}\right] &=p \\ \operatorname{Var}\left[\sum_{i=1}^{n} \frac{X_{i}}{n}\right] &=\frac{p(1-p)}{n}-\frac{(n-1) p(1-p)}{n(N-1)} \end{aligned}
$$
The random variable $\sum_{1}^{n} X_{i}$ is called **hypergeometric** and has a PMF given by
$$
P\left\{\sum_{i=1}^{n} X_{i}=k\right\}=\frac{\left( \begin{array}{c}{N p} \\ {k}\end{array}\right) \left( \begin{array}{c}{N-N p} \\ {n-k}\end{array}\right)}{\left( \begin{array}{l}{N} \\ {n}\end{array}\right)}
$$

##### Sum of Two Independent Uniform Random Variables

 If $X$ and $Y$ are independent random variables both uniformly distributed on $(0, 1)$, then calculate the probability density of $X+Y$:

Since the PDF of $X$ and $Y$ are the same, suppose they are $h$ and $g$:
$$
f(a)=g(a)=\left\{\begin{array}{ll}{1,} & {0<a<1} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$
Recall the equation in Convolution:
$$
f_{X+Y}(a)=\int_{0}^{1} f(a-y) d y
$$
For $0 \leqslant a \leqslant 1$, this yields
$$
f_{X+Y}(a)=\int_{0}^{a} d y=a
$$
For $1<a<2​$, we get
$$
f_{X+Y}(a)=\int_{a-1}^{1} d y=2-a
$$
Hence,
$$
f_{X+Y}(a)=\left\{\begin{array}{ll}{a,} & {0 \leqslant a \leqslant 1} \\ {2-a,} & {1<a<2} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$

##### Sums of Independent Poisson Random Variables

Let $X$ and $Y$ be independent Poisson random variables with respective means $\lambda_1$ and $\lambda_2$. Calculate the distribution of $X$ and $Y​$.


$$
\begin{aligned} P\{X+Y=n\} &=\sum_{k=0}^{n} P\{X=k, Y=n-k\} \\ &=\sum_{k=0}^{n} P\{X=k\} P\{Y=n-k\}\\
&=\sum_{k=0}^{n} e^{-\lambda_{1}} \frac{\lambda_{1}^{k}}{k !} e^{-\lambda_{2}} \frac{\lambda_{2}^{n-k}}{(n-k) !} \\ &=e^{-\left(\lambda_{1}+\lambda_{2}\right)} \sum_{k=0}^{n} \frac{\lambda_{1}^{k} \lambda_{2}^{n-k}}{k !(n-k) !} \\ &=\frac{e^{-\left(\lambda_{1}+\lambda_{2}\right)}}{n !} \sum_{k=0}^{n} \frac{n !}{k !(n-k) !} \lambda_{1}^{k} \lambda_{2}^{n-k} \\ &=\frac{e^{-\left(\lambda_{1}+\lambda_{2}\right)}}{n !}\left(\lambda_{1}+\lambda_{2}\right)^{n} 
\end{aligned}
$$

In words, $X_1+X_2$ has a Poisson distribution with mean $\lambda_1+\lambda_2$.

####  Joint Probability Distribution of Functions of Random Variables

Let $X_1​$ and $X_2​$ be jointly continuous random variables with joint probability density function $f(x_1,x_2)​$. It is sometimes necessary to obtain the joint distribution of the random variables $Y_1​$ and $Y_2​$ which arise as functions of $X_1​$ and $X_2​$ . Specifically, suppose that $Y_1 = g_1(X_1,X_2)​$ and $Y_2 = g_2(X_1,X_2)​$ for some functions $g_1​$ and $g_2​$.

Assume that the functions $g_1$ and $g_2$ satisfy the following conditions:

1.  The equations $y_1 = g_1(x_1,x_2)$ and $y_2 = g_2(x_1,x_2)$ can be uniquely solved for $x_1$ and $x_2$ in terms of $y_1$ and $y_2$ with solutions given by, say, $x_1 =h_1(y_1,y_2)$, $x_2 = h_2(y_1,y_2)$.

2. The functions $g_1$ and $g_2$ have continuous partial derivatives at all points $(x_1,x_2)$ and are such that the following $2\times2​$ determinant at all points.
   $$
   J\left(x_{1}, x_{2}\right)=\left| \begin{array}{ll}{\frac{\partial g_{1}}{\partial x_{1}}} & {\frac{\partial g_{1}}{\partial x_{2}}} \\ {\frac{\partial g_{2}}{\partial x_{1}}} & {\frac{\partial g_{2}}{\partial x_{2}}}\end{array}\right| \equiv \frac{\partial g_{1}}{\partial x_{1}} \frac{\partial g_{2}}{\partial x_{2}}-\frac{\partial g_{1}}{\partial x_{2}} \frac{\partial g_{2}}{\partial x_{1}} \neq 0
   $$

Under these two conditions, $Y_1$ and $Y_2$ are jointly continuous with joint density function given by
$$
f_{Y_{1}, Y_{2}}\left(y_{1}, y_{2}\right)=f_{X_{1}, X_{2}}\left(x_{1}, x_{2}\right)\left|J\left(x_{1}, x_{2}\right)\right|^{-1}
$$

For the joint density function of $Y_1,Y_2,\cdots,Y_n$,where 
$$
Y_1=g_1(X_1,X_2,\cdots,X_n)\\
Y_2=g_2(X_1,X_2,\cdots,X_n)\\
\cdots\\
Y_n=g_n(X_1,X_2,\cdots,X_n)
$$
$X_1,X_2,\cdots,X_n$ is given random variables. The approach is the same:
$$
J\left(x_{1}, \ldots, x_{n}\right)=\left| \begin{array}{llll}{\frac{\partial g_{1}}{\partial x_{1}}} & {\frac{\partial g_{1}}{\partial x_{2}}} & {\dots} & {\frac{\partial g_{1}}{\partial x_{n}}} \\ {\frac{\partial g_{2}}{\partial x_{1}}} & {\frac{\partial g_{2}}{\partial x_{2}}} & {\cdots} & {\frac{\partial g_{2}}{\partial x_{n}}} \\ {\frac{\partial g_{n}}{\partial x_{1}}} & {\frac{\partial g_{n}}{\partial x_{2}}} & {\cdots} & {\frac{\partial g_{n}}{\partial x_{n}}}\end{array}\right|
$$

#### Moment Generating Functions

The moment generating function $\phi(t)$ of the random variable $X$ is defined for all values $t$ by
$$
\phi(t) =E\left[e^{t x}\right] =\left\{\begin{array}{ll}{\sum_{x} e^{t x} p(x),} & {\text { if } X \text { is discrete }} \\ {\int_{-\infty}^{\infty} e^{t x} f(x) d x,} & {\text { if } X \text { is continuous }}\end{array}\right.
$$
We call $\phi(t)​$ the **moment generating function** because all of the moments of $X​$ can be obtained by differentiating $\phi(t)​$.
$$
\phi^{n}(0)=E\left[X^{n}\right], \quad n \geqslant 1
$$

##### Moment Generating Function for Some Common Distributions.

|     Discrete probability distribution      |                          PMF,$p(x)$                          |       Moment Generating Function,$\phi(x)$        | Mean          | Variance            |
| :----------------------------------------: | :----------------------------------------------------------: | :-----------------------------------------------: | ------------- | ------------------- |
|            Binomial with $n,p$             | $\begin{array}{c}{\left( \begin{array}{l}{n} \\ {x}\end{array}\right) p^{x}(1-p)^{n-x}} \\ {x=0,1, \ldots, n}\end{array}$ |         $\left(p e^{t}+(1-p)\right)^{n}$          | $np$          | $np(1-p)$           |
|         Poisson with  $\lambda>0$          | $\begin{array}{l}{e^{-\lambda} \frac{\lambda^{x}}{x !}} \\ {x=0,1,2, \ldots}\end{array}$ | $\exp \left\{\lambda\left(e^{t}-1\right)\right\}$ | $\lambda$     | $\lambda$           |
| Geometric with $0 \leqslant p \leqslant 1$ | $\begin{array}{c}{p(1-p)^{x-1}} \\ {x=1,2, \dots}\end{array}$ |          $\frac{p e^{t}}{1-(1-p) e^{t}}$          | $\frac{1}{p}$ | $\frac{1-p}{p^{2}}$ |

| Continuous probability distribution |                          PMF,$p(x)$                          |       Moment Generating Function,$\phi(x)$        | Mean          | Variance            |
| ---- | ---- | ---- | ---- | ---- |
| Uniform over $(a,b)$ | $f(x)=\left\{\begin{array}{ll}{\frac{1}{b-a},} & {a<x<b} \\ {0,} & {\text { otherwise }}\end{array}\right.$ | $\frac{e^{t b}-e^{t a}}{t(b-a)}$ | $\frac{a+b}{2}$ | $\frac{(b-a)^{2}}{12}$ |
| Exponential with $\lambda>0$ | $f(x)=\left\{\begin{array}{ll}{\lambda e^{-\lambda x}, x>0} \\ {0, \quad x<0}\end{array}\right.$ | $\frac{\lambda}{\lambda-t}$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^{2}}$ |
| Gamma with $(n,\lambda)$ | $f(x)=\left\{\begin{array}{ll}{\frac{\lambda e^{-\lambda x}(\lambda x)^{n-1}}{(n-1) !},} & {x \geqslant 0} \\ {0,} & {x<0}\end{array}\right.$ | $(\frac{\lambda}{\lambda-t})^n$ | $\frac{n}{\lambda}$ | $\frac{n}{\lambda^{2}}$ |
| Normal with ($\mu$,$\sigma^2$) | $\begin{aligned} f(x)=& \frac{1}{\sqrt{2 \pi} \sigma} \ \exp \left\{-(x-\mu)^{2} / 2 \sigma^{2}\right\} \\ &-\infty<x<\infty \end{aligned}$ | $\exp \left\{\mu t+\frac{\sigma^{2} t^{2}}{2}\right\}$ | $\mu$ | $\sigma^2$ |

Another important result is that **the moment generating function uniquely determines the distribution.** That is, there exists a one-to-one correspondence between the moment generating function and the distribution function of a random variable.

##### Poisson Paradigm

The number of successes in n trials that are either independent or at most weakly dependent is, when the trial success probabilities are all small, approximately a Poisson random variable.

To see that this is the case, suppose that the trials are independent, with trial $i$ resulting in a success with probability $p_i$, where the $p_i$ are small.

Let $X_i$
$$
X_{i}=\left\{\begin{array}{ll}{1,} & {\text { if the } i \text { th trial is a success }} \\ {0,} & {\text { otherwise }}\end{array}\right.
$$
and X
$$
X=\sum_{i=1}^{n} X_{i}
$$
Using that $X_i$ is a Bernoulli random variable, its moment generating function is
$$
E\left[e^{t X_{i}}\right]=p_{i} e^{t}+1-p_{i}=1+p_{i}\left(e^{t}-1\right)
$$
and
$$
e^{x} \approx 1+x
$$

$$
E\left[e^{t X_{i}}\right]=1+p_{i}\left(e^{t}-1\right) \approx \exp \left\{p_{i}\left(e^{t}-1\right)\right\}
$$

Because the moment generating function of a sum of independent random variables is the product of their moment generating functions, the preceding implies that
$$
E\left[e^{t X}\right] \approx \prod_{i=1}^{n} \exp \left\{p_{i}\left(e^{t}-1\right)\right\}=\exp \left\{\sum_{i} p_{i}\left(e^{t}-1\right)\right\}
$$
The right side is the moment generating function of a Poisson random variable with $\sum_{i} p​$.

##### Laplace transform

For a nonnegative random variable $X​$, it’s often convenient to define its **Laplace transform $g(t)​$ **,by
$$
g(t)=\phi(-t)=E\left[e^{-t X}\right] As in the case of moment generating functions, it remains true that nonnegative random variables that
have the same Laplace transform must also have the same distribution.
$$
As in the case of moment generating functions, it remains true that nonnegative random variables that have the same Laplace transform must also have the same distribution.

##### Joint Moment Generating Function

 is also possible to define the joint moment generating function of two or more random variables. This is done as follows. For any n random variables $X_1,X_2,\cdots,X_n​$, the joint moment generating function, $\phi(t_1,...,t_n)​$, is defined for all real values of $t_1,...,t_n​$ by
$$
\phi\left(t_{1}, \ldots, t_{n}\right)=E\left[e^{\left(t_{1} X_{1}+\cdots+t_{n} X_{n}\right)}\right]
$$
It can be shown that $\phi(t_1,...,t_n)$ uniquely determines the joint distribution of $X_1,\cdots,X_n​$.

##### The Multivariate Normal Distribution

Let $Z_1,\cdots,Z_n$ be a set of independent standard normal random variables. If, for some constants $a_{ij}$ and $\mu_i$,
$$
\begin{aligned} X_{1} &=a_{11} Z_{1}+\cdots+a_{1 n} Z_{n}+\mu_{1} \\ X_{2} &=a_{21} Z_{1}+\cdots+a_{2 n} Z_{n}+\mu_{2} \\ & \vdots \\ X_{i} &=a_{i 1} Z_{1}+\cdots+a_{i n} Z_{n}+\mu_{i} \\ & \vdots \\ X_{m} &=a_{m 1} Z_{1}+\cdots+a_{m n} Z_{n}+\mu_{m} \end{aligned}
$$
The sum of independent normal random variables is itself a normal random variable, whose mean and variance given by
$$
\begin{aligned} E\left[X_{i}\right] &=\mu_{i} \\ \operatorname{Var}\left(X_{i}\right) &=\sum_{j=1}^{n} a_{i j}^{2} \end{aligned}
$$
Let us determine the joint moment generating function:
$$
\phi\left(t_{1}, \ldots, t_{m}\right)=E\left[\exp \left\{t_{1} X_{1}+\cdots+t_{m} X_{m}\right\}\right]
$$
Note $\sum_{i=1}^{m} t_{i} X_{i}$ is also normally distributed. 
$$
E\left[\sum_{i=1}^{m} t_{i} X_{i}\right]=\sum_{i=1}^{m} t_{i} \mu_{i}\\
\operatorname{Var}\left(\sum_{i=1}^{m} t_{i} X_{i}\right)=\operatorname{Cov}\left(\sum_{i=1}^{m} t_{i} X_{i}, \sum_{j=1}^{m} t_{j} X_{j}\right)=\sum_{i=1}^{m} \sum_{j=1}^{m} t_{i} t_{j} \operatorname{Cov}\left(X_{i}, X_{j}\right)
$$
Recall that if $Y$ is a normal random variable with mean $\mu$ and variance $\sigma^2$, then
$$
E\left[e^{Y}\right]=\phi_{Y}\left.(t)\right|_{t=1}=e^{\mu+\sigma^{2} / 2}
$$
Thus
$$
\phi\left(t_{1}, \ldots, t_{m}\right)=\exp \left\{\sum_{i=1}^{m} t_{i} \mu_{i}+\frac{1}{2} \sum_{i=1}^{m} \sum_{j=1}^{m} t_{i} t_{j} \operatorname{Cov}\left(X_{i}, X_{j}\right)\right\}
$$

##### Sample Variance

Let $X_1,\cdots,X_n$ be independent and identically distributed random variables, each with mean $\mu$ and variance $σ^2$. The random variables $S^2$ defined by
$$
S^{2}=\sum_{i=1}^{n} \frac{\left(X_{i}-\overline{X}\right)^{2}}{n-1}
$$
is called the **Sample variance** of the data. 

To compute $E(S^2)$, we use the identity: 
$$
\sum_{i=1}^{n}\left(X_{i}-\overline{X}\right)^{2}=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}-n(\overline{X}-\mu)^{2}
$$
which is proven as follows:
$$
\begin{aligned} \sum_{i=1}^{n}\left(X_{i}-\overline{X}\right) &=\sum_{i=1}^{n}\left(X_{i}-\mu+\mu-\overline{X}\right)^{2} \\ &=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}+n(\mu-\overline{X})^{2}+2(\mu-\overline{X}) \sum_{i=1}^{n}\left(X_{i}-\mu\right) \\ &=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}+n(\mu-\overline{X})^{2}+2(\mu-\overline{X})(n \overline{X}-n \mu) \\ &=\sum_{i=1}^{n}\left(X_{i}-\mu\right)^{2}+n(\mu-\overline{X})^{2}-2 n(\mu-\overline{X})^{2} \end{aligned}
$$
Hence