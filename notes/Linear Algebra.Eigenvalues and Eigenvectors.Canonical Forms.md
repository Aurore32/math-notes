---
id: 0v6omcg3j6htia1jtgc613m
title: Canonical Forms
desc: ''
updated: 1737448288860
created: 1737434907603
nav_order: 5
---
> <span style="background-color: #03cafc; color: black;">Definition</span>. A **canonical form** for a $2\times 2$ matrix includes the following:
1. an enlargement along the axes $\begin{bmatrix}
\lambda_1 & 0 \\
0 & \lambda_2
\end{bmatrix}$,
2. a shear $\begin{bmatrix}
\lambda & 1 \\
0 & \lambda
\end{bmatrix}$, and
3. scalar multiples of the identity matrix $\begin{bmatrix}
\lambda & 0 \\
0 & \lambda
\end{bmatrix}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. All $2\times 2$ matrices are similar to one of the above canonical forms.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Which canonical form the matrix is similar to depends on its eigenvalues: whether it has two identical eigenvalues, or two distinct eigenvalues. Let $A$ be the $2\times 2$ matrix in question, and let $\lambda_1, \lambda_2$ be its two eigenvalues; we thus have either $\lambda_1 = \lambda_2$, or $\lambda_1 \neq \lambda_2$ (note that two eigenvalues, not necessarily real are guaranteed to exist by the Fundamental Theorem of Algebra).

**Case 1**. $\lambda_1 \neq \lambda_2$. As different eigenvalues correspond to different eigenvectors, and different eigenvectors are linearly independent, $A$ must be diagonalizable as its eigenvectors span $\mathbb{F}^2$. As such, it is similar to $\begin{bmatrix}
\lambda_1 & 0 \\
0 & \lambda_2
\end{bmatrix}$.

**Case 2**. $\lambda_1 = \lambda_2 = \lambda$. The matrix is either (i) diagonalizable if the eigenvalue is not defective, or (ii) not diagonalizable. If the matrix is diagonalizable, then from our study of diagonalization, it is similar to $\begin{bmatrix}
\lambda & 0 \\
0 & \lambda
\end{bmatrix}$ and we are done. However, if the matrix is not diagonalizable, $\lambda$ must be defective, indicating that
$$
(A-\lambda I)\mathbf{x} = 0
$$
has a solution space of dimension 1. (It cannot have dimension 0 because $A\mathbf{x} = \lambda\mathbf{x}$ by definition for another $\mathbf{x}$ besides the zero vector; this is guaranteed by $\det(A - \lambda I) = 0$). Let the vector $\mathbf{v}$ span the eigenspace $E_{\lambda}$ and construct $(\mathbf{v,w})$ spanning $\mathbb{F}^2$ by selecting $\mathbf{w}$ as linearly independent to $\mathbf{v}$. Suppose that
$$
A\mathbf{w} = \alpha \mathbf{v} + \beta \mathbf{w}
$$
for some $\alpha, \beta \in \mathbb{F}$  - i.e. that $A$ maps $\mathbf{w}$ to $(\alpha, \beta)$ in the basis $(\mathbf{v,w})$. As such, as the matrix representation of $A$ has columns $A\mathbf{v}, A\mathbf{w}$, we know that $A$ can be transformed into
$$
A = \begin{bmatrix}
A\mathbf{v} & A\mathbf{w}
\end{bmatrix} 
= \begin{bmatrix}
\lambda & \alpha \\
0 & \beta
\end{bmatrix} 
$$
by a change of basis. Let this transformed matrix be denoted $\tilde{A}$. As $\tilde{A}$ and $A$ represent the same linear map, they have the same eigenvalues (but not necessarily the same eigenvectors); thus $\tilde{A}$ also has a repeat eigenvalue $\lambda$. This means that $\beta = \lambda$ (as can be seen from the characteristic equation). We further observe that
$$
(\tilde{A}-\lambda I)^2 = \begin{bmatrix}
0 & \alpha \\
0 & 0
\end{bmatrix}^2 = 
\begin{bmatrix}
0 & 0 \\
0 & 0
\end{bmatrix}.
$$
Define $\mathbf{u} = (\tilde{A}-\lambda I) \mathbf{w}$, where $\mathbf{u} \neq 0$ because $\mathbf{w}$ is not an eigenvector of $\tilde{A}$ (it is linearly independent to the eigenvector). As such, we have $(\tilde{A}-\lambda I) \mathbf{u} = \mathbf{0}$ per the above, and thus $\mathbf{u}$ is an eigenvector of $\tilde{A}$. We also have
$$
\tilde{A} \mathbf{w} = \mathbf{u} + \lambda \mathbf{w},
$$
as well as
$$
\tilde{A}\mathbf{u} = \lambda \mathbf{u}
$$
by $\mathbf{u}$ being an eigenvector, and thus we conclude that the matrix $\hat{A}$ where
$$
\hat{A} = \begin{bmatrix}
\tilde{A}\mathbf{u} & \tilde{A}\mathbf{w}
\end{bmatrix} =
\begin{bmatrix}
\lambda & 1 \\
0 & \lambda
\end{bmatrix}
$$
is similar to $\tilde{A}$, and thus similar to $A$. $\square$


> <span style="background-color: #ffb812; color: black;">Remark</span>. The matrices $\begin{bmatrix}
\lambda_1 & 0 \\
0 & \lambda_2
\end{bmatrix}$ and $\begin{bmatrix}
\lambda_2 & 0 \\
0 & \lambda_1
\end{bmatrix}$ are similar by means of the transformation matrix $\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}$.

> <span style="background-color: #ffb812; color: black;">Remark</span>. It is possible to derive simiar canonical forms, or **Jordan normal forms**, for any complex $n\times n$ matrix; specifically, all square matrices $A$ are similar to a canonical form $\tilde{A}$ satisfying
$$
\tilde{A}_{ii} = \lambda_i,\ \tilde{A}_{i(i+1)} \in \{1, 0\}, \text{ 0 otherwise}
$$
> i.e. the elements on the diagonal are the eigenvalues, the elements on the superdiagonal (one above the diagonal) are one or zero, and all other elements are zero.

