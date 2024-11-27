
# Introduction
As we have known that function is just a special case of vector, we can simply define orthogonal between functions.
Let's say if we have a function sequence $g_{n}(x)$ defined in $[a, b]$, if $\forall n,m, g_{m}(x), g_{n}(x)$ is integrable on $[a, b]$.
Also:
$$
\int_{a}^{b}g_{m}(x)g_{n}(x){\rm d}x = \begin{cases} 0, & m\neq n,\\[8pt]
 \displaystyle\int_{a}^{b}g_{n}^{2}(x){\rm d}x \gt 0, & m = n
\end{cases}
$$
They are called **orthogonal sequence of functions**.
Furthermore, if $g_{n}(x)$ is a polynomial with degree $n$, they are called **orthogonal sequence of polynomials**.

# Application
## Legendre Polynomials
#legendre_polynomials
Let's introduce Legendre polynomials here.
$$
p_{n}(x)=\frac{1}{2^{n}n!} \frac{\rm d^{n} }{{\rm d}x^{n}} (x^{2}-1)^{n} \quad (n=0, 1, 2, \cdots)
$$
We can prove that it has n different roots on $(-1, 1)$.

Now let's say $\{p_{n}(x)\}$ are an orthogonal sequence of polynomials on $[-1, 1]$.
To prove that, we simply do the $I_{mn}$ by integration by parts once and once.
And when $n = m$ the integration is $\frac{2}{2n+1}$.

## sin and cos
$\{1, \sin x, \cos x, \sin 2x, \cos 2x, \cdots, \sin nx, \cos nx, \cdots\}$ are an orthogonal sequence of functions on $[-\pi, \pi]$.
In fact, they can be on any interval with length $2\pi$.
