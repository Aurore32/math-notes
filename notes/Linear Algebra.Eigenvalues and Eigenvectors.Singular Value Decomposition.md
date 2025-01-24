---
id: 2yto361ji010ae96sp9iee0
title: Singular Value Decomposition
desc: ''
updated: 1737732558863
created: 1737716370312
nav_order: 11
---
## Defining SVD

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **singular value decomposition** is a factorization of a real or complex $m\times n$ matrix $A$, of the form
$$
A = U \Sigma V^{\dagger}
$$
> where $U$ is a $m\times m$ unitary matrix, $\Sigma$ is a $m\times n$ rectangular diagonal matrix with non-negative real numbers on the diagonal, and $V$ is a $n\times n$ unitary matrix.

> <span style="background-color: #03cafc; color: black;">Definition</span>. In the above factorization, we typically denote the diagonal terms of $\Sigma$, $\sigma_1, \sigma_2, ..., \sigma_n$, as the **singular values** of $A$ (usually reordered so that $\sigma_1 \geq \sigma_2 \geq ... \geq \sigma_n$).

This can be thought of as a generalization of the diagonalization
$$
A = P\Lambda P^{-1}
$$
applicable only for square matrices that have $n$ linearly independent eigenvectors.

## Constructing a possible SVD

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Every real or complex $m\times n$ matrix $A$ has a singular value decomposition.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We prove the above statement by literally willing the factorization into existence through the power of ~~God and anime~~ Hermitian matrices on our side. This is considered to be a "sigma move", and - this is true - is the reason why $\Sigma$ is the letter chosen for SVD.

Begin by defining

> <span style="background-color: #03cafc; color: black;">Definition</span>. A square matrix $H$ is **positive semi-definite** if it has non-negative eigenvalues; a matrix $D$ is **positive definite** if it has strictly positive eigenvalues.

> <span style="background-color: #1eff12; color: black;">Sketch of proof</span>.  
1. Construct a Hermitian matrix $H = A^{\dagger}A$ and prove it is positive semi-definite using the Hermitian form. 
2. Denote the eigenvalues of $H$, all non-negative by virtue of semi-definiteness, as $\lambda_1, ..., \lambda_n$, with corresponding eigenvectors $\mathbf{v_1, v_2, ..., v_n}$.
2. Construct another Hermitian matrix $H' = AA^{\dagger}$. Show that $A\mathbf{v_i}$ are eigenvectors of $H'$, and that $H'$ has the same nonzero eigenvalues as $H$.
3. Using the fact that transformation matrices from the standard orthonormal basis to the orthonormal eigenvectors of a Hermitian matrix are unitary, construct the SVD.

**Part 1: positive semi-definiteness of $H$**.
Let $A$ be a real or complex $m\times n$ matrix, and let $H$ be the $n\times n$ Hermitian matrix
$$
H = A^{\dagger}A\ (=(A^{\dagger}A)^{\dagger})
$$
which, as previously shown, is diagonalizable via the unitary matrix $V$ as
$$
V^{\dagger}H V = \Lambda
$$
where $\Lambda$ is the diagonal matrix of eigenvalues of $H$. Now consider the Hermitian form
$$
\mathbf{x}^\dagger H \mathbf{x} 
$$
for some $n\times 1$ vector $\mathbf{x}$. As we have
$$
\mathbf{x}^\dagger H \mathbf{x} = \mathbf{x}^\dagger A^{\dagger}A \mathbf{x} = (A\mathbf{x})^\dagger (A\mathbf{x}) = |A\mathbf{x}|
$$
with $A\mathbf{x}$ being a vector, this form is always non-negative by virtue of norms being non-negative. We know that Hermitian forms can be simplified onto the principal axes of the eigenvectors via
$$
\mathbf{x}^\dagger H \mathbf{x} = \mathbf{x}^\dagger V \Lambda V^{\dagger}\mathbf{x} = (V^{\dagger}\mathbf{x})^{\dagger}\Lambda(V^{\dagger}\mathbf{x}) = (\mathbf{x}')^{\dagger}\Lambda\mathbf{x'}
$$
which involves only the sum of diagonal terms
$$
\sum_{i=1}^n \lambda_i |\mathbf{x}'_i|^2.
$$
As shown above, this is non-negative; $\mathbf{x}$ can be any vector, so we conclude that the $\lambda_i$ are non-negative. Denote the corresponding values to $\lambda_i$, reordered with $\lambda_1 \geq \lambda_2 \geq ... \geq \lambda_n$, as $\mathbf{v_i}$; supposes also that, after reordering, only the first $r$ eigenvalues are strictly positive ($\lambda_1, ..., \lambda_r$, with the other $n-r$ eigenvalues being zero).

