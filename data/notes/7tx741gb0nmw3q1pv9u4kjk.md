## Definitions and Basic Properties
Recall the transformation laws from the previous section. We define
> <span style="background-color: #03cafc; color: black;">Definition</span>. If $n\times n$ matrices $A$ and $B$ are identical under a change of basis, as detailed previously by
$$
A = P^{-1} B P
$$
> for some invertible $n\times n$ matrix $P$, then $A$ and $B$ are **similar** or **conjugate** matrices.

> <span style="background-color: #ffb812; color: black;">Property</span>. As $P^{-1} I P = I$, the only matrix the identity matrix is similar to is itself.

> <span style="background-color: #ffb812; color: black;">Property</span>. Similar matrices have the same determinant and trace.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 
Let $A' = P^{-1} A P$ for similar square matrices $A, A'$ and invertible square matrix $P$. Our goal is to prove that $\det A' = \det A$ and $Tr(A') = Tr(A)$. <br/><br/>
First: 
$$
\begin{aligned}
\det A' &= \det (P^{-1}A P) \\
 &= \det P^{-1} \det P \det A \\
 &= \det(P^{-1}P) \det A \\
 &= \det I \det A \\
 &= \det A
\end{aligned}
$$
> And also:
$$
\begin{aligned}
Tr(A') &= Tr(P^{-1}AP) \\
&= P^{-1}_{ik}A_{kj}P_{ji} \\
&= P_{ji}P^{-1}_{ik}A_{kj} \\
&= \delta_{jk}A_{kj} \\
&= A_{jj} \\
&= Tr(A).
\end{aligned}
$$
> Geometrically speaking, the determinant of similar matrices being the same can be intuited by the fact that they both represent the same linear map under different bases (and thus have the same volume scaling effect).

As a linear map has the same trace and determinant no matter what basis its matrix is expressed in, we can speak of a **unique trace and determinant** for that map.

> <span style="background-color: #ffb812; color: black;">Property</span>. If $u$ is an eigenvector of $A$, then $v = P^{-1} u$ is an eigenvector of $A'$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. Suppose that $Au = \lambda u$ for some scalar $\lambda$. Then if
$$
\begin{aligned}
A'(P^{-1} u) = \lambda(P^{-1} u)
\end{aligned}
$$
> we have
$$
\begin{aligned}
A'(P^{-1} u) &= \lambda(P^{-1} u) \\
P^{-1}A P^ (P^{-1} u) &= \lambda (P^{-1} u) \\
P^{-1} A u &= \lambda P^{-1} u \\
Au &= \lambda u
\end{aligned}
$$
> which proves the statement as every step is reversible.

> <span style="background-color: #ffb812; color: black;">Property</span>. Similar matrices have the same characteristic equation.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Suppose that $A$ and $B$ are similar: $B = P^{-1} A P$ for some transformation matrix $P$. We thus have
$$
\begin{aligned}
\det(B - \lambda I) &= \det(P^{-1} A P - \lambda I) \\
&= \det{P^{-1}}\det(AP - \lambda P) \\
&= \det{P^{-1}}\det(A-\lambda I) \det{P} \\
&= \det(PP^{-1}) \det(A-\lambda I) \\
&= \det(A-\lambda I)
\end{aligned}
$$
which is the characteristic equation of $A$.

## Diagonalization

> <span style="background-color: #03cafc; color: black;">Definition</span>. A matrix representing a linear map $A: \mathbb{F^n} \to \mathbb{F^n}$ is **diagonalizable** if its eigenvectors span $\mathbb{F^n}$.

This means that:
1. The matrix has $n$ linearly independent eigenvectors;
2. The matrix can be written in the form of a diagonal matrix under a change of basis (as the matrix representation of $A$ is diagonal if and only if the basis chosen are its eigenvectors)
3. The matrix is similar to such a diagonal matrix.

According to the above definition of similar matrices, we also have
$$
D = P^{-1}AP
$$
where $D$ is diagonal.

> <span style="background-color: #ffb812; color: black;">Remark</span>. If the $n\times n$ matrix $A$ has $n$ distinct eigenvalues, then it must be diagonalizable, as their eigenvectors are distinct and thus linearly independent; however, this is not a necessary condition (i.e. some matrices have repeated eigenvalues but are still diagonalizable).

The above scenario can occur if one eigenvalue corresponds to more than one linearly independent eigenvector: i.e. the system of equations
$$
(A-\lambda I)\mathbf{x} = 0
$$
has a solution space of $\dim 2$. In other words, there are no defective eigenvalues. This will be clarified with the lemma below:

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Suppose that a linear map $A: \mathbb{F^n} \to \mathbb{F^n}$ has eigenvalues $\lambda_1, \lambda_2, ..., \lambda_r$, and let $B_1, B_2, ..., B_r$ be the bases of the eigenspaces $E_{\lambda_1}, E_{\lambda_2}, ..., E_{\lambda_n}$ (in that order). Then the union of $B_1, ..., B_n$ form a linearly independent set.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Attempt a proof by contradiction. Denote the $j$th basis vector of $B_i$ as $v_{ij}$; if the set of all such $v_{ij}$s are linearly dependent, then there exist scalars $c_{11}, ..., c_{ij}$ such that
$$
\sum_{i=1}^{r} \sum_{j=1}^{m_{\lambda_i}} c_{ij}v_{ij} = 0.
$$
where $m_{\lambda_i}$ denotes the geometric multiplicity of $\lambda_i$. Utilizing the property that $Av_{ij} = \lambda_{i} v_{ij}$, we proceed similarly to the proof for linear independence of eigenvectors by applying the operator
$$
(A-\lambda_1 I) (A - \lambda_2 I) ... (A-\lambda_{K-1} I) (A - \lambda_{K+1} I) ... (A - \lambda_r I) 
$$
equalling
$$
\prod_{i=1,2,...,\bar{K},...,r} (A-\lambda_i I)
$$
to the above equation, which leads to
$$
\begin{aligned}
&\prod_{i=1,2,...,\bar{K},...,r}^{r} (A - \lambda_i I)\sum_{i=1}^{r} \sum_{j=1}^{m_{\lambda_i}} c_{ij}v_{ij} \\
&=\sum_{i=1}^{r} \sum_{j=1}^{m_{\lambda_i}} (\prod_{i=1,2,...,\bar{K},...,r}(\lambda_i - \lambda_k)) c_{ij}v_{ij} \\

\end{aligned}
$$
where the product is zero for every term except $i = K$, leading to the above sum equalling
$$
\sum_{j=1}^{m_{\lambda_K}} \prod_{i=1,2,...,\bar{K},...,r}(\lambda_K - \lambda_k) c_{Kj}v_{Kj}
$$
which is zero. This reaches a contradiction, as the vectors $v_{K1}, v_{K2}, ... v_{Km_{\lambda_{k}}}$ are a basis for $E_{\lambda_{K}}$ and are linearly independent by definition. $\square$

> <span style="background-color: #ffb812; color: black;">Remark</span>. A consequence of the above lemma concerns defective and non-defective eigenvalues. The lemma essentially states that the eigenspaces of any linear map are all linearly independent; as such, if no eigenvalue is defective - i.e. if the geometric multiplicities sum to $n$ - then $n$ linearly independent eigenvectors can be found, and the map is diagonalizable. If, however, defective eigenvalues do exist, the map is not diagonalizable.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Diagonalization matrix for linear maps**. The transformation matrix $P$ that maps the matrix $A$, in the standard orthonormal basis of $\mathbb{F}^n$, to the diagonalized basis of $n$ distinct eigenvectors of $A$, $\mathbf{x_1}, \mathbf{x_2}, ..., \mathbf{x_n}$ is 
$$
P = \begin{bmatrix}
\mathbf{x}_1 & \mathbf{x}_2 & ... & \mathbf{x}_n
\end{bmatrix}
$$
> where $D = P^{-1} A P$ results in the diagonalized matrix
$$
D = \begin{bmatrix}
\lambda_1 & 0 & ... & 0 \\
0 & \lambda_2 & ... & 0 \\
\vdots & \vdots & \ddots & \ddots \\
0 & 0 & ... & \lambda_n
\end{bmatrix}
$$
> where $\lambda_1, ..., \lambda_n$ correspond to the eigenvectors $\mathbf{x}_1, \mathbf{x}_2, ..., \mathbf{x}_n$.

This gives us a general process for determining whether a matrix is diagonalizable, as well as determining what that diagonalization is:

1. Find the characteristic equation of the matrix and determine its roots,
2. For each root $\lambda_i$, check the system of homogeneous linear equations
$$
(A-\lambda_i I)\mathbf{x} = \mathbf{0}
$$
and the dimension of its solution space (which is the dimension of the eigenspace).
3. Check if the dimension of the solution space (the geometric multiplicity) is equal to the algebraic multiplicity for every $\lambda_i$ - i.e. check if there are defective eigenvalues.
4. If there are no defective eigenvalues, find $n$ linearly independent eigenvectors from the above systems of equations and form $P$ as shown above.

