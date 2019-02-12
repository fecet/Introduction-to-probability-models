# Conditional Probability and Conditional Expectation

## The Discrete Case

Recall that for any two events $E$ and $F$, the conditional probability of $E$ given $F$ is defined by
$$
P(E | F)=\frac{P(E F)}{P(F)}
$$
Hence, if $X$ and $Y$ are discrete random variables, then it’s natural to define the **conditional probability mass function** of $X$ given that $Y=y$, by
$$
\begin{aligned} p_{X|Y}(x | y) &=P\{X=x | Y=y\} \\ &=\frac{P\{X=x, Y=y\}}{P\{Y=y\}} \\ &=\frac{p(x, y)}{p_{Y}(y)} \end{aligned}
$$
the **conditional probability distribution function** by
$$
\begin{aligned} F_{X|Y}(x | y) &=P\{X \leqslant x | Y=y\} \\ &=\sum_{a \leqslant x} p_{X|Y}(a | y) \end{aligned}
$$
the **conditional expectation** by
$$
\begin{aligned} E[X | Y=y] &=\sum_{x} x P\{X=x | Y=y\} \\ &=\sum_{x} x p_{X|Y}(x | y) \end{aligned}
$$

## The Continuous Case

If $X$ and $Y$ have a joint probability density function $f (x, y)$, then the **conditional probability density function** of $X$, given that $Y=y$, is defined for all values of $y$ such that $f_Y(y)>0$,by
$$
f_{X|Y}(x | y)=\frac{f(x, y)}{f_{Y}(y)}
$$
The **conditional expectation** of $X$, given that $Y = y$, is defined for all values of $y$ such that $f_Y (y) > 0,$ by
$$
E[X | Y=y]=\int_{-\infty}^{\infty} x f_{X|Y}(x | y) d x
$$

## Computing Expectations by Conditioning

Denote $E[X | Y]​$ as a function:
$$
E[X | y]=E[X | Y=y]
$$
An extremely important property of it is
$$
E[X]=E[E[X | Y]]
$$
When $X$ and $Y$ are discrete, give a proof of above equation
$$
\begin{aligned} \sum_{y} E[X | Y=y] P\{Y=y\} &=\sum_{y} \sum_{x} x P\{X=x | Y=y\} P\{Y=y\} \\ &=\sum_{y} \sum_{x} x \frac{P\{X=x, Y=y\}}{P\{Y=y\}} P\{Y=y\} \\ &=\sum_{y} \sum_{x} x P\{X=x, Y=y\} \\ &=\sum_{x} x \sum_{y} P\{X=x, Y=y\} \\ &=E[X] \end{aligned}
$$