Note here that the eigenvectors $\mathbf{v_i}$ form an orthonormal set because they are the columns of the unitary matrix $V$; thus, each $\mathbf{v_i}$ is a** unit vector.**

**Part 2: constructing $H'$**. Let $\mathbf{v_i}$ be the eigenvectors of $H$ as above, with 
$$
H\mathbf{v_i} = A^{\dagger}A\mathbf{v_i} = \lambda_i \mathbf{v_i}.
$$
Define
$$
\mathbf{u_i} = A\mathbf{v_i},
$$
which is an eigenvector of $H' = AA^{\dagger}$, also Hermitian, as
$$
AA^{\dagger}(A\mathbf{v_i}) = A(A^{\dagger}A\mathbf{v_i})=A(H\mathbf{v_i}) = A(\lambda_i \mathbf{v_i}) =\lambda_i (A\mathbf{v_i}) = \lambda_i \mathbf{u_i},
$$
leading to the conclusion that if $\lambda_i$ is an eigenvalue of $H$, then it is an eigenvalue of $H'$. 

**Part 3: constructing the SVD**. In order to make $\mathbf{u_i}$ orthonormal to construct the unitary matrix $U$ containing the $\mathbf{u_i}$ as columns (as any matrix with orthonormal columns is unitary), consider
$$
\begin{aligned}
\mathbf{u_i}\cdot \mathbf{u_i}&= \mathbf{u_i}^{\dagger}\mathbf{u_i} \\
&= \mathbf{v_i}^{\dagger}A^{\dagger}A\mathbf{v_i} \\
&=\mathbf{v_i}^{\dagger}H\mathbf{v_i} \\
&=\lambda_i\mathbf{v_i}^{\dagger}\mathbf{v_i} \\
&= \lambda_i
\end{aligned}
$$
Therefore, we need to divide each $\mathbf{u}_i$ by $\sqrt{\lambda_i}$. Call these values $\sigma_i = \sqrt{\lambda_i}$. Thus,
$$
\mathbf{u_i} = \frac{A\mathbf{v_i}}{\sigma_i}
$$
form a unitary matrix $U$. The above equation in matrix form can be expressed as
$$
U = AV\Sigma^{-1}
$$
where $\Sigma$ is the diagonal matrix of $\sigma_i$s, which leads to
$$
A = U \Sigma V^{-1}.
$$

> What if we have some eigenvalues equal to zero?

