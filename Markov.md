#### Markov

令$\left\{X_{n}, n=0,1,2, \cdots\right\}$是有限个值或可数有限个值的随机过程，它一般是非负数的集合，记
$$
\mathrm{P}\left\{X_{n+1}=j | X_{n}=i, X_{n-1}=i_{n-1}, \cdots, X_{1}=i_{1}, X_{0}=i_{0}\right\}=P_{i j}
$$
这样的随机过程称为**马尔科夫链**，$X_{n+1}$的分布依赖于$X_n$，且独立于过去的状态。以 $P$ 记为该过程的矩阵：
$$
\boldsymbol{P}=\left[ \begin{array}{cccc}{P_{00}} & {P_{01}} & {P_{02}} & {\cdots} \\ {P_{10}} & {P_{11}} & {P_{12}} & {\cdots} \\ {\vdots} & {\vdots} & {\vdots} \\ {P_{i 0}} & {P_{i 1}} & {P_{i 2}} & {\cdots} \\ {\vdots} & {\vdots} & {\vdots}\end{array}\right]
$$
其中，$\sum_{j=0}^{\infty} P_{i j}=1$。

定义 $n$ 步转移概率为：
$$
P_{i j}^{n}=\mathrm{P}\left\{X_{n+k}=j | X_{k}=i\right\}, \quad n \geqslant 0, i, j \geqslant 0
$$
显然，我们有C-K方程：
$$
P_{i j}^{n+m}=\sum_{k=0}^{\infty} P_{i k}^{n} P_{k j}^{m}
$$
这恰好符合矩阵乘法，如果记 $P^{(n)}$ 为 $n$ 步转移矩阵 $P^{n}_{ij}$



