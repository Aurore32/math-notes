## What are forms?
> <span style="background-color: #03cafc; color: black;">Definition</span>. A **form** $F(\mathbf{x})$, with associated **coefficient matrix** $A$ (or $\mathcal{F}(\mathbf{x})$, which has a funny squiggly little tail and is ten times more of a pain in my ass when trying to type this up in LaTeX), is defined as the linear map
$$
F(\mathbf{x}) = \mathbf{x}^{\dagger} A \mathbf{x} = \sum_{i=1}^{n}\sum_{j=1}^n x^{*}_i A_{ij}x_j
$$
> which is the complex scalar product between $\mathbf{x}$ and the image of $\mathbf{x}$ under $A$, $A\mathbf{x}$. The map $F$ maps the $n\times 1$ vector $\mathbf{x}$ to a complex scalar in $\mathbb{C}$: $\mathbb{C^n \to C}$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. If the coefficient matrix of a form $F$ is Hermitian, $F$ is called a **Hermitian form**.

> <span style="background-color: #ffb812; color: black;">Property</span>. Hermitian forms have real outputs; they map to $\mathbb{R}$ instead of $\mathbb{C}$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Consider the form $F(\mathbf{x})$ with Hermitian coefficient matrix $H$. We have
$$
F(\mathbf{x}) = \mathbf{x}^{\dagger} H \mathbf{x}
$$
which, in order to prove is real, requires
$$
F(\mathbf{x})^{\dagger} = F(\mathbf{x})^{*} = F(\mathbf{x})
$$
as the complex conjugate of a scalar is itself if and only if the scalar is real. This implies that
$$
(\mathbf{x}^{\dagger} H \mathbf{x})^\dagger = \mathbf{x}^{\dagger} H^\dagger \mathbf{x} = \mathbf{x}^{\dagger} H \mathbf{x}
$$
which is true as $H^{\dagger} = H$ by property of a Hermitian matrix.

> <span style="background-color: #03cafc; color: black;">Definition</span>. If the coefficient matrix of a form $F$ is a real symmetric matrix, $F$ is called a **quadratic form**.

