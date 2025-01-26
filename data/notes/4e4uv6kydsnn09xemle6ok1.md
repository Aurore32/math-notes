Recall the following definitions and properties:

> <span style="background-color: #03cafc; color: black;">Definitions</span>. A Hermitian matrix $A$ is such that $A^{\dagger} = A$, where $A^{\dagger}$ denotes the complex conjugate of the transpose of $A$; the complex dot product is defined $\mathbf{u \cdot v}$, for two vectors $\mathbf{u, v}$, as being $\bar{u_i}v_i$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The eigenvalues of a Hermitian matrix are real.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $A$ be a Hermitian matrix. For eigenvalues $\mathbf{x}$ and corresponding eigenvalues $\lambda$ of $A$, we have
$$
A\mathbf{x} = \lambda\mathbf{x}
$$
And thus
$$
\mathbf{x^{\dagger}}A\mathbf{x} = \lambda\mathbf{x^{\dagger}x}
$$
Taking the Hermitian conjugate of both sides gives
$$
\mathbf{x^{\dagger}}A^{\dagger}\mathbf{x} = \mathbf{x^{\dagger}}A\mathbf{x} =\lambda^{\dagger}\mathbf{x^{\dagger}x} = \lambda^* \mathbf{x^{\dagger}x}
$$
as $A^{\dagger} = A$ by definition, and the Hermitian conjugate of a scalar $\lambda$ is just its conjugate. It thus follows that
$$
\lambda^* \mathbf{x^{\dagger}x}= \lambda \mathbf{x^{\dagger}x},
$$
and that
$$
(\lambda^* - \lambda)\mathbf{x^{\dagger}x} = 0,
$$
and as $\mathbf{x^\dagger x} \neq 0$ unless $\mathbf{x}$ is the zero vector (impossible if $\det(A-\lambda I) = 0$, by definition), we have
$$
\lambda^* = \lambda
$$
and thus $\lambda$ is real.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. As real symmetric matrices are also Hermitian, the eigenvalues of real symmetric matrices are real.

> <span style="background-color: #1eff12; color: black;">Proof</span> (Adjoint maps).

Proceed with the following definitions:

> <span style="background-color: #03cafc; color: black;">Definition</span>. For an inner product $\langle\mathbf{u,v}\rangle$, define the **adjoint** $A^*$ to a linear map $A$ as such that $\langle A\mathbf{u,v}\rangle = \langle \mathbf{u}, A^*\mathbf{v} \rangle$. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Self-adjoint** maps $A$ are such that $A$ is its own adjoint over some inner product (e.g. the dot product).


Hermitian matrices are **self-adjoint maps** over the complex dot product; that is, they satisfy 
$$
\mathbf{u} \cdot (A\mathbf{v}) = (A\mathbf{u}) \cdot \mathbf{v}
$$
where $\cdot$ denotes the **complex dot product** (in contrast, real symmetric matrices are self-adjoint over the real dot product).

> <span style="background-color: #1eff12; color: black;">Proof</span> that Hermitian matrices are self-adjoint. The complex dot product between $A\mathbf{u}$ and $\mathbf{v}$ can also be expressed in matrix form as

$$
(A\mathbf{u})^{\dagger} \mathbf{v}.
$$
> Taking the Hermitian transpose of this gives
$$
 \mathbf{v}^{\dagger} (A\mathbf{u})
$$
which, as $A^{\dagger} = A$, equals
$$
\mathbf{v}^{\dagger} A^{\dagger} \mathbf{u} = (A\mathbf{v})^{\dagger} \mathbf{u}
$$
which is $(A\mathbf{v}) \cdot \mathbf{u}$. The proof that symmetric matrices are self-adjoint follows similarly.

We can utilize the properties of self-adjoint matrices particularly well here. Let $\mathbf{x}$ be an eigenvector of $A$ and consider the norm
$$
\lambda(\mathbf{x}\cdot \mathbf{x}).
$$
By $A\mathbf{x} = \lambda \mathbf{x}$, we have
$$
\begin{aligned}
&\lambda(\mathbf{x}\cdot \mathbf{x}) \\
&= (\lambda \mathbf{x}\cdot \mathbf{x}) \\
&= (A\mathbf{x} \cdot \mathbf{x}) \\
&= (\mathbf{x} \cdot A\mathbf{x}) \\
&= (\mathbf{x} \cdot \lambda \mathbf{x}) \\
&= \lambda^* (\mathbf{x}\cdot \mathbf{x}) 
\end{aligned}
$$
by the properties of the complex dot product (non-commutative because of a conjugate). As $(\mathbf{x}\cdot \mathbf{x}) > 0$ ($\mathbf{x} \neq 0$), we have $\lambda = \lambda^*$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. A $n\times n$ Hermitian matrix $A$ has $n$ orthogonal eigenvectors.