In that case, we will no longer be able to find
$$
\mathbf{u_i} = \frac{A\mathbf{v_i}}{\sigma_i}
$$
for $\sigma_i = \sqrt{\lambda_i} = 0$. However, we can implement a correction: first sort the $\sigma_i$ in descending order as $\lambda_i \geq 0$, owing to $H$ being positive semi-definite. Suppose that $\sigma_1, \sigma_2, ..., \sigma_r$ are strictly positive after sorting, and that $\sigma_{r+1}, ..., \sigma_n$ are all zero. Obtain $\mathbf{u_1, u_2, ..., u_r}$ as above. By the Gram-Schmidt process, it is always possible to find $\mathbf{w_{1}, ..., w_{n-r}}$ such that
$$
\{\mathbf{u_1, u_2, ..., u_r, w_1, ..., w_{n-r}}\}
$$
form an orthonormal set, and thus that the matrix $U$ with columns equal to these vectors is unitary. Accordingly, we can no longer write
$$
U = AV\Sigma^{-1}
$$
where $\Sigma$ is a square matrix with the singular values $\sigma_i$ on its diagonal, as $\sigma_{r+1}, ..., \sigma_n$ are zero and make $\Sigma$ non-invertible; instead, we write directly
$$
U\Sigma = Av
$$
where $\Sigma$ has rows equal to zero corresponding to the columns $\mathbf{w_1}, ..., \mathbf{w_{n-r}}$ of $U$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The $m$ columns of $U$ are referred to as the **left-singular vectors** of $A$; the $n$ columns of $V$ are referred to as the **right-singular vectors**.

## Interpretations of the SVD

> <span style="background-color: #03cafc; color: black;">Geometric interpretation</span>.

The SVD decomposes any $m\times n$ matrix $A$, itself representing a linear map from $\mathbb{R^n \to R^m}$, into
$$
A = U\Sigma V^{-1}
$$
or three linear maps $V^{-1}, \Sigma$, and $U$ applied in that order, where $\Sigma$ is diagonal and $U$ and $V$ are unitary. Unitary matrices (and their inverses) map one orthonormal basis to another, and thus they can be thought of as **rotations** or **reflections**: they "rotate" or "reflect" the original basis, sometimes in combination, to form the new one. Thus, the SVD tells us that any linear map $A: \mathbb{R^n \to R^m}$ is equivalent to three maps applied in sequence:
1. The rotation/reflection matrix $V^{-1}$.
2. The enlargement matrix $\Sigma$, which enlarges the vector in some directions by a scalar multiple and may also make the other directions disappear (as $\Sigma$ maps from $\mathbb{R^n \to R^m}$.)
3. The rotation/reflection matrix $U$.

Note that the notion of a "rotation/reflection" only really makes sense if $U$ and $V$ are real, i.e. they are orthogonal instead of unitary.

> <span style="background-color: #03cafc; color: black;">Series interpretation.</span>

The SVD can be thought of as a matrix analogue of functional series like the Taylor or Fourier series. To observe this, note that
$$
A = \begin{bmatrix}
\mathbf{u_1} & \mathbf{u_2} & ... & \mathbf{u_m} \end{bmatrix}
\begin{bmatrix}
\sigma_1 & 0 & 0 & ... \\
0 & \sigma_2 & 0 & ... \\
0 & 0 & \sigma_3 & ... \\
\vdots & \vdots & \vdots & \ddots \\
0 & 0 & 0 & \dots
\end{bmatrix}
\begin{bmatrix}
\mathbf{v_1^\dagger} \\
\mathbf{v_2^\dagger} \\
\vdots \\
\mathbf{v_n^\dagger}
\end{bmatrix}
$$
Which leads to
$$
A = \begin{bmatrix}
\mathbf{u_1} & \mathbf{u_2} & ... & \mathbf{u_m} \end{bmatrix}
\begin{bmatrix}
\sigma_1\mathbf{v_1^\dagger} \\
\sigma_2\mathbf{v_2^\dagger} \\
\vdots \\
\end{bmatrix}
$$
and
$$
A = \sum_{i=1}^m \sigma_i\mathbf{u_i}\mathbf{v_i}^{\dagger}
$$
each of which are simpler $m\times n$ matrices, with $\mathbf{u_i}$ being $m \times 1$ and $\mathbf{v_i}^\dagger$ being $1 \times n$. This is useful in contexts such as image decomposition, where a large image stored as a matrix of pixels can be decomposed into simpler incomplete images.

## Applications of SVD

> <span style="background-color: #bc42f5; color: black;">Application</span>. **Linear least-squares**.

