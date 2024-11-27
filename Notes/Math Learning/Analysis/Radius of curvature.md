This is actually a question in physics. But we probably need math to solve for it.
The curvature is defined as:
$$
\kappa = \frac{{\rm d}\theta}{{\rm d}s}
$$
And the radius is defined as:
$$
\rho = \frac{{\rm d}s}{{\rm d}\theta}
$$
As $s = R \theta$.
Let's say the curve is defined by following equations:
$$
\begin{cases}
x=x(t) \\
y=y(t)
\end{cases}
$$
We should notice:
$$
\frac{{\rm d}y}{{\rm d}x} = \tan \varphi
$$
Therefore:
$$
\begin{align}
&\varphi = \arctan \frac{{\rm d}y}{{\rm d}x} = \arctan \frac{y'}{x'}\\
&\frac{{\rm d}\varphi}{{\rm d}t} = \frac{(x')^{2}}{(x')^{2}+(y')^{2}} \frac{y''x' - x''y'}{(x')^2}=\frac{x'y''-x''y'}{(x')^2+(y')^2}
\end{align}
$$
We also know:
$$
\frac{{\rm d}s}{{\rm d}t}=\sqrt{(x')^2+(y')^2}
$$
Consider invariance of the first-order differential form, we can divide them to get either $\rho$ or $\kappa$.
