---
tags:
  - continuity
---
Uniform continuity is different from continuity.
Continuity is talking about a specific point. When you are using $\delta-\varepsilon$ language, $\delta$ is defined by both $\varepsilon$ and $x_0$.
Talking about uniform continuity, we are talking about an interval.
If $f$ is uniform continuous on interval $I$, that said we will have a $\delta$ only defined by $\varepsilon$, which works for every point in $I$.
As that's hard to describe, we will introduce a new theorem.

>[!THEOREM] Uniform Continuity
>Let's say $f$ is define on interval $X$. $f$ is uniform continuous if and only if for every sequence $\{x_n^\prime\}$ and $\{x^{\prime\prime}_n\}$, if they satisfied $\lim_{n\to\infty} (x_n^\prime - x_n^{\prime\prime}) = 0$, then $\lim f(x_n^\prime) - f(x_n^{\prime\prime}) = 0$.

There is a even more famous theorem.
If $f$ is continuous on a closed interval $[L, R]$, then $f$ is uniform continuous on the same interval. This is called Cantor Theorem.
And we will see if $f$ is continuous on an open interval $(L, R)$, and we also have $f(L^-), f(R^+)$, then $f$ is uniform continuous on interval $(L, R)$. And that's a necessary condition.