To prove this, we need to introduce a powerful tool:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Gram-Schmidt Process**.

The Gram-Schmidt process yields an orthogonal set of $r$ vectors $\tilde{B} = \{\mathbf{v_1,v_2,...,v_r}\}$ from $r$ linearly independent vectors $B = \{\mathbf{w_1,w_2,...,w_r}\}$.

First define the **projection operator** $P_{\mathbf{v}}(\mathbf{w})$ as an orthogonal projection of the vector $\mathbf{w}$ onto the direction of $\mathbf{v}$:
$$
P_{\mathbf{v}}(\mathbf{w}) = \frac{\mathbf{v\cdot w}}{\mathbf{v \cdot v}}\mathbf{v}.
$$
This projection works by first constructing a vector that is a scalar multiple of $\mathbf{v}$: $P_{\mathbf{v}}(\mathbf{w}) = \lambda\mathbf{v}$ for some $\mathbf{v}$. As $P_{\mathbf{v}}(\mathbf{w})$ is a projection of $\mathbf{w}$ onto $\mathbf{v}$, it has magnitude equal to $|\mathbf{w}|\cos \theta$ where $\theta$ is the angle between the two vectors. Thus we have
$$
\begin{aligned}
|\lambda\mathbf{v}| &= |\mathbf{w}|\cos \theta \\
\lambda^2 (\mathbf{v}\cdot \mathbf{v}) &= (\mathbf{w}\cdot\mathbf{w})\cos^2 \theta \\
\lambda^2 &= \frac{(\mathbf{w}\cdot\mathbf{w})}{(\mathbf{v}\cdot \mathbf{v})}\cos^2 \theta \\

\end{aligned}
$$
as $\cos^2 \theta = \frac{(\mathbf{w \cdot v})^2}{(\mathbf{w\cdot w})(\mathbf{v\cdot v})}$ by the properties of the dot product, we have
$$
\lambda = \frac{\mathbf{v\cdot w}}{\mathbf{v \cdot v}}.
$$
Also observe that $\mathbf{w} - P_\mathbf{v}(\mathbf{w})$ is the normal vector from $\mathbf{w}$ to $\mathbf{v}$, and is thus orthogonal to $\mathbf{v}$. This gives us a clue on how to begin our Gram-Schmidt orthogonalization process for $B = \{\mathbf{w_1,w_2,...,w_n}\}$ to orthogonal vectors $\tilde{B} = \{\mathbf{v_1,v_2,...,v_n\}}$:
1. Let $\mathbf{v}_1 = \mathbf{w_1}$.
2. We want $\mathbf{v_2}$ to be orthogonal to $\mathbf{v}_1$. Therefore, let $\mathbf{v}_2$ be the perpendicular from $\mathbf{w}_2$ onto $\mathbf{v_1}$: $\mathbf{v_2} = \mathbf{w_2} - P_{\mathbf{v_1}}(\mathbf{w_2})$.
3. We want $\mathbf{v_3}$ to be orthogonal to both $\mathbf{v}_1$ and $\mathbf{v}_2$. Thus let $\mathbf{v}_3$ be the perpendicular from $\mathbf{w}_3$ to both $\mathbf{v_1}$ and $\mathbf{v}_2$: $\mathbf{v}_3 = \mathbf{w}_3 - P_{\mathbf{v_1}}(\mathbf{w}_3) - P_{\mathbf{v_2}}(\mathbf{w}_3)$.
4. $\vdots$
5. We want $\mathbf{v_n}$ to be orthogonal to $\mathbf{v_1}, \mathbf{v_2}, ..., \mathbf{v_{n-1}}$, so let $\mathbf{v_n}$ to be the perpendicular of $\mathbf{w}_n$ to all of the above vectors: $\mathbf{v}_n = \mathbf{w}_n - \sum_{i=1}^{n-1}P_{\mathbf{v}_{i}}(\mathbf{w}_n)$. 

