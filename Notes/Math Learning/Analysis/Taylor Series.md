The motivation of *Taylor Series* is to "mimic" other functions using polynomial functions.
So one of the important question is about "how far away we are from the original function?"

So firstly we state the equation:
$$
f_{n}(x) = \sum_{i=0}^n \dfrac{f^{(i)}(a)}{i!}(x-a)^i + R_n(x)
$$
The $R_n(x)$ is the error part.


> [!NOTE] Taylor's Theorem
> There exists a function $h_n: \mathbb R \rightarrow \mathbb R$, s.t.
> $$
> f_{n}(x) = \sum_{i=0}^n \dfrac{f^{(i)}(a)}{i!}(x-a)^i + h_n(x)(x-a)^n
> $$
> and
> $$
> \lim_{x\rightarrow a} h_n(x) = 0
> $$

Taylor's Theorem in fact says that: if $x$ is close enough to $a$, then the error is $o(x-a)^n$.
And that's called **Peano form of the Remainder**.

There are some other form of the remainder, but I found that these are hard for me.
[The Material about Remainders](https://zhuanlan.zhihu.com/p/550513650).