## Principle axes and simplifying forms

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Any Hermitian form 
$$
F(\mathbf{x}) = \mathbf{x}^{\dagger} H \mathbf{x} = \sum_{i=1}^{n}\sum_{j=1}^n x^{*}_i H_{ij}x_j
$$ 
> can be simplified into a form whose coefficient matrix is diagonal:
$$
F'(\mathbf{x'})=(\mathbf{x'})^{\dagger}\Lambda \mathbf{x'} = \sum_{i=1}^n |x_i|^2 \Lambda_{ii}.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

The above simplification follows from the fact that all Hermitian matrices are diagonalizable by unitary matrices. Let $H$ be the Hermitian matrix which is the coefficient matrix of the form $F(\mathbf{x})$, with
$$
H = U\Lambda U^{-1} = U\Lambda U^{\dagger}.
$$
where $\Lambda$ is the matrix of eigenvalues of $H$. Define $\mathbf{x}' = U^{\dagger} \mathbf{x}$. Thus we have
$$
\begin{aligned}
F(\mathbf{x}) &= \mathbf{x}^{\dagger} H \mathbf{x} \\
&= \mathbf{x}^{\dagger} (U\Lambda U^{\dagger}) \mathbf{x} \\
&= ( \mathbf{x}^{\dagger} U)\Lambda (U^{\dagger} \mathbf{x}) \\
&=(U^{\dagger} \mathbf{x})^{\dagger} \Lambda (U^{\dagger} \mathbf{x}) \\
&= \mathbf{(x')}^{\dagger} \Lambda\mathbf{x'}
\end{aligned}
$$
which corresponds to the norm $F'(\mathbf{x}')$ with corresponding coefficient matrix $\Lambda$, which is a diagonal matrix with diagonal entries equal to the eigenvalues $\lambda_1, \lambda_2, ..., \lambda_n$ of $H$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. For a form $F$ with Hermitian coefficient matrix $H$, define the orthonormal basis eigenvectors corresponding to eigenvalues $\lambda_1, ..., \lambda_n$ as the **principal axes** of $F$.

## Applications of forms

> <span style="background-color: #bc42f5; color: black;">Application</span>. **Hessian matrix.** (Time to bust out the purple.)

Recall from **Differential Equations** that the **Hessian matrix** for a multivariate function $f(x_1,x_2,...,x_n),\ \mathbb{R^n \to R},$ of $n$ variables was defined
$$
H_{ij} = \frac{\partial f}{\partial x_i x_j}
$$
with the matrix-valued function $H(\mathbf{a})$ for some $\mathbf{a}\in\mathbb{R}^n$ defined as 
$$
H_{ij}(\mathbf{a}) = \frac{\partial f}{\partial x_i x_j}(\mathbf{a}).
$$
If $f$ has continuous second-order derivatives, recall that the mixed second-order derivatives commute, i.e.
$$
H_{ij} = \frac{\partial f}{\partial x_i x_j} = \frac{\partial f}{\partial x_j x_i} = H_{ji}
$$
meaning that $H$ is symmetric. Suppose that $f(\mathbf{a})$ is a critical point of $f$, $\mathbf{a}\in\mathbb{R}^n$: $\frac{\partial f}{\partial x_i} (\mathbf{a}) = 0$ for all $i= 1, 2, ..., n$. To analyze whether $\mathbf{a}$ is a maximum, a minimum, or a saddle point, we consider a small perturbation $\mathbf{a + x}$ near $\mathbf{a}$ with $|\mathbf{x}|<<1$. By Taylor's theorem, we have
$$
f(\mathbf{a}+ \mathbf{x}) = f(\mathbf{a}) + \sum_{i=1}^n \mathbf{x}_i \frac{\partial f}{\partial x_i} (\mathbf{a}) +\frac{1}{2} \sum_{i=1}^n\sum_{j=1}^n \mathbf{x}_i \frac{\partial^2 f}{\partial x_i x_j} (\mathbf{a})\mathbf{x}_j
$$
plus terms with powers of $\mathbf{x}$ above $2$. The term containing the first derivatives are zero as the first derivatives themselves are zero. The second-derivative term can be rewritten in matrix form as
$$
\frac{1}{2}\sum_{i=1}^n\sum_{j=1}^n \mathbf{x}_i H_{ij}(\mathbf{a})\mathbf{x}_j = \frac{1}{2}\mathbf{x}^{T} H(\mathbf{a})\mathbf{x}
$$
This is a form with a real symmetric associated coefficient matrix, and as shown above, it can be simplified to the form
$$
(\mathbf{x}')^T \Lambda \mathbf{x}
$$
which allows us to write
$$
f(\mathbf{a+x})-f(\mathbf{a})\approx \frac{1}{2}(\mathbf{x}')^T \Lambda \mathbf{x} = \sum_{i=1}^n \lambda_i(x_i)^2,
$$
which is positive if all the $\lambda_i$ are positive, negative if all the $\lambda_i$ are negative, and indeterminate if there is at least one positive and one negative eigenvalue. These cases correspond to a minimum point (surrounding point $f(\mathbf{a+x})$ larger than $f(\mathbf{a})$), a maximum point (surrounding point $f(\mathbf{a+x})$ smaller than $f(\mathbf{a})$), and a saddle point respectively.

> <span style="background-color: #bc42f5; color: black;">Application</span>.  **Quadric surfaces.**

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **quadric surface** in $n$-dimensions is a defined by the zeroes of a real quadratic polynomial in $n$ variables:

$$
\sum_{i,j=1}^n A_{ij}x_i x_j + \sum_{i=1}^n \mathbf{b}_i x_i + c = 0
$$
> where $\mathbf{b}$ is a $n\times 1$ real vector and $A$ is a $n\times n$ real matrix. This represents a general quadratic polynomial as it encompasses the second-order terms $(x_1x_j)$, the first-order terms $(x_i)$, and the constant term $c$. In matrix form, we can write the above as
$$
\mathbf{x}^T A \mathbf{x + b^T x} + c = 0.
$$
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Any quadric surface can be expressed in the form
$$
(\mathbf{x}')^T \Lambda \mathbf{x'} = k
$$
> for some $n\times 1$ column vector $\mathbf{x}$, diagonal matrix of eigenvalues $\Lambda$, and real constant $k$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Using $A$ as above, define the symmetric matrix
$$
S = \frac{1}{2}(A + A^T).
$$
Taking the transpose of both sides of the quadric surface equation gives
$$
\mathbf{x}^T A^T \mathbf{x + b^T x} + c = 0.

$$
where the latter two terms are not affected by the transpose because the second term is a dot product and the third is a constant. Adding the new equation to the original equation gives
$$
\mathbf{x}^T (A+A^T) \mathbf{x + 2b^T x} + 2c = 0,
$$
or
$$
\frac{1}{2}\mathbf{x}^T (A+A^T) \mathbf{x + b^T x} + c = 0,
$$
leading to 
$$
\mathbf{x}^T S \mathbf{x + b^T x} + c = 0.
$$
As proven previously, $S$ is always diagonalizable and has real eigenvalues by virtue of being symmetric; let $S = Q\Lambda Q^{-1}$, where $Q$ is a transformation matrix of orthonormal eigenvectors and $\Lambda$ is the diagonal matrix of eigenvalues of $S$. Thus we have
$$
(\mathbf{x}')^T \Lambda \mathbf{x' + (b')^T x} + c = 0
$$
for $\mathbf{x'} = Q^{-1} \mathbf{x}$ and $\mathbf{b'} = Q^{-1}\mathbf{b}$. The transformation 
$$
\mathbf{x}' = \mathbf{y} - \frac{1}{2}\Lambda^{-1} \mathbf{b}'
$$
which exists as long as $\Lambda^{-1}$ exists, i.e. there is no zero eigenvalue, results in
$$
\begin{aligned}
\mathbf{(x')}^T \Lambda \mathbf{x}' \\
= ( \mathbf{y}^T - \frac{1}{2}(\mathbf{b}')^T \Lambda^{-1} )\Lambda(\mathbf{y} - \frac{1}{2}\Lambda^{-1} \mathbf{b}') \\
=( \mathbf{y}^T - \frac{1}{2}(\mathbf{b}')^T \Lambda^{-1} )(\Lambda\mathbf{y} - \frac{1}{2} \mathbf{b}') \\
= \mathbf{y}^T \Lambda\mathbf{y}  - \frac{1}{2} \mathbf{y}^T \mathbf{b}' - \frac{1}{2}(\mathbf{b}')^T\mathbf{y}+\frac{1}{4}(\mathbf{b}')^T\Lambda^{-1}(\mathbf{b}') \\
= \mathbf{y}^T \Lambda\mathbf{y}  -  (\mathbf{b}')^T\mathbf{y}+\frac{1}{2}(\mathbf{b}')^T\Lambda^{-1}(\mathbf{b}') - k \\
= \mathbf{y}^T \Lambda\mathbf{y}  -  (\mathbf{b}')^T(\mathbf{y}-\frac{1}{2}\Lambda^{-1}(\mathbf{b}')) - k \\
= \mathbf{y}^T \Lambda\mathbf{y}  -  (\mathbf{b}')^T\mathbf{x} - k

\end{aligned}
$$
where $k$ is a constant (this can be done because every term in the above is a constant). Adding this back to the original equation yields
$$
\mathbf{y}^T\Lambda\mathbf{y}=k

$$
for some constant $k$, and $\mathbf{y} = \begin{bmatrix} x_1' \\ x_2 \\ ... \\ x_n' \end{bmatrix}$ (i.e. because of the transformation $\mathbf{x}' = \mathbf{y} - \frac{1}{2}\Lambda^{-1} \mathbf{b}'
$, we are now operating along the $x_1', x_2', ..., x_n'$ axes instead of the original $x_1, x_2, ..., x_n$ axes.)

> <span style="background-color: #bc42f5; color: black;">Application</span>. **Conic sections**.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Conic sections are a special case of quadric surfaces: specifically, those in 2 variables (e.g. $x$ and $y$). 

> <span style="background-color: #ffb812; color: black;">Proposition</span>. Conic sections have general form
$$
\lambda_1 (x')^2 + \lambda_2 (y')^2 = k,
$$
> or, equivalently,
$$
\frac{(x')^2}{\lambda_2} + \frac{(y')^2}{\lambda_1} = k
$$

> for any constant $k$. Note that $x'$ and $y'$ are intentionally used to indicate that they can be different orthogonal axes than the default $x$- and $y$-axes. This derives from the general form of quadric sections $\mathbf{y}^T\Lambda\mathbf{y}=k$ with eigenvectors $\lambda_1, \lambda_2$, which holds true as long as $\lambda_1 \neq 0$ and $\lambda_2 \neq 0$.

Conic sections (so-called because can be classified into the following forms according to the values of $\lambda_1$ and $\lambda_2$:
1. **Ellipses**. If $\lambda_1\lambda_2 > 0$, the two eigenvalues are of the same sign. As such, the equation can be manipulated to yield
$$
\frac{(x')^2}{a^2}+\frac{(y')^2}{b^2}=1
$$
for some $a$, $b$, which determines an ellipse with width $2a$ and height $2b$ about the origin. Its **principal axes** are given by the $x'$ and $y'$ axes (which are the eigenvectors of the coefficient matrix of the original form), and its scale is determined by $k$.
If $a = b$ or $\lambda_1 = \lambda_2$, the ellipse becomes a circle; any pair of orthogonal principal axes can be chosen.

2. **Hyperbolas.** If $\lambda_1 \lambda_2 < 0$, the conic section is a hyperbola with principal axes coinciding with the $x'$- and $y'$-axes.

3. **Parabolas**. If $\lambda_1 = 0$ or $\lambda_2 = 0$ (but not both at the same time), $\Lambda$ is not invertible; instead, an alternate translation gives a conic section of the form $\lambda_1 (x')^2 + b_2' y_2 = k$, which describes a (quadratic) parabola with principal axes coinciding with the $x'$- and $y'$-axes.    

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. (**Principal axis theorem**). From the fact that symmetric matrices have orthogonal eigenvectors, we observe that the **principal axes** of any conic section are orthogonal.