In each step, we construct $\mathbf{v}_i$ from the difference between $\mathbf{w}_i$ and its orthogonal projection to the vector space formed by $\mathbf{v}_1, \mathbf{v}_2, ..., \mathbf{v}_{i-1}$, thus yielding an orthogonal vector to all the previous $\mathbf{v}$s. 
 
> <span style="background-color: #1eff12; color: black;">Proof</span> that the Gram-Schmidt process yields a list of orthogonal vectors.

Proceed by induction. First, the base case: $\mathbf{v}_1$ and $\mathbf{v}_2$ are orthogonal by definition of the projection operator ($\mathbf{v}_2$ is perpendicular to a projection onto $\mathbf{v}_1$.) If we can prove that any consecutive sequence of vectors in $\tilde{B}$ are orthogona, then we can prove that they are mutually orthogonal.

Suppose that $\mathbf{v}_1, \mathbf{v}_2, ..., \mathbf{v}_{k}$ are an orthogonal list of vectors; that is, suppose that 
$$
\mathbf{v}_i \cdot \mathbf{v}_j = 0
$$
for all $i, j = 1, 2, ..., k$ and $i \neq j$. We want to prove that $\mathbf{v}_{k+1}$ is orthogonal to this list. Consider, for any $j = 1, 2, ..., k$,
$$
\begin{aligned}
 \mathbf{v}_j \cdot \mathbf{v}_{k+1} \\
= \mathbf{v}_{j} \cdot (\mathbf{w}_{k+1} - \sum_{i=1}^{k}P_{\mathbf{v}_i} (\mathbf{w}_{k+1})) \\
= \mathbf{v}_{j} \cdot (\mathbf{w}_{k+1} - \sum_{i=1}^{k}\frac{\mathbf{v_i \cdot w_{k+1}}}{\mathbf{v_i \cdot v_i}} \mathbf{v}_i) \\
= \mathbf{v}_{j} \cdot \mathbf{w}_{k+1} - \sum_{i=1}^{k}\frac{\mathbf{v_i \cdot w_{k+1}}}{\mathbf{v_i \cdot v_i}} \mathbf{v}_{j} \cdot\mathbf{v}_i
\end{aligned}
$$
where, as $\mathbf{v}_i \cdot \mathbf{v}_j = 0$ for all $i \neq j$, the sum has its only nonzero term as $i = j$:
$$
= \mathbf{v}_{j} \cdot \mathbf{w}_{k+1} - \frac{\mathbf{v_j \cdot w_{k+1}}}{\mathbf{v_j \cdot v_j}} \mathbf{v}_{j} \cdot\mathbf{v}_j 
$$
which is zero. Thus, by the principle of mathematical induction, $\mathbf{v}_{k+1}$ is orthogonal to the list $\mathbf{v_1, v_2, ..., v_k}$. $\square$

The extra wao sugoi thing about the Gram-Schmidt process is that it doesn't just give us a list of orthogonal vectors; it gives us a list of basis vectors of $\mathbf{F}^n$, from any list of $n$ vectors in $\mathbf{F}^n$. This is owing to

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Any set of nonzero orthogonal vectors is also linearly independent (and thus a basis). 

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Suppose for the sake of contradiction that $\{\mathbf{v_1, v_2, ..., v_n}\}$ is a list of orthogonal vectors (all of which are nonzero), and that there exist scalars $a_1, ..., a_n$, not all zero, such that
$$
\sum_{i=1}^n a_i \mathbf{v_i} = 0
$$
violating linear independence. Taking the dot product with $\mathbf{v_K}$ for some $K = 1, 2, ..., n$ yields
$$
\sum_{i=1}^n a_i (\mathbf{v_i} \cdot \mathbf{v_K}) = 0
$$
but as the dot product of any $\mathbf{v_i, v_K}$, $i \neq K$, is zero by definition of an orthogonal set of vectors, the above sum is only nonzero when $i = K$. Thus, it is equivalent to the single term
$$
a_K (\mathbf{v_K \cdot v_K}) = 0
$$
$\mathbf{v}_K$ is nonzero and thus has nonzero norm; thus, $a_K = 0$. However, the above process can be conducted with any $K = 1, 2, ..., n$, leading to the conclusion that 
$$
a_i = 0
$$
for all $i = 1, 2, ..., n$. This forms a contradiction.

