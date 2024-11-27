### Conclusion with (-1, 1) matrix
When $n \ge 2$, we have $n!$ numbers which are either 1 or -1.
$n!$ is an even number.
Assuming we have $k_1$ 1s and $k_2$ -1s, they must have same parity, therefore the answer must be even.

Let's list several properties for computing determinants.
First, give the following definition:
$$
\det A = \sum\limits_{k} (-1)^{\tau(i)+\tau(k)}\prod a_{i_{j}k_{j}}
$$

^8c7c67

Basically we choose permutation $i$ to be 1, 2, 3, ..., n.

### Property 1:
$$
\det A = \det A^{T}
$$
That's trivial.

### Property 2:
$$
\begin{vmatrix} 
a_{11} & a_{12} & \cdots & a_{1n} \\ 
\vdots & \vdots &  & \vdots  \\ 
ka_{i1} & ka_{i2} & \cdots & ka_{in} \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
=
k\begin{vmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{i1} & a_{i2} & \cdots & a_{in} \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
$$
By definition, still easy to prove.

### Property 3:
$$
\begin{vmatrix} 
a_{11} & a_{12} & \cdots & a_{1n} \\ 
\vdots & \vdots &  & \vdots  \\ 
b_{1} + c_{1}  & b_{2} + c_{2} & \cdots & b_{n} + c_{n}  \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
=
\begin{vmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\ 
\vdots & \vdots &  & \vdots  \\ 
b_{1}   & b_{2} & \cdots & b_{n}   \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
+
\begin{vmatrix} 
a_{11} & a_{12} & \cdots & a_{1n} \\ 
\vdots & \vdots &  & \vdots  \\ 
c_{1}  &  c_{2} & \cdots &  c_{n}  \\ 
\vdots & \vdots &  & \vdots  \\ 
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
$$
This can also be prove by definition.
### Property 4:
Swap two rows, determinant times $-1$.

### Property 5:
Matrix with two same rows, have determinant 0.
As we can swap two rows and have $x = -x$.

### Property 6:
By 3, we can add a multiple of one row to another row.

### Conclusion with special (a, b) matrix
$$
\begin{vmatrix}
a & b & b & \cdots & b \\ 
b & a & b & \cdots & b \\ 
b & b & a & \cdots & b \\ 
\vdots & \vdots & \vdots & & \vdots \\ 
b & b & b & \cdots & a
\end{vmatrix}
=
[a + (n-1)b] (a-b)^{n-1}
$$
### Laplace Expansion
Using the [[#^8c7c67|definition]] here, we can simply prove that.
But Laplace Expansion can expand according $k$ rows.
More general theorem, we choose $k$ rows $i_{1}\lt i_{2}\lt i_{3} \lt \cdots \lt i_{k}$, we have:
$$
\det A = \sum\limits_{1\le j_{1} \lt \cdots \lt j_{k} \le n} A\begin{pmatrix}i_{1}, \cdots, i_{k} \\ j_{1}, \cdots, j_{k}\end{pmatrix} (-1)^{\sum\limits i_{t} + \sum\limits j_{t}} A\begin{pmatrix}i'_{1}, \cdots, i'_{n-k} \\ j'_{1}, \cdots, j'_{n-k}\end{pmatrix}
$$
That's not hard to prove based on the above definition. 

### Property 7:
$$
\sum\limits_{j=1}^{n}a_{ij} A_{kj} = 0, \quad k \neq i
$$
That's simply true as this equals the determinant we replace row k with row i.

### Vandermonde Determinant
$$
\begin{vmatrix}
1 & 1 & 1 & \cdots & 1 \\ 
a_{1} & a_{2} & a_{3} & \cdots  & a_{n} \\ 
a_{1}^{2} & a_{2}^{2} & a_{3}^{2} & \cdots & a_{n}^{2} \\ 
\vdots & \vdots & \vdots & & \vdots \\ 
a_{1}^{n-1} & a_{2}^{n-1} & a_{3}^{n-1} & \cdots & a_{n}^{n-1}
\end{vmatrix}
= 
\prod_{1 \le j \lt i \le n} (a_{i} - a_{j})
$$
