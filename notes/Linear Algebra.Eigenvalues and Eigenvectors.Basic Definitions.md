---
id: tklb5g2nntypp66xuohwavb
title: Basic Definitions and Results
desc: ''
updated: 1737081207832
created: 1736470671130
nav_order: 1
---

## Polynomials and algebra

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Fundamental theorem of algebra**. Let $p(z)$ be a polynomial of degree $n \geq 1$:
$$
p(z) = \sum_{i=0}^n a_i z^i
$$
> for $a_i \in \mathbb{C}$. Then the equation $p(z)=0$ has at least one solution in $\mathbb{C}$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. Trivial.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. $p(z)$ having at least one solution $\omega_n$ implies that it can be factored into the form
$$
p(z) = (z-\omega_n)q(z)
$$
> for some polynomial $q(z)$ of degree $n-1$. Recursion on this until we are left with a polynomial of degree 0 - a constant, which necessarily equals the leading coefficient $a_n$ - leads to the following factorization:
$$
p(z) = \prod_{i=1}^n a_n(z-\omega_i)
$$
> where $\omega_i$ is the $i$th root of $p(z)$. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **multiplicity** of a root $\omega_i$ of $p(z)$ is the highest power of the term $(z-\omega_i)$ in the above factorization of $p(z)$; alternatively, we may say that if $(z-\omega_i)^k$ is its highest power, then $\omega_i$ is a $k$-times repeated root of $p(z)$.

>  <span style="background-color: #ffb812; color: black;">Proposition</span>. According to the above, a polynomial with complex coefficients of degree $n$ has exactly $n$ complex roots, with multiplicity counted.

## Eigenvalues and Eigenvectors

> <span style="background-color: #03cafc; color: black;">Definition</span> (**Linear map definition for eigenvectors and eigenvalues**). For a linear map $A: \mathbb{F}^n \to \mathbb{F}^n$, where $\mathbb{F} = \mathbb{R}$ or $\mathbb{C}$, define an **eigenvector** of $A$ as a vector $\mathbf{x} \in \mathbb{F}^n$ such that
$$
A(\mathbf{x}) = \lambda \mathbf{x}
$$
> for some scalar $\lambda \in \mathbb{F}$. Also define the **eigenvalue** corresponding to $\mathbf{x}$ as $\lambda$. 

> <span style="background-color: #ffb812; color: black;">Remarks</span>. 
1. The geometrical interpretation of an eigenvector $\mathbf{x}$ of a linear map $A$ is such that $\mathbf{x}$ preserves its direction when transformed by $A$.
2. The subspace formed by all eigenvectors of $A$, denoted $l = \text{span} (\mathbf{x})$, is denoted the **invariant subspace** of $A$ (as it is invariant in direction under transformation by $A$)
3. For any polynomial $p(z) = \sum_{i=0}^n c_i z^i$, $p(A)\mathbf{x} = p(\lambda) \mathbf{x}$ by matrix algebra.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Matrix definition for eigenvectors and eigenvalues)**. For an $n\times n$ matrix $A$, define its eigenvector $\mathbf{x}$ and corresponding eigenvalue $\lambda$ as satisfying
$$
A\mathbf{x}=\lambda \mathbf{x}
$$
> or, equivalently,
$$
(A-\lambda I)\mathbf{x}=0
$$
> where $I$ denotes the $n\times n$ identity matrix. This forms a system of linear equations that either has unique solution $\mathbf{x} = \mathbf{0}$ if $(A-\lambda I)$ is invertible, or has other solutions if $(A-\lambda I)$ is not invertible. Thus, to find values of $\lambda$ that give us eigenvectors $\mathbf{x}$ outside of $\mathbf{x}=0$, we have
$$
\det (A-\lambda I) = 0
$$
> as the condition for $A-\lambda I$ being singular. Thus, we conclude that if $\mathbf{x}$ is a nonzero eigenvector of $A$, then its corresponding eigenvalue $\lambda$ must satisfy the above equation. 

> <span style="background-color: #ffb812; color: black;">Remark</span>. As previously considered in "Matrix Inverses and Linear Equations", we know that if $\det (A-\lambda I) = 0$, then the system of linear equations $(A-\lambda I)\mathbf{x} = 0$ has at least one solution.

> <span style="background-color: #03cafc; color: black;">Definition</span>. $\det (A-\lambda I) = 0$ is the **characteristic equation** of square matrix $A$. 

