# Introduction of Taylor Expansion
The motivation of *Taylor Series* is to "mimic" other functions using polynomial functions.
So one of the important question is about "how far away we are from the original function?"

So firstly we state the equation:
$$
f_{n}(x) = \sum_{i=0}^n \dfrac{f^{(i)}(a)}{i!}(x-a)^i + R_n(x)
$$
The $R_n (x)$ is the error part.

# Peano Remainder
> [!NOTE] Taylor's Theorem
> If $f$ is nth differentiable at point $a$. There exists a function $h_n: \mathbb R \rightarrow \mathbb R$, s.t.
> $$
> f_{n}(x) = \sum_{i=0}^n \dfrac{f^{(i)}(a)}{i!}(x-a)^i + h_n(x)(x-a)^n
> $$
> and
> $$
> \lim_{x\rightarrow a} h_n(x) = 0
> $$

Taylor's Theorem in fact says that: if $x$ is close enough to $a$, then the error is $o(x-a)^n$.
And that's called **Peano form of the Remainder**.
I'm going to prove it here.

## **Proof:**
First we're going to prove a lemma here.
### Lemma:
When $f$ is 2 times differentiable at $x_0$, then $f$ is differentiable in a neighborhood of $x_0$.
#### proof of lemma:
$f^{'}$ is defined in a neighborhood of $x_0$, otherwise, if $\forall \delta \gt 0, \exists x_t \in U(x_0, \delta) \to f'(x_t) \,\text{DNE}$. Then choose $\delta_i = \frac{1}{i}$, and choose a sequence with limit $x_0$ but $\lim_{x\to x_0} f'(x_0) \,\text{DNE}$, therefore $f'$ is not continuous, which in turn implies $f'$ is not differentiable at $x_{0}$, and $f$ can not be 2 times differentiable at $x_{0}$.
**End of proof.**

Now we are prepared to prove.
Let $r_{n}(x) = f(x) - \sum\limits_{k=0}^n \frac{f^{(i)}(a)}{i!}(x-a)^i$. We want to prove $r_{n}(x) = o(x-a)^n$.
First we know $r_{n}(a) = r_{n}^{(1)}(a) = \cdots = r_{n}^{(n)}(a) = 0$. ^55b36c
And we are going to apply LHospital rule:
$$
\begin{align}
\lim_{x \to a} \frac{r_n(x)}{(x-a)^n} &= \lim_{x\to a} \frac{r_n^{(1)}(x)}{n(x-a)^{n-1}} \\
&= \lim_{x\to a} \frac{r_n^{(2)}(x)}{n(n-1)(x-a)^{n-2}}\\
&= \cdots \\
&= \lim_{x\to a} \frac{r_n^{(n-1)}(x)}{n!(x-a)}\\
&= \frac{1}{n!}\lim_{x \to a} \left[\frac{f^{(n-1)}(x)-f^{(n-1)}(a)-f^{(n)}(a)(x-a)}{x-a}\right]\\
&= \frac{1}{n!}\lim_{x \to a}\left[\frac{f^{(n-1)}(x)-f^{(n-1)}(a)}{x-a}-f^{(n)}(a) \right]\\
&= \frac{1}{n!}( f^{(n)}(a) -f^{(n)}(a))\\
&= 0
\end{align}
$$
The reason we can use L's rule is because we have proved that they are both differentiable in a neighborhood and they are both approaching zero (limit should be the value when continuous). The last step is just expand $r$.
**End of proof.**
# Lagrange Error
2024-10-30 upd:

> [!Lagrange Error]
> If $f(x)$ has nth continuous derivative functions on $[a, b]$ and has (n+1)th derivative on $(a, b)$. Let $x_0 \in [a, b]$, $\forall x \in [a, b]$ we have:
> $$
> f(x)=\sum_{i=1}^n \frac{f^{(i)}(x_0)}{i!}(x-x_0)^i + r_n (x)
> $$
> s.t.
> $$
> r_n (x) = \frac{f^{(n+1)}(\xi)} {(n+1)!}(x-x_0)^{n+1}, \xi \in [x, x_0]
> $$

It's the same thing if we choose different point different times.
Should be $(x-x_{0})^{a_{i}}\times \cdots \times (x-x_{n})^{a_{n}}$.

I would not give a proof as I don't fully understand the proof (which constructs a function).

# Integral Error
So, Peano error says "well that's something going to be very very small."
Lagrange error in turn gives the conclusion "yeah it connects to some $\xi$."
In this case, we will certainly ask, so who the error is?

Let $f: \mathbb R \to \mathbb R$ be a function that has $n+1$ continuous derivatives in some neighborhood $U$ of $x=a$. 
Let's say 
$$
f(x)=\sum_{i=1}^{n} \frac{f^{(i)}(a)}{i!}(x-x_0)^{i} + \int_{a}^{x} f^{(n+1)}(t)\dfrac{(x-t)^{n}}{n!} {\rm d}t
$$
That's real for $n = 1$, as that's the definition of integral.
Let's say if $n = k-1$ is true, for $n = k$.

$$
f(x) = \sum\limits_{i=1}^{k-1} \dfrac{f^{(i)}(a)}{i!}(x-a)^{i} + \int_{a}^{x} f^{(k)}(t)\dfrac{(x-t)^{k-1}}{(k-1)!} {\rm d} t
$$
Doing the integral by IBP.
$$
\begin{align}
u = f^{(k)}(t), {\rm d}v=\dfrac{(x-t)^{k-1}}{(k-1)!} {\rm d}t \\
{\rm d}u = f^{(k+1)}(t) {\rm d}t, v = -\dfrac{(x-t)^{k}}{k!} \tag{1}\label{ref_1}
\end{align} 
$$
Then we get:
$$
\begin{align}
uv = -f^{(k)}(x)\dfrac{(x-x)^{k}}{k!} + f^{(k)}(a)\dfrac{(x-a)^k}{k!}
\end{align}
$$
The first term is zero.
So:
$$
\begin{align}
f(x) &= \sum\limits_{i=1}^{k} \dfrac{f^{(i)}(a)}{i!} (x-a)^{i} - \int_{a}^{x} v{\rm d}u \eqref{ref1}\\
&= \sum\limits_{i=1}^{k}\dfrac{f^{(i)}(a)}{i!} (x-a)^{i} + \int_{a}^{x} f^{(k+1)}(t) \dfrac{(x-t)^{k}}{k!}{\rm d}t
\end{align}
$$

Therefore we prove the integral remainder.
This can also prove Lagrange remainder using integral MVT.