> <span style="background-color: #ffb812; color: black;">Remark</span>.
1. A set of $n$ mutually orthogonal vectors form a basis in $\mathbb{F}^n$.
2. Each $\mathbf{v}_n$ is a linear combination of the $\mathbf{w}_n$.
3. If $\mathbf{w_1, w_2, ..., w_n}$ is a list of linearly dependent vectors, the Gram-Schmidt process will not be able to generate a full list of $n$ orthogonal vectors; if $\mathbf{w}_k$ is the first linearly dependent vector in $\mathbf{w}$, then $\mathbf{v}_k = 0$.  This is because $\mathbf{v}_k$ is a linear combination of $\mathbf{w}_1, ..., \mathbf{w}_k$.
4. If a set of linearly independent eigenvectors $B = \{\mathbf{w_1,...,w_r}\}$ yields an orthogonal set of vectors $\tilde{B} = \{\mathbf{v_1, ..., v_r}\}$ by Gram-Schmidt, then $\tilde{B}$ also constitutes a set of eigenvectors because $\tilde{B}$ is a linear combination of $B$. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. An **orthonormal** set, as previously defined is an orthogonal set of vectors $\{\mathbf{u_1, u_2, ..., u_n}\}$ such that
$$
\mathbf{u_i} \cdot \mathbf{u_j} = \delta_{ij},
$$
> i.e. the vectors are mutually orthogonal (have dot product zero) and each of norm 1. An orthogonal set can be converted to an orthonormal set simply by normalizing each vector to norm 1.

> <span style="background-color: #ffb812; color: black;">Remark</span>. If $B$ is an orthogonal set that forms a set of eigenvectors, then the orthonormal set $\tilde{B}$ constructed from $B$ is also a set of eigenvectors (owing to eigenspaces being subspaces). 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Transformation matrices between two orthonormal bases are unitary.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Suppose that the two bases $u = \{\mathbf{u_1, ..., u_n}\}$ and $v = \{\mathbf{v_1, ..., v_n\}}$ are orthonormal; we have $\mathbf{u_i \cdot u_j = v_i \cdot v_j} = \delta_{ij}$. The transformation matrix mapping $u$ to $v$ can be denoted
$$
U = \begin{bmatrix}
U_{11} & U_{12} & ... & U_{1n} \\
U_{21} & U_{22} & ... & U_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
U_{n1} & U_{n2} & ... & U_{nn}
\end{bmatrix}
$$
where
$$
\mathbf{v}_j = \sum_{i=1}^n U_{ij} \mathbf{u}_i
$$
with its columns expressing the basis $v$ in terms of the vectors of $u$. We want to prove that this matrix is unitary, i.e. that 
$$
U^{\dagger} U = I
$$
or, in scalar form, that
$$
U^{\dagger}_{ik} U_{kj} = U^*_{ki} U_{kj} = \delta_{ij}
$$
As $\mathbf{v}_j \cdot \mathbf{v}_k = 0$ for $i \neq j$, we have
$$
\begin{aligned}
(\sum_{i=1}^n U_{ij} \mathbf{u}_i) \cdot (\sum_{r=1}^n U_{rk} \mathbf{u}_i) = 0
\end{aligned}
$$
where the only term in the sum that is nonzero is when $i=r$, i.e.
$$
\sum_{i=1}^n U_{ij}^* U_{ik}(\mathbf{u_i} \cdot \mathbf{u_i}) = 0.
$$
(The complex conjugate arises due to the dot product being the complex scalar product). As $\mathbf{u}_i \cdot \mathbf{u}_i = 1$ by orthonormality, we have
$$
\sum_{i=1}^n U_{ij}^* U_{ik} = 0
$$
for $j \neq k$.

