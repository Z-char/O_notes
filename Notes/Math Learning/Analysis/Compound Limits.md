---
tags:
  - limits
---
Given $\lim_{x\to x_0} g(x) = a, \lim_{u\to u_0} f(u) = A$, be careful we don't have $\lim_{x\to x_0} f\circ g(x) = A$.
In fact, we need an addition restrction.
If we have a $\delta_0 \gt 0$, when $x \in \mathring{U}(x_0, \delta_0), g(x) \neq u_0$. We will have $\lim f\circ g(x) = A$.
Because limit has said nothing about $f(u_0)$, if we have lots of $f(u_0)$, the limit DNE.
Also, if we do have $g(x) = u_0$, but we also have restictions on $f(u_0)$, for example $f$ is continuous, this rule also works.
And that's basically we can use exponentiate and always have:
$$
\lim_{x \to x_0} e^{f(x)} = e^{\lim\limits_{x \to x_0} f(x)}
$$
