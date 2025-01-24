---
id: xsw48w148tbq8wcyezaw1hj
title: Eigenspaces
desc: ''
updated: 1736765136876
created: 1736492566547
nav_order: 2
---
> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the set of all vectors corresponding to an eigenvalue $\lambda$ as the **eigenspace** of $\lambda$, denoted $E_{\lambda}$. As this set is the nullspace of $(A-\lambda I)$, it is a subspace.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **algebraic multiplicity** $M_{\lambda}$ of an eigenvalue $\lambda$ of a matrix $A$ as the multiplicity of the root $\lambda$ in the characteristic equation of $A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. For any matrix $A$ with characteristic polynomial of degree $n$, summing across all its eigenvalues yields
$$
\sum_{\lambda} M_{\lambda} = n.
$$
We refer to any eigenvalue $\lambda$ with $M_{\lambda} > 1$ as *degenerate*. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **geometric multiplicity** $m_{\lambda}$ of $\lambda$ as the dimension of its eigenspace: $m_{\lambda} = \dim E_{\lambda}$. (This is equivalent to the number of linearly independent eigenvectors corresponding to $\lambda$: the number of independent solutions to $(A-\lambda I)\mathbf{x=0}$.)

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. For any eigenvalue $\lambda$, we have $m_{\lambda} \leq M_{\lambda}$: the geometric multiplicity is no greater than the algebraic multiplicity.

> <span style="background-color: #1eff12; color: black;">Proof</span> will be shown later.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **defect** of $\lambda$ as $\Delta_{\lambda} = M_{\lambda} - m_{\lambda}$. As given by the above theorem, the defect is always non-negative. 

> <span style="background-color: #ffb812; color: black;">Property</span>. If $\sum_{\lambda} \Delta_{\lambda}$ is positive, i.e. if $\sum_{\lambda} m_{\lambda} < n$, then the eigenvectors of $A$ do not span its donamin $\mathbb{F}^n$. This is because the eigenspaces corresponding to $A$ have total dimension less than $n$.


> <span style="background-color: #03cafc; color: black;">Definition</span>. Define a **generalized eigenvector** $\mathbf{x}$ of a linear map (matrix) $A: \mathbb{F^n}\to\mathbb{F^n}$ as satisfying the equation
$$
(A-\lambda I)^k\mathbf{x=0},
$$
> where $\lambda$ is the corresponding eigenvalue and $k$ is a positive integer. Generalized eigenvectors are necessary when degenerate eigenvalues exist; i.e. the eigenvectors do not span $\mathbb{F}^n$. In such a case, the generalized eigenvectors do span $\mathbb{F}^n$ and the behavior of $A$ can be analyzed through them.

But even if no eigenvalue is defective - i.e. the dimensions of all the eigenspaces sum to $n$ - can we guarantee that the eigenvectors of $A$ span its domain? The following theorem ensures it is so:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Linear independence of eigenvectors**. Suppose the linear map $A$ has distinct eigenvectors $\mathbf{x_1, x_2, ..., x_r}$, corresponding to distinct eigenvalues $\lambda_1, \lambda_2, ..., \lambda_r$. Then the eigenvectors $\mathbf{x_1, ..., x_r}$ are linearly independent.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We proceed by contradiction: suppose that there exist scalars $c_1, ..., c_r \in \mathbb{F}$, not all of which are zero, such that
$$
c_1 \mathbf{x_1} + c_2 \mathbf{x_2} + ... + c_r\mathbf{x_r} = \mathbf{0}
$$
> i.e. that $\mathbf{x_1, ..., x_r}$ are not linearly independent. For some $K = 1, ..., r$, define
$$
D = (A-\lambda_{1} I) (A - \lambda_2 I) ... \overline{(A-\lambda_K I)}...(A-\lambda_r I)
$$
> where the bar denotes that the term is missing from the product; i.e. $D$ is the product of all $A-\lambda I$ except for $A-\lambda_K I$. Hence we can also write
$$
D = \prod_{i \neq K, i = 1, ..., r} (A-\lambda_i I)
$$
> Noting that $(A-\lambda_i I)\mathbf{x_i} = 0$ by definition. Applying $D$ to the above equation yields
$$
\begin{aligned}
D(c_1 \mathbf{x_1} + c_2 \mathbf{x_2} + ...  + c_K \mathbf{x_K} + ... +  c_r\mathbf{x_r}) &= \mathbf{0} \\

\end{aligned}
$$
>and thus
$$
\begin{aligned}
D(c_K \mathbf{x_K}) &= \mathbf{0} \\
\prod_{i \neq K, i = 1, ..., r} (A-\lambda_i I)(c_K \mathbf{x_K}) &= \mathbf{0} \\
\prod_{i \neq K, i = 1, ..., r} c_K (\lambda_K-\lambda_i)(\mathbf{x_K}) &= \mathbf{0}
\end{aligned}
$$
> as all the other terms yield zero, and $A\mathbf{x_K} = \lambda_K \mathbf{x_K}$. This equation is a single product of constants $\lambda_K - \lambda_i$, $c_K$, and the vector $\mathbf{x_K}$. As all the eigenvalues are distinct, $\lambda_K - \lambda_i \neq 0$; hence $c_K = 0$. However, this argument is valid for any $K$ and thus we have $c_K = 0$ for all $K = 1, 2, ..., r$. This contradicts our definition of linear dependence. $\square$

An alternative, and much shorter, proof is found below:

> <span style="background-color: #1eff12; color: black;">Proof</span>. As above, let $\mathbf{x_i}$ be the eigenvectors of $A$ and $\lambda_i$ be their corresponding eigenvalues for $i = 1, 2, ..., r$. Let
$$
c_1 \mathbf{x_1} + c_2 \mathbf{x_2} + ...  + c_K \mathbf{x_K} = \mathbf{0}
$$
> be the **shortest possible** sequence of $\mathbf{x_1, ..., x_K}$ that are linearly dependent. Multiplying both sides by
$$
(A-\lambda_1 I)(c_1 \mathbf{x_1} + c_2 \mathbf{x_2} + ...  + c_K \mathbf{x_K}) = \mathbf{0}
$$
> eliminates $\mathbf{x_1}$ from the equation and thus yields an even shorter sequence, which is a contradiction.

> <span style="background-color: #ffb812; color: black;">Remarks</span>. 
1. As all eigenvectors are linearly independent, if a $n\times n$ matrix has $n$ distinct eigenvectors, its eigenvectors span $\mathbb{F^n}$. 
2. A $n\times n$ matrix can have at most $n$ distinct eigenvectors, as its domain has dimension $n$.
3. If a $n\times n$ matrix does not have $n$ distinct eigen**values**, it is sometimes still possible to find $n$ distinct eigenvectors that span its domain.