As $\mathbf{v}_j \cdot \mathbf{v}_j = 1$, we have
$$
\begin{aligned}
(\sum_{i=1}^n U_{ij} \mathbf{u}_i) \cdot (\sum_{r=1}^n U_{rj} \mathbf{u}_i) = 1
\end{aligned}
$$
or that
$$
\sum_{i=1}^n U_{ij}^* U_{ij} = 1
$$
As such we conclude from the above that
$$
U_{ij}^* U_{ik} = \delta_{jk}
$$
using suffix notation, or $U^*_{ki} U_{kj} = \delta_{ij}$. Thus $U$ is unitary. $\square$

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. A $n\times n$ Hermitian matrix $H$ has $n$ orthogonal, and thus linearly independent, eigenvectors.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

> We present the following alternatives:

> 1. **Proof by condescension.** The statement is trivial and thus does not require a proof.
 2. **Proof a la Pierre de Fermat**. I have devised a truly marvelous proof of this theorem, but it is too large to fit inside my computer's hard drive.
3. **Proof by appeal to authority**. My textbook says so, so it must be true.
4. **Proof by slippery slope**. If Hermitian matrices don't have $n$ orthogonal eigenvectors, then soon enough symmetric matrices aren't going to have orthogonal eigenvectors too and the universe will die a slow, painful, tortured heat death.
5. **Proof by emotional appeal**. 