> <span style="background-color: #ffb812; color: black;">Properties</span>.
1. The characteristic equation of a $n\times n$ matrix $A$ is a polynomial in $\lambda$ of degree $n$; even if $A$ is a real matrix, its characteristic equation may still have complex roots
2. By the Fundamental Theorem of Algebra, the characteristic equation of $A$ has $n$ complex roots (counting repeated roots/multiplicities); thus, $A$ has $n$ eigenvalues and associated eigenvectors (which need not be distinct).

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Suppose $p(\lambda) = \sum_{i=0}^n c_i \lambda^i$ is the characteristic equation of $A$, with roots equalling the eigenvalues of $A$, $\lambda_1, \lambda_2, ..., \lambda_n$, not necessarily all distinct. Then:
1. $\det A = c_0 = \lambda_1 \lambda_2 ... \lambda_n$.
2. $c_{n-1} = (-1)^{n-1}Tr(A) = (-1)^{n-1}(\lambda_1 + \lambda_2 + ... + \lambda_n)$. This also implies that the trace of a matrix is the sum of its eigenvalues.
3. $c_n = (-1)^n$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. $A - \lambda I$, by definition, has determinant zero for all $\lambda_1, ..., \lambda_n$; using the Kronecker delta, we write
$$
A - \lambda I = \{A_{ij} - \lambda \delta_{ij}\}
$$
> and thus
$$
\det(A - \lambda I) = \sum \epsilon_{j_1, j_2, ..., j_n}(A_{j_1 1} - \lambda \delta_{j_1 1})(A_{j_2 2}-\lambda \delta_{j_2 2}) ... (A_{j_n n} - \lambda \delta_{j_n n})
$$
> across all possible permutations of $j_1, j_2, ..., j_n = 1, 2, ..., n$, not necessarily in that order. The terms $A_{j_i i} - \lambda \delta_{j_1 i}$ only contain $\lambda$ if $j_1 = i$, as only then will the $\delta$ term be nonzero. Thus, the only term that contains $n$ powers of $\lambda$, i.e. every term in the product has a $\lambda$, is
$$
\epsilon_{1,2,3,4,5,6,...,n}(A_{11}-\lambda)(A_{22}-\lambda)...(A_{nn}-\lambda)
$$
> which is simply
$$
(A_{11}-\lambda)(A_{22}-\lambda)...(A_{nn}-\lambda) = (-1)^{n}\lambda^n + ...
$$
> as the $\epsilon$ term is one. Thus, the leading coefficient of $p(\lambda)$ is one; with the knowledge that it has roots $\lambda_1, ..., \lambda_n$, we can factor it into
$$
p(\lambda) = (\lambda_1 - \lambda)(\lambda_2 - \lambda)...(\lambda_n - \lambda)
$$
> Note that the $\lambda^{n-1}$ term also originates from
$$
(A_{11}-\lambda)(A_{22}-\lambda)...(A_{nn}-\lambda)
$$
> as it is not possible for a term in the sum for the determinant to have $n-1$ occurrences of $\lambda$ (that would imply that only $1$ number from $j_1, j_2, ..., j_n$ is out of position compared to $1,2,...,n$, which is impossible). We have
$$
(A_{11}-\lambda)(A_{22}-\lambda)...(A_{nn}-\lambda)
= (-1)^n \lambda^n +(-1)^{n-1}(A_{11}+A_{22}+...+A_{nn})\lambda^{n-1}+...
$$
> and so the coefficient of $\lambda^{n-1}$ in $p(\lambda)$ is $(-1)^{n-1}(A_{11}+A_{22}+...+A_{nn})$, which is equal to $(-1)^{n-1}$ times the trace. If we compare this to
$$
p(\lambda) = (\lambda_1 - \lambda)(\lambda_2 - \lambda)...(\lambda_n - \lambda)
$$
> the we have $A_{11}+A_{22}+...+A_{nn} = \lambda_1 + \lambda_2 + ... + \lambda_n$: the sum of eigenvalues for $A$ is equivalent to its trace. Finally, in order to express $\det A$ using $p(\lambda)$, note that
$$
p(\lambda) = \det (A - \lambda I)
$$
> by definition, and so $p(0) = \det A = c_0 = \lambda_1\lambda_2...\lambda_n$.