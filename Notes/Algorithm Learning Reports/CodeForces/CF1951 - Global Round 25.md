### C
Formal Problem:
Given a sequence $\{a_n\}$, construct a sequence $\{b_n\}$ such that $\sum b_i = k, 0 \le b_i \le m$, minimize $\sum_{i=1}^n a_ib_i + \sum_{1\le i \lt j \le n} b_i b_j$.

Input Restriction:
$n\le 3e5, m \le 1e9, k \le \min(nm, 1e9), a_i \le 1e9$.

Solution:
It's obvious that we can sort sequence A without changing the answer. Then the first sum is minimized when we construct $b = (m, m, m, \cdots, k \bmod m, 0, 0, \cdots, 0)$. The second sum is in fact $(\sum_{i=1}^n b_i)^2 - \sum_{i=1}^nb_i^2 = k^2 - \sum_{i=1}^n b_i^2$. Not surprisingly, $b = (m, m, m, \cdots, k \bmod m, 0, 0, \cdots, 0)$ gives the minimum sum. To prove that, suppose we have two position $i, j$ satisfying $b_i\le b_j \lt m$. $(b_i -1, b_j + 1)$ donates $b_i^2 + b_j^2 + 2 + 2 (b_j - b_i)$ which is bigger than $b_i^2 + b_j^2$.

### D
Formal Problem:
Given $n, k$, construct a sequence $\{a_m\}$ such that $m \le 60, a_i \le 1e18$. $n$ will donate $\left\lfloor \frac{n}{a_1}\right\rfloor$ and $n \bmod a_1$ will remain and so on. Make sure the total donation is $k$.

Input Restriction:
$t \le 1000, n, k \le 1e18$.

Solution:
GuessForces so hard. It's obvious there is no solution when $n \lt k$, and when $n = k$ there is a trivial construction which is 1. When $n \gt k$, at most $\left\lfloor \frac n2\right\rfloor + n\bmod 2$ donation would be donated. When $n$ is even, $2k \le n$, otherwise $2k\le n+1$. Therefore when $2k \gt n + 1$ there is no solution. For $2k \le n + 1$, picking $a_1 = n - k + 1, a_2 = 1$ solves the problem and it's easy to prove.

### E
Formal Problem:
Given a string $s$ consisting of lowercase Latin characters. Give a sequence of some $k$ strings $t_1, t_2, \cdots, t_k$ such that $t_1 + t_2 + \cdots + t_k = s$ and any of $t_i$ is not a palindrome.

Input Restriction:
$\sum |s| \le 1e6$.

Solution:
If $s$ is not palindrome, we're done. Consider we have a $s$ which is palindrome and contains at least two distinct characters. Let $t$ be the first position where $s_1 \not= s_t$, meaning $s_{1, t}$ is not a palindrome. If $s_{t + 1, n}$ is a palindrome, we would say $s$ has the form $AbAb\cdots AbA$ where $A$ consists of $t-1$ $\textsf{a}$ characters (given that $s$ and $s_{t+1, n}$ are palindromes). Then notice if $s$ is $AbA$ there is no solution. If $s$ is $ababababa$ there is no solution too. Otherwise for $AbAbAbA$ or something, $Aba$ and the remaining are both not palindrome. Therefore we find the solution. If we have a solution, there is always a solution such that at most 2 substrings work.

### F
Formal Problem:
Given a permutation $p$ of size $n$, also a non-negative integer $k$. 你需要构造一个排列 $q$，满足 $\rm inv(\it q\rm) + \rm inv(\it qp\rm) = k$, 其中 $\rm inv$ 表示逆序对数，$qp$ 表示将 $p$ 看为置换后对 $q$ 操作的排列。

Input Restriction:
$\sum n \le 3e5, 0\le k \le n(n-1)$.

Solution:
If $p_i \lt p_j$, in $q$ that $q_{p_i}, q_{p_j}$ has the same "inverseness" with $qp_i, qp_j$. Otherwise they have the oppsite "inverseness". So that we shall know parity of the equation. 