(I'm going to get out of here and never come back)

Suppose that $\lambda_i$ and $\lambda_j$ are two eigenvalues of $H$, not necessarily distinct, corresponding to eigenvectors $v_i$ and $v_j$ respectively. Our goal is to prove that $v_i$ and $v_j$ are orthogonal, i.e. $v_i \cdot v_j = 0$; in matrix form, this can be expressed as $v_i^{\dagger} v_j = 0$ (using the complex scalar product).

**Case 1**: $\lambda_i  \neq \lambda_j$. In any case, we have $Hv_i = \lambda v_i$ and $H v_j = \lambda v_j$. 

Now consider the (complex) dot product between $v_i$ and $v_j$, $v_i^{\dagger} v_j$. If $Hv_j = \lambda_j v_j$, then we have
$$
v_i^{\dagger}Hv_j = v_i^{\dagger} \lambda_j v_j
$$
where taking the Hermitian transpose of both sides gives
$$
v_j^{\dagger} H^{\dagger} v_i = v_j^{\dagger}\lambda_j^* v_i
$$
where $H^{\dagger} = H$, so
$$
v_j^{\dagger} H v_i = v_j^{\dagger} \lambda_i v_i = v_j^{\dagger}\lambda_j^* v_i
$$
as $Hv_i = \lambda_i v_i$. Thus $(\lambda_i^* - \lambda_j) (v_j^{\dagger} v_i) = 0$. However, as proven above, the eigenvalues of $H$ are real, so $\lambda_i^* = \lambda_i \neq \lambda_j$, and so $v_j^\dagger v_i = 0$. (This can also be proven using self-adjoint maps).

**Case 2:** $\lambda_i = \lambda_j$ (repeated eigenvalue). Suppose that $H$ has distinct eigenvalues $\lambda_1, \lambda_2, ..., \lambda_r$, with the other $n-r$ eigenvalues being repeated. By Case 1 (distinct eigenvalues correspond to orthogonal/orthonormal eigenvectors), the corresponding eigenvectors $\{\mathbf{v_1,v_2,...,v_r}\}$ form an orthonormal set. Let

$$
v = \{\mathbf{v_1,v_2,...,v_r,u_{1},u_{2},...,u_{n-r}\}}
$$
be an orthonormal basis for $\mathbb{F}^n$; by Gram-Schmidt, such an orthonormal basis can always be found containing $\mathbf{v_1,...,v_r}$ (which are orthonormal, and thus not affected by Gram-Schmidt) by selecting any basis containg $\mathbf{v_1,v_2,...,v_r}$ and applying the process. Thus let $P$ represent the transformation matrix from the original basis of $H$ to the orthonormal basis $v$, i.e.
$$
P = \begin{bmatrix}
\mathbf{v_1} & \mathbf{v_2} & ... & \mathbf{v_r} & \mathbf{u_1} & \mathbf{u_2} & ... & \mathbf{u_{n-r}}
\end{bmatrix}
$$
By the above theorem, $P$ is unitary with $P^{\dagger} = P^{-1}$. As such, $H$ with basis changed to $v$ is
$$
P^{-1} H P = P^{\dagger} H P = (P^{\dagger} H P )^{\dagger}
$$
as $H^{\dagger} = H$, and so $H$ is again symmetric under basis transformation to $v$:
$$
P^{-1}HP = \tilde{H} = \begin{bmatrix}
\Lambda & \mathbf{0} \\
\mathbf{0} & C
\end{bmatrix}
$$
where $\mathbf{0}$ represents the zero matrix (of appropriate size), $\Lambda$ is the diagonal matrix of distinct eigenvalues $\lambda_1, \lambda_2, ..., \lambda_n$ (as the first $r$ basis vectors $\mathbf{v_1,v_2,...,v_r}$ are eigenvectors)
$$
\Lambda = \begin{bmatrix}
\lambda_1 & 0 & ... & 0 \\
0 & \lambda_2 & ... & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & ... & \lambda_r
\end{bmatrix}
$$
And $C$ is a $(n-r)\times (n-r)$ symmetric matrix
$$
C = \begin{bmatrix}
c_{11} & ... & c_{1(n-r)} \\
\vdots & \ddots & \vdots \\
c_{(n-r)1} & ... & c_{(n-r)(n-r)}
\end{bmatrix}
$$
which is symmetric because $P^{-1}HP$ is symmetric as shown above. The eigenvalues of $C$ are also eigenvalues of $H$: $\tilde{H}$ and $H$ share a characteristic equation because they are similar, so
$$
\det(H-\lambda I) = \det(\tilde{H} - \lambda I) = (\lambda_1 - \lambda)(\lambda_2 - \lambda)...(\lambda_r - \lambda)\det (C-\lambda I)
$$
where $\det(C-\lambda I)$ represents the eigenvalues of $C$. As $\lambda_1, \lambda_2, ..., \lambda_r$ are the distinct eigenvalues of $H$, it follows that $\det(C-\lambda I)$ solves for the repeated eigenvalues. 

First, assume that $C$ does not have repeated eigenvalues. $C$ contains the repeat eigenvalues of $H$, but we assume for the sake of simplicity that these eigenvalues do not repeat more than once (i.e. algebraic multiplicity $\leq 2$); if they do, repeat the above steps until we obtain a new $C$ in the bottom-right corner with no repeated eigenvalues.

As $H$ is Hermitian, $C$ is also Hermitian, and so by Case 1 we know that $C$ has $(n-r)$ orthogonal eigenvectors, all distinct; let them be labeled $\mathbf{V_1, V_2, ..., V_{n-r}}$. Now carry out a further change of basis for $H$ through the transformation matrix
$$
Q = 
\begin{bmatrix}
I_{r\times r} & \mathbf{0}\\
\mathbf{0} & \mathbf{V}
\end{bmatrix}
$$
where $I_{r\times r}$ is the $r\times r$ identity matrix and $\mathbf{V}$ is the matrix of eigenvectors of $C$, in order. The transformation
$$
\hat{H} = Q^{-1}\tilde{H}Q = Q^{-1}(P^{-1}HP)Q
$$
thus leaves the first $r$ columns the same, but diagonalizes the last $(n-r)$ columns:
$$
\hat{H} = \begin{bmatrix}
\lambda_1 & 0 & ... & 0 \\
0 & \lambda_2 & ... & 0 \\
\vdots & \vdots & \ddots & 0 \\
0 & 0 & ... & \lambda_n
\end{bmatrix}
$$
We conclude that $H$ is diagonalizable through a series of transformations $P$ and $Q$, and therefore that $H$ has $n$ linearly independent eigenvectors, represented by the matrix
$$
V = PQ.
$$

> <span style="background-color: #12ffd7; color: black;">Corollary</span>.
1. The eigenvectors of Hermitian matrices can always form an orthonormal basis for $\mathbb{C}^n$.
2. Hermitian matrices are always diagonalizable; in particular, they are diagonalizable by unitary matrices, as the transformation matrix from the standard orthonormal basis to the basis of eigenvectors (orthonormal) is unitary by an above theorem.
3. All of the above also applies to (real) symmetric matrices: they have orthogonal eigenvectors, have real eigenvalues, and are diagonalizable by orthogonal matrices instead of unitary matrices.

> <span style="background-color: #03cafc; color: black;">Definition</span>. $A$ is a **normal matrix** if $AA^{\dagger} = A^{\dagger}A$. It is possible to show that normal matrices are always diagonalizable.