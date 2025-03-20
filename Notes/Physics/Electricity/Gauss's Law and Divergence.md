**Main line:** as we learned Gauss's formula, which is similar to Maxwell's equations, we wonder how we can get Maxwell's equation by Gauss's formula. Then we found the right side, when there is a $F=\dfrac{1}{r^2}$ something, the right part is always zero except including the force source. After we know only surface including source has non-zero value, we define div to find the source (where there is a non-zero value), thus, it's natural to define div. Moreover, we found Gauss's law because the div for point charge is exactly the q. (Thus, it's trivial to get Maxwell's first equation as well as Gauss's law which is just the integration form of Maxwell's equation.)


We have already learned Gauss's formula, Stokz's formula, and Green's formula.

They can all be explained by one idea:
$$
\int_{\partial D} w = \int_{D} {\mathrm{d}} w
$$


However, they are just math equations while we try to use integral in physics.

For vector space, the very natural and old-styled question is fluid velocity in a space.

We care about the amount of water flowed across a closed surface, thus, we call this the "flux".

Let's write down the definition:

$$
\Phi = \oint _{\Sigma} \vec{v} \cdot \mathrm{d}\vec{S}
$$
By Gauss's formula, we simply have:
$$
\oint _{\Sigma} \vec{v}\cdot  \mathrm{d} \vec{S} = \int _{\Omega} \left(  \frac{ \partial P }{ \partial x }  + \frac{ \partial Q }{ \partial y }  + \frac{ \partial R }{ \partial z }   \right) \mathrm{ d} V
$$
We find that when $\Sigma$ approaches zero, this one approaches zero. In fact as $\mathrm{d}V$ keeps the same sign we will have:
$$

\oint _{\Sigma} \vec{v}\cdot  \mathrm{d} \vec{S} = \int _{\Omega} \left(  \frac{ \partial P }{ \partial x }  + \frac{ \partial Q }{ \partial y }  + \frac{ \partial R }{ \partial z }   \right) \mathrm{ d} V = V \left( \frac{ \partial P }{ \partial x }  + \frac{ \partial Q }{ \partial y } + \frac{ \partial R }{ \partial z }  \right)_{\tilde{x}, \tilde{y}, \tilde{z}}
$$
As we known, if there is no "source" or "sink", the flux for an enclosed surface should be zero, thus, we use this to measure if there is a "source" or "sink".

We define divergence for a filed as following:
$$
\mathrm{div}\ \vec{v} = \nabla \cdot \vec{v} = \lim_{ V\to 0} \frac{\oint _{\Sigma} \vec{v}\ \mathrm{d} \vec{S}}{V} = \left( \frac{ \partial P }{ \partial x }  + \frac{ \partial Q }{ \partial y }  + \frac{ \partial R }{ \partial z }  \right)
$$
When $\mathrm{div}\ \vec{v} > 0$, there is a source and vise versa.

So we can rewrite Gauss's formula by:
$$
\oint_{\Sigma} \vec{v} \cdot \mathrm{d} \vec{S} = \int_{\Omega} \mathrm{div}\ \vec{v} \ \mathrm{ d} V
$$
Let's proof why div can represent source or sink.

Imagine a point charge. The electric field is towards outside (can be proven by solving differential equations).

We check div for any other point other than origin:

$$
\frac{ \partial E_{x} }{ \partial x }  = \dfrac{\partial{\dfrac{1}{4\pi \epsilon_{0}} \dfrac{q}{r^2} \dfrac{x}{r} }}{\partial x}
$$

![[Pasted image 20250319193053.png]]

By Calculation we get any div other than origin should be zero (can't say origin as the r is zero).

As we know div is zero all over the world and Gauss's formula works for any enclosed surface without including origin. Any enclosed surface should have zero flux.

And what about a surface including origin?

We can't use Gauss's formula directly as the origin's function doesn't belong to $C^1$.

We can do a trick here similar to what we have done when proving Green's formula in a [n-connect region](https://en.wikipedia.org/wiki/Homotopical_connectivity). Let's assume we dig out a sphere with radius $a$. Applied Gauss's formula we have:
$$
\int_{\Sigma - \sigma} \vec{E} \cdot \mathrm{d} \vec{S} = 0
$$
Therefore:
$$
\int_{\Sigma} \vec{E}\cdot \mathrm{d} \vec{S} = \int_{\sigma} \vec{E} \cdot \mathrm{d} \vec{S}
$$
The detailed calculations are omitted here. Interested readers may perform the integration themselves.

The result is as follows:
$$
\int_{\Sigma} \vec{E} \cdot \mathrm{d} \vec{S} = \dfrac{q}{\epsilon_{0}}
$$
Hence, Gauss's law is proven.