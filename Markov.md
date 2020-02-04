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
这恰好符合矩阵乘法，如果记 $P^{(n)}$ 为 $n$ 步转移矩阵 $P^{n}_{ij}$，那么有
$$
{P}^{(n+m)}={P}^{(n)} \cdot {P}^{(m)}
$$
如果对于某个 $n \geq 0$ ，有$P_{i j}^{n}>0$，也就是说 $n$ 步后，状态 $i$ 转移至状态 $j$ 是可能的， 那么称状态 $j$ 是从状态 $i$ 是**可达的**。

互相可达的两个状态 $i$ 和 $j$ 称为互通的，记为 $i \leftrightarrow j$

 两个互通的状态，称为在同一个状态类内，两个状态类或者相同，或者不相交。如果马尔科夫链仅有一个类，那么它称为**不可约的**。

对于任意状态 $i$ ,如果
$$
\sum_{n=1}^{\infty} P_{i i}^{n}=\infty
$$
那么它称为**常返态**，反正，称为**暂态**，常返性是一个类性质。

在常返态中，我们以 $f_i$ 记为开始在状态 $i$ 迟早将再进入该状态的概率。现在推广该定义，以 $f_{i,j}$ 表示
$$
f_{i,j}=P\{对于某个n>0有X_n=j|X_0=i\}
$$
如果 $i$ 是常返的，且 $i \leftrightarrow j$，那么 $f_{i,j}=1$。

如果状态 $j$ 是常返的，记从 $j$ 开始再次返回 $j$ 的期望转移次数为 $m_j$：
$$
m_{j}=\mathrm{E}\left[N_{j} | X_{0}=j\right]
$$
其中，
$$
N_{j}=\min \left\{n>0 : X_{n}=j\right\}
$$
若 $m_{j}<\infty$，则称状态$j$ 是**正常返**的，否则，则是**零常返**的。

记一个马尔科夫链在状态 $j$ 停留的长程时间比例为 $\pi_j$，那么
$$
\pi_{j}=\frac{1}{m_{j}}
$$
正常返也是一个类性质。

注意到：
$$
\pi_{j}=\sum_{i} \pi_{i} P_{i, j}
$$
所以，为了确认各状态的长程比例，可在如下线性系统中求得
$$
\left\| \pi\right\| _1=1\\
P\cdot \pi=\pi
$$
其中 $\pi$ 是向量 $\{\pi_0, \pi_1, \pi_2, \cdots\}$。

如果该线性系统无解，则该马尔科夫链是暂态或者是零常返的，并且一切 $\pi_j=0$。

长程比例又被称为**平稳概率**，这是由于如果
$$
\mathrm{P}\left\{X_{0}=j\right\}=\pi_{j}, \quad j \geqslant 0
$$
那么
$$
\mathrm{P}\left\{X_{n}=j\right\}=\pi_{j}
$$

### MC生成的数据模型的平均转移次数

为确定模型 $i_{1}, \cdots, i_{k}$ 出现的转移次数, 记
$$
N(i_1,i_2,\cdots,i_k)=\min\left\{n \geqslant k: X_{n-k+1}=i_{1}, \cdots, X_{n}=i_{k}\right\}
$$
为了求,
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{0}=r\right]
$$
记 $\mu(i,j)$ 为从状态 $i$ 到状态 $j$ 的平均转移次数, 则
$$
\mu\left(i, i_{1}\right)=1+\sum_{j \neq i_{1}} P_{i, j} \mu\left(j, i_{1}\right), \quad i \geqslant 0
$$
这来自于对于第一次转出取条件.

下面考虑对于一个MC, 生成一个与之相伴的 MC, 称之为 $k$ 链, $k$ 链的状态是原MC之前 $k$ 个状态的数组.

> 例如 $k=3$, $X_2=4,X_3=1,X_4=1$, $k_4=(4,1,1)$

记 $k$ 链的平稳概率为 $\pi\left(j_{1}, \cdots, j_{k}\right)$
$$
\pi\left(j_{1}, \cdots, j_{k}\right)=\pi_{j_{1}} P_{j_{1}, j_{2}} \cdots P_{j_{k-1}, j_{k}}
$$
于是
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | k_{0}=(i_{1}, i_{2}, \cdots, i_{k})\right]=\frac{1}{\pi\left(i_{1}, \cdots, i_{k}\right)}
$$
如果该模型前后不重叠, 则
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | k_{0}=(i_{1}, i_{2}, \cdots, i_{k})\right]=\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{0}=i_{k}\right]
$$
否则, 若该模型有大小为 $j$ 的重叠, 即
$$
\left(i_{k-j+1}, \cdots, i_{k}\right)=\left(i_{1}, \cdots, i_{j}\right), \quad j<k
$$
那么
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | k_{0}=(i_{1}, i_{2}, \cdots, i_{k})\right]=\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{1}=i_{1},X_2=i_2,\cdots, X_j=i_j\right]
$$
对于不重叠的情况而言
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{0}=i_{k}\right]=\mu\left(i_{k}, i_{1}\right)+\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{1}=i_{1}\right]
$$
所以
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{0}=r\right]=\mu\left(r, i_{1}\right)+\frac{1}{\pi\left(i_{1}, \cdots, i_{k}\right)}-\mu\left(i_{k}, i_{1}\right)
$$
对于重叠的情况, 由于
$$
N\left(i_{1}, i_{2}, \cdots, i_{k}\right)=N\left(i_{1}, \cdots, i_{j}\right)+N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{1}=i_{1},X_2=i_2,\cdots ,X_j=i_j
$$
所以有
$$
\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{k}\right) | X_{0}=r\right]=\mathrm{E}\left[N\left(i_{1}, i_{2}, \cdots, i_{j}\right) | X_{0}=r\right]+\frac{1}{\pi\left(i_{1}, \cdots, i_{k}\right)}
$$
由于 $j<k$, 可以在有限次内转化为非重叠的情况.



> 设 $r$ 为在状态空间上定义的有界函数, 那么
> $$
> \lim _{N \rightarrow \infty} \frac{\sum_{n=1}^{N} r\left(X_{n}\right)}{N}=\sum_{j=0}^{\infty} r(j) \pi_{j}
> $$

假设 $a_j(N)$ 为MC在 $1,2,\cdots,N$ 时间内处于状态 $j$ 的时间, 则
$$
\sum_{n=1}^{N} r\left(X_{n}\right)=\sum_{j=0}^{\infty} a_{j}(N) r(j)
$$
注意到
$$
\lim_{N\to\infty}\frac{a_j(N)}{N}=\pi_j
$$
于是结论得证.

