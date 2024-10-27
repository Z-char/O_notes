So, the definition of eigenvalues(特征值) for a matrix is following:
$$
A\lambda = \lambda\vec{v}
$$
Now, $\lambda$ is a eigenvalue corresponding to the matrix $A$.
Why do we need eigenvalues though?

First, recall that a flip transformation about x-axis:
$$
A = \begin{bmatrix}1 & 0\\0 & -1\end{bmatrix}
$$
That's a diagonal matrix, which is easy to work with.
But what about a flip transformation about a random line?

Notice that, when we choose the direction vector of the line as our new $\vec{x}$ basis vector, and any vector is orthogonal to $\vec{x}$ as our new $\vec{y}$ basis vector. The flip transformation matrix should be as simple as $A$.

Using the "change the basis rule", we notice that the transformation in our normal basis should be:
$$
\begin{bmatrix}
\vec{x} & \vec{y}
\end{bmatrix}^{-1}
\times
T
\times
\begin{bmatrix}
\vec{x} & \vec{y}
\end{bmatrix}
$$
on the new basis. And the result is guaranteed to be a diagonal matrix, which is easy to work with.
Basically, eigenvalues convert a matrix mulplication into a scaler mulplication.