(All following integrable is Riemann integrable.)
> [!Riemann Integrable]
> $f$ must be bounded on interval $[a, b]$ to be integrable.
> Also, $f$ is integrable if and only if for any partition $P$, when $\lambda = \max_{1\le i\le n}(\Delta x) \to 0$, Darboux Big sum has the same limit with Darboux small sum.

See pg239 on *Mathematics Analysis by Jixiu Chen*.
Also, this theorem also state that $f$ is integrable if and only if $\lim\limits_{\lambda \to 0}\sum\limits_{i=1}^{n} \omega_{i} \Delta x_{i} = 0$, where the $\omega_{i}$ is defined by $M_{i}-m_{i}$. In fact, we have if there is a partition $P'$ s.t. $\sum\limits_{i=1}^{n}\omega_{i}\Delta x_{i} \lt \epsilon, \forall \epsilon$, then it's integrable. Just imagine any partition with smaller $\lambda$, called $P$. We call merge $P'$ and $P$ to get a $P*$. And see $|c(P) - C(P*)| + |c(P*) - c(P')|$.

Based on the above necessary and sufficient condition, we have the following corollaries.

When $f$ is continuous on $[a, b]$, then it's integrable. When $f$ is monotonic on $[a, b]$, then it's integrable.

Also, when there is only finite discontinuous points on closed interval $I$, $f$ is integrable.
