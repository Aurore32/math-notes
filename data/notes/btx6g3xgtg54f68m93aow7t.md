> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Every complex square matrix $A$ satisfies its own characteristic equation: if $p_A(\lambda) =0$ denotes the characteristic equation of $A$, then $p_A(A) = 0$ also (replacing constants with constant multiples of the identity matrix).

> <span style="background-color: #1eff12; color: black;">Proof</span>. (Partial, only for diagonalizable and diagonal matrices)

**Case 1**: diagonal matrices of the form
$$
A = \begin{bmatrix}
\lambda_1 & 0 & ... & 0 \\
0 & \lambda_2 & ... & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & ... & \lambda_n
\end{bmatrix}.
$$
The characteristic equation of $A$ is given by $\det(A - \lambda I) = 0$, or equivalently, 
$$
(\lambda_1 - \lambda)(\lambda_2 - \lambda) ...(\lambda_n-\lambda) = 0
$$
by Laplace expansion. Plugging in $A$ into the equation and replacing $\lambda_i$ with $\lambda_i I$ gives
$$
\begin{aligned}
(\lambda_1 I - A)(\lambda_2 I-  A) ... (\lambda_n I - A)  = \mathbf{0}\\
\end{aligned}
$$
which is a product of $n$ diagonal matrices with the first diagonal term missing, the second term missing, etc., in that order. As multiplying diagonal matrices is equivalent to multiplying their terms, $(\lambda_1 I - A)(\lambda_2 I - A)$ has its first two diagonal terms missing; multiplying that onto $(\lambda_3 I - A)$ results in a matrix with its third diagonal term missing; and so on and so forth, until the resulting product is a matrix with all its diagonal terms missing, i.e. the zero matrix.

**Case 2**: diagonalizable matrices. We have
$$
P^{-1}AP = D
$$
for some diagonal matrix $D$ and transformation matrix $P$. As previously proven, similar matrices have the same characteristic equation; if $A$ is similar to $D$, then $D$ must satisfy the characteristic equation of $A$, $p_A$. Hence
$$
p_A(D) = p_A(P^{-1} A P) = 0
$$
Suppose that $p_A$ can be written as the polynomial $\sum_{i=0}^{n} c_i \lambda^i$. Then we have 
$$
\sum_{i=0}^n c_i (P^{-1}AP)^i = 0
$$
or, because of the following lemma:
> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Powers of diagonalizable matrices. $(P^{-1} A P)^{i} = P^{-1}APP^{-1}AP...P^{-1}AP = P^{-1}A^iP$; this is useful in taking higher powers, as exponentiating a diagonal matrix is fairly easy.

We thus have
$$
\begin{aligned}
\sum_{i=0}^n c_i P^{-1}A^iP &= 0 \\
P^{-1}\sum_{i=0}^n c_iA^i P &= 0 \\
P^{-1}(\sum_{i=0}^n c_iA^i)P &= 0 \\
\sum_{i=0}^n c_iA^i &= 0.
\end{aligned}
$$
Thus $A$ satisfies its own characteristic equation.

**Case 3**: $2\times 2$ matrices. As previously shown, all $2\times 2$ matrices can be written as one of three canonical forms; the first two canonical forms are diagonal and are addressed in Case 1, with the final canonical form
$$
B = \begin{bmatrix}
\lambda & 1 \\
0 & \lambda
\end{bmatrix}
$$
having characteristic equation $p_B(z) = (\lambda-z)^2$; $p_B(B) = 0$, as is computationally verifiable.

Suppose that $B = P^{-1} A P$ again for some transformation matrix $P$ and $2\times 2$ matrix $A$. Then $B$ and $A$ have the same characteristic equation due to similarity. We also have
$$
\begin{aligned}
p_B(B) = 0 &= p_A(P^{-1} A P) \\
 &= P^{-1}p_A(A)P
\end{aligned}
$$
owing to derivations in the previous case, and thus $p_A(A) = 0$.
