若函数 $f(x)$ 在区间 $I$ 上是一个下凸函数，则对于任意 $x_i \in I$ 和满足 $\sum_{i=1}^n \lambda_i = 1, \quad \forall i, \lambda_i > 0$。 
$$
f(\sum_{i=1}^n \lambda_i x_i) \le \sum_{i=1}^n \lambda_i f(x_i)
$$
### 证明：
首先，当我们只取两个数的时候，显然有不等式成立，这是下凸的定义。
现在，假设 $k=n-1$ 的时候不等式成立，现在考察 $k=n$ 的情况。
$$
\begin{align}
f(\sum_{i=1}^n \lambda_i x_i) &= f((1-\lambda_n)\sum_{i=1}^{n-1}\frac{\lambda_i}{1-\lambda_n}x_i + \lambda_n x_n)\\
& \le (1-\lambda_n)f(\sum_{i=1}^{n-1}\frac{\lambda_i}{1-\lambda_n}(x_i) + \lambda_n f(x_n)\\
& \le (1-\lambda_n)\sum_{i=1}^{n-1}\frac{lambda_i}{1-lambda_n}f(x_i) + \lambda_n f(x_n)\\
& = \sum_{i=1}^n \lambda_i f(x_i)
\end{align}
$$
第一个等号是显然的，第一个不等号利用 $k=2$ 的不等式，第二个不等式利用 $k=n-1$ 的不等式。
至于这两次不等式的条件为什么满足 ~~读者自证不难~~。
这里只给出不那么直观的部分的证明，我们宣称 $k=2$ 时选取的 $\sum\limits_{i=1}^{n-1}\dfrac{\lambda_i}{1-\lambda_n}x_i$ 这个作为新的 $x$ 仍然在区间 $I$ 里。
注意到，不失一般性，我们可以令 $x_i \gt x_{i+1}$。
那么有：
$$
\sum_{i=1}^{n-1}\frac{\lambda_i}{1-\lambda_n} x_i \gt x_n
$$
这个证明只需要把分母乘过去，后续证明不难，不继续写。

### 应用
注意到 $\ln(x)$ 是比较经典的上凸函数，所以有：
$$
\begin{align}
\frac{1}{p}f(a^p) + \frac{1}{q}f(b^q) \le f(\frac{1}{p}a^p + \frac{1}{q}b^q)\\
\ln(a b) \le \ln(\frac{1}{p} a^p + \frac{1}{q} b^q)\\
a b \le \frac{1}{p}a^p + \frac{1}{q}b^q
\end{align}
$$
在 $a, b \ge 0$ 且 $\frac{1}{p} + \frac{1}{q} = 1$ 时。
