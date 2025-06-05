People are suffering from random functions who are hard to deal with. Although people find Taylor Expansion already, Taylor Expansion requires not only to have many times derivative, but also a tiny space approximation (like Peano remainder, $x$ should be close enough to $a$).

Therefore, it's necessary to find another approximation.

Think of the functions we have been seen, the power series is the easiest while cos sin are the second easiest.

Define Fourier Expansion:

$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} (a_{n} \cos (nx) + b_{n} \sin (nx))
$$

Assume we can have such a form, how we get the coefficients?

Recall [[Orthogonal Functions#^d9ae17|orthogonal property of sin and cos]].

Thus we can do multiply both side by $\cos(nx)$ and then integrate from $-\pi$ to $\pi$.

$$
\begin{split}

\int_{-\pi}^{\pi} f(x) \cos (nx) \mathrm{d} x &= \pi a_{0} \int_{-\pi}^{\pi} \cos (nx)  \mathrm{d}x + a_{n}\pi \\
&= a_{n} \pi
\end{split}
$$
Therefore:
$$
a_{n} = \dfrac{\int_{-\pi}^{\pi} f(x) \cos(nx) \mathrm{d} x}{\pi}
$$
Same for $b_{n}$, but remember here we exchange the order of integral and sigma, we have to prove uniform convergence to do this (here we just assume if we can how we get the coefficient).

So now we have two main questions. If the form always uniform convergence (so we can use this method also make sure they converge to a function). If the form converges to f or some other function.

Skip the proof and the conclusion is following:

1. if $f$ can be divided into N segments and mono-increase or decrease in each segment.
2. if $x$ is a continuous point or removed or jumped point on $f$, and $\forall \delta \gt 0, \exists L \gt 0, \alpha \in (0, 1]$, such that $|f(x \pm u) - f(x\pm)|\le Lu^{\alpha} \hspace{3em}(0 \lt u \lt \delta)$.
Then Fourier Series converges to $\dfrac{f(x+)+f(x-)}{2}$.
The second condition is called $f(x)$ satisfied Holder condition at $x$ for $\alpha$, when $\alpha = 1$, this also called Lipschitz condition).

The second condition is basically $\mathrm{d}f = \mathcal{O}(u^{\alpha})$, and differential is stronger.

So we can use differential as most functions are beautiful.

(btw, there is no such a condition that is iff to convergence).

You might be wondering u have seen some Fourier Transformation but where is the $e^{-i\omega t}$ something comes from? Although we have some similar integral above but there is nothing to do with $e$ am I right?

You may recall Euler's formula and substitute to get $e$.

But this is only for periodic function, what if we want to approximately get a whole function?

I don't plan to just write down all stuff once more so I will drop the picture here:
![[Pasted image 20250323142941.png]]![[Pasted image 20250323143112.png]]

There we have gotten Fourier Transformation.

Here are some properties that why this is useful:

![[Pasted image 20250323145303.png]]
![[Pasted image 20250323145322.png]]
![[Pasted image 20250323150119.png]]
下面给一个实用的例子。
![[Pasted image 20250323150437.png]]
然后可以引入离散傅里叶变化，这显然和 OI 学的一致，本质就是通过变化和逆变换的矩阵满足的正定关系来转化和逆转化，看似没有减少数据量，但事实上变换后的值较为集中，将一些模很小的强制置零误差仍然让人满意，而且较为连续的数据也可以有更多的处理手段，此外，由于每个点含有原信息的整体信息，所以即使有一些干扰对原信息整体影响也不大。