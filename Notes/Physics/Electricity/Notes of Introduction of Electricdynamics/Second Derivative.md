If we think of divergence, curl, and gradient all be derivatives, just from different point of view, like partial derivative, then we are able to define second derivative.

But since we use $\mathrm{grad}$ and $\mathrm{div}$ and $\mathrm{curl}$, which is hard to remember, we introduce a new symbol here.

$$
\nabla = \hat{x} \frac{ \partial  }{ \partial x } + \hat{y} \frac{ \partial  }{ \partial y } + \hat{z} \frac{ \partial  }{ \partial z } 
$$
Therefore we know div is just dot product, curl is cross product, and grad is acted upon. This is called "nabla", a vector operator.

#### Divergence of Gradient
Let's consider divergence of gradient first:

$$
\begin{align}
\nabla \cdot (\nabla T) &= \left( \hat{x}\frac{ \partial  }{ \partial x }  + \hat{y}  \frac{ \partial  }{ \partial y } + \hat{z}\frac{ \partial  }{ \partial z }   \right) \cdot \left( \frac{ \partial T }{ \partial x }  \hat{x} + \frac{ \partial T }{ \partial y }  \hat{y} + \frac{ \partial T }{ \partial z }  \hat{z} \right) \\ \\
&= \frac{ \partial ^2T }{ \partial x^2 }  + \frac{ \partial ^2T }{ \partial y^2 }  + \frac{ \partial ^2T }{ \partial z^2 } 
\end{align}
$$
We call this **Laplacian** of $T$, notation as $\nabla^2$. We also have this for a vector function, but it's just an extension of this (take three components and then do $\nabla^{2}$ and make it back to vector).
后面会更深入的分析，目前简单的理解就是，电势求电场之后，电场的散度跟电势的关系，这某种意义上是高斯定理，未来会研究加入磁场后的影响。
#### Curl of Gradient
This is always zero. Let's try to prove. (Also this one is very important, it implies that every field that has potential should has no curl. Like electricity.)

$$
\begin{vmatrix}
\hat{x} & \hat{y} & \hat{z} \\
\hat{x} \frac{ \partial  }{ \partial x }  & \hat{y}\frac{ \partial  }{ \partial y }  & \hat{z} \frac{ \partial  }{ \partial z }  \\
\frac{ \partial T }{ \partial x } \hat{x}  & \frac{ \partial T }{ \partial y } \hat{y} & \frac{ \partial T }{ \partial z }  \hat{z}
\end{vmatrix} = 0
$$
Okay seems like I didn't prove but write down the thing is proof itself as you can Laplace expand the first row and shall see.
Here should be careful as $\nabla \times \nabla$ is not zero, so we can't prove using this.
这就是静电场是无旋场(无旋场等价于有势场)，因而路径无关。
#### Gradient of Divergence
Didn't appear very much in physics. Not equal to divergence of gradient.
#### Divergence of Curl
This is always zero too, readers can prove by themselves. Just make sure you don't use the fraudulent shortcut (using multi-product to get $\nabla \times \nabla$ and then say it's zero).

So we talked the previous zero representing something, what about this one? Well, see [this page](https://wuli.wiki/online/HlmPr2.html?utm_source=chatgpt.com). By this we understand how this equality is important. Also, look at the third formula in theorem 1, this is just Biot-Savart law, thus we get $\nabla \cdot B = 0$ (so this equality implies that every field that has vector potential should has no source.) By the way, wiki said all $B$ people has found until not satisfied $\nabla \cdot B = 0$, which is one of Maxwell's equation.
也就是无源场一定可以找到一个矢势场，磁场永远都会是无源场(目前而言)。 ^388151

#### Curl of Curl
So $\nabla \times (\nabla \times\vec{v}) = \nabla(\nabla \cdot\vec{v}) - \nabla^2v$, so there is really nothing new.

### Conclusion
So there is really 2 second derivatives we care about, the gradient of divergence and Laplacian one.

另外，对于这三种求导，显而易见的是我们可以定义相对应的积分，对于梯度很显然就是原函数(势能)差，对于散度则是散度定理(一个体内部的流入流出就是边界的总流量)，对于旋度则是斯托克斯定理(内部的旋转要么互相抵消要么到边界上)，如果这个面闭合了，则旋度为 0。

另外，对于这三种求导，也可以分别定义分部积分，只不过需要先研究求导乘积之后是如何拆开的，然后积分即可。