Suppose we are trying to fit a multivariate linear regression model to data: for some input in $n$ variables
$$
\mathbf{x} = \begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix},
$$
and some output we want in $m$ variables (most commonly just a single variable)
$$
\mathbf{y} = \begin{bmatrix}
y_1 \\ y_2 \\ \vdots \\ y_m
\end{bmatrix},
$$
can we find a $m \times n$ matrix $W$ such that the systems of linear equations
$$
W\mathbf{x} = \begin{bmatrix}
W_{11}x_1 + W_{12}x_2 + ... + W_{1n}x_n \\
W_{21}x_1 + W_{22}x_2 + ... + W_{2n}x_n \\
\vdots \\
W_{n1}x_1 + W_{n2}x_2 + ... + W_{nn}x_n
\end{bmatrix}
$$
is as close as possible to $\mathbf{y}$, e.g. it minimizes the Euclidean distance $||W\mathbf{x-y}||$ (just one possible metric)?

This is the problem of linear least-squares; if solved correctly, it gives us the **line of best fit** for a set of data, perfect for all your linear regression needs such as predicting the Earth's climate in 2050, mapping your level of respect in me as a human being over time, and forecasting how many chicks you'll pull per year in the next decade (perfectly modeled by a flat line). It is slightly less perfect for modelling needs such as trying to "conquer the stock market" (sorry, Chad, I don't think you're going to become the next Warren Buffett using Excel), tracking my erotic fascination towards Danny DeVito over time (exponential growth), or calculating the gravitational pull between me and your** mom.**

It turns out that the linear least-squares problem is solved using SVD. (It's also solved using multivariable calculus, but the symbol $\nabla$ is an affront to all that is good and holy.) If we write
$$
W\mathbf{x} - \mathbf{y} = U\Sigma V^{-1}\mathbf{x - y}
$$
using SVD on $W$, we have
$$
U\Sigma V^{-1}\mathbf{x - y} = U\Sigma (V^{-1}\mathbf{x}) - UU^{\dagger}\mathbf{y} = U(\Sigma\mathbf{z} - \mathbf{d}),
$$
where $UU^{\dagger} = I$ by definition of a unitary matrix and $\mathbf{z} = V^{-1} \mathbf{x}, \mathbf{d} = U^{-1}\mathbf{y}$. Taking the Euclidean norm gives
$$
||W\mathbf{x-y}|| = (U(\Sigma\mathbf{z} - \mathbf{d}))^{\dagger}U(\Sigma\mathbf{z} - \mathbf{d}) = (\mathbf{z}^{\dagger}\Sigma^{\dagger}-\mathbf{d}^{\dagger})U^{\dagger}U(\Sigma\mathbf{{z-d}})
$$
where $U^{\dagger}U = I$ and disappears, so the above simply equals
$$
\begin{aligned}
(\mathbf{z}^{\dagger}\Sigma^{\dagger}-\mathbf{d}^{\dagger})(\Sigma\mathbf{{z-d}}) \\
= \sum_{i=1}^{m} (\Sigma \mathbf{z} - \mathbf{d})^2_i

\end{aligned}
$$
Supposing there are $r$ nonzero singular values $\sigma_1, \sigma_2, ..., \sigma_r$, for these $r$ values we have 
$$
\sum_{i=1}^r (\sigma_{i}z_{i}-d_i)^2
$$
and for the remaining $m-r$ values, we have
$$
\sum_{i=r+1}^{m}d_i^2.
$$
Both terms are sums of squares and are always non-negative, and so
$$
||W\mathbf{x-y}|| \geq \sum_{i=r+1}^{m}d_i^2
$$
where $\mathbf{d}$ is a constant, with equality holding if and only if
$$
z_i = \frac{d_i}{\sigma_i}
$$
for $i= 1,...,r$.

> <span style="background-color: #bc42f5; color: black;">Application</span>. **Pseudoinverse**.
