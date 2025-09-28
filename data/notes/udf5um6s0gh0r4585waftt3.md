## Matrix algebra

In addition *(ba-dum tss)* to the matrix addition, scalar multiplication, and multiplication operations defined previously, we define the following operations on matrices:

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Matrix transpose**. For any matrix $A = \{A_{ij}\}$, define its transpose $A^T$ as $\{A_{ji}\}$: $A$ with rows and columns swapped.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. **Properties of the matrix transpose**:
1. $(A^T)^T = A$.
2. Transposing a column vector yields a row vector.
3. $(AB)^T = B^T A^T$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 
$$
\begin{aligned}
(AB)^T_{ij} &= (AB)_{ji} \\
&= A_{jk} B_{ki} \\
&= B_{ki} A_{jk} \\
&= (B^T)_{ik} (A^{T})_{kj} \\
&= B^T A^T
\end{aligned}
$$

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Hermitian conjugate**. For any matrix $A = \{A_{ij}\}$, define its Hermitian conjugate $A^{\dagger}$ as $\{A_{ji}^*\}$: in other words, $A^{\dagger} = (A^T)^*$ - the conjugate of $A$ transpose.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The Hermitian conjugate obeys the above three properties of the matrix transpose.

## Matrix classifications
> <span style="background-color: #03cafc; color: black;">Definition</span>. **Symmetric matrices** $A$ are such that $A = A^T$: symmetry arises across the matrix's diagonal.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Anti-symmetric** or **skew-symmetric** matrices are such that $A = -A^T$. This necessitates that the diagonal elements of the matrix are zero, as any $A_{ii}$ lying on the diagonal remain unchanged by the transpose; as such, $A = -A^T$ implies $A_{ii} = -A_{ii} = 0$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Hermitian** matrices are such that $A = A^{\dagger}$. This implies that the diagonal elements of $A$ are all real, as real numbers are their own conjugate.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Skew-Hermitian** matrices are such that $A = -A^{\dagger}$. The diagonal elements of such a matrix must be purely imaginary.

## Matrix operations

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Trace**. The trace of a matrix $A$, denoted $Tr(A)$, is the sum of its diagonal elements $A_{ii}$. 

> <span style="background-color: #ffb812; color: black;">Proposition</span>. For two matrices $B$ and $C$ whose products are square matrices, $Tr(BC) = Tr(CB)$ even though $BC$ and $CB$ are not necessarily equal. This can be seen by simply expanding the diagonal terms of the product.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Identity matrix**. The $n \times n$ identity matrix $I_{n\times n}$ is the matrix which provides an analogy to $1$ for matrices: multiplication with $I$ does not change the original matrix, i.e. $AI = IA = A$ for any matrix $A$ (as long as the product is well-defined). We have
$$
I_{n\times n} = \begin{bmatrix}
1 & 0 & ... & 0 \\
0 & 1 & ... & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & ... & 1
\end{bmatrix} = \{\delta_{ij}\}
$$
> with all $1$s on the diagonal and all $0$s everywhere else.

## Matrix decompositions

> <span style="background-color: #ffb812; color: black;">Proposition</span>.
Every matrix can be written as the sum of a symmetric and an anti-symmetric matrix.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $A = \{A_{ij}\}$. Observe that for any $A_{ij}$, we have
$$
A_{ij} = \frac{A_{ij}+A_{ji}}{2} + \frac{A_{ij}-A_{ji}}{2}
$$
> Thus define the symmetric matrix $S^{+} = \{\frac{A_{ij}+A_{ji}}{2} \}$ and the antisymmetric matrix $S^{-} = \{\frac{A_{ij}-A_{ji}}{2}\}$, such that $A = S^+ + S^-$. Note that $S^+ = \frac{A+A^T}{2}$ and $S^- = \frac{A-A^T}{2}$.

Following from this, we also have:

> <span style="background-color: #ffb812; color: black;">Proposition</span>. Every square matrix can be written as a sum of a symmetric *trace-free* matrix (trace is zero), an antisymmetric matrix and an isotropic matrix.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Isotropic matrices** are scalar multiples of the identity matrix $I$... for now. ~~chuckles ominously~~

> <span style="background-color: #1eff12; color: black;">Proof</span>. Using the preceding decomposition, we have $A = S^+ + S^-$. The trace of $S^+$ is $\sum A_{ii}$, which is equal to the trace of $A$; let this trace be $n\sigma$, where $n$ is the dimension of $A$.<br/><br/>
In order to make $S^+$ trace-free, we need to subtract all elements on the diagonal of $S^+$ by $\sigma$; this results in the matrix $S^{+} - \sigma I = E$. Thus we have
$$
A = E + S^{-} + \sigma I
$$
> where the first matrix $E$ is symmetric and trace-less, the second is antisymmetric, and the third is isotropic.

This decomposition finds applications in various physical and mathematical scenarios; for instance, a point in a solid body deformed from point with position vector $\mathbf{x}$ to $A\mathbf{x}$ for some matrix $A$ will have the following:
1. *Average expansion/contraction* $\sigma$.
2. *Strain* $E$.
2. *Average rotation* $S^{-}\mathbf{x}$.

## Matrix inverses

> <span style="background-color: #03cafc; color: black;">Definition</span>. For a $m\times n$ matrix $A$, the $n\times m$ matrix $B$ deemed the **left inverse** of $A$ is such that
$$
BA = I
$$
> where $I$ is the $n\times n$ identity matrix; simultaneously, the $n\times m$ matrix $C$ deemed the **right inverse** of $A$ is such that
$$
AC = I
$$
> where $I$ is now the $m \times m$ identity matrix.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. For a square matrix of dimensions $n \times n$, the left and right inverses are identical. In fact, this is true for any matrix as long as both the left and right inverses exist.

> <span style="background-color: #1eff12; color: black;">Proof</span>. By the above, $BA=I \iff BAC = C \iff B(AC)=C$ by associativity. As $AC = I$ by definition, we have $B = C$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Invertible matrices** are square matrices whose inverse exists. 

Note that if an inverse of a square matrix, denoted $A^{-1}$ for the matrix $A$, does exist, then it is necessarily unique (as the right inverse equals the left inverse).

> <span style="background-color: #ffb812; color: black;">Properties</span>. 
1. $A = (A^{-1})^{-1}.$
2. $(AB)^{-1} = B^{-1} A^{-1}$. This can be demonstrated through associativity: $ABB^{-1}A^{-1}=A(B B^{-1})A^{-1}=AIA^{-1}=AA^{-1}=I$.

The inclusion of the inverse allows us to define two more categories of matrices:

## Orthogonal and unitary matrices

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Orthogonal matrices** $A$ are such that the inverse of $A$ is equal to its transpose: $A^{T} = A^{-1}$.

> <span style="background-color: #ffb812; color: black;">Property</span>. **The rows and columns of an orthogonal matrix form orthonormal sets**.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $A_{(i,*)}$ and $A_{(j,*)}$ denote the $i$th and $j$th row of the $n\times n$ orthonormal matrix $A$, respectively, where $i, j$ are integers from $1$ to $n$. Then the sum of the products of their terms equal 
$$
A_{(i,*)} (A_{(j,*)})^T = (AA^{T})_{ij} 
$$
> which is $1$ if $i = j$ and $0$ if $i \neq j$, as $AA^T = I$. Thus, the dot product between two rows of $A$ are $0$ if they are two different rows and $1$ if they are the same row, matching the definition of an orthonormal set. The proof for columns proceeds similarly.

> <span style="background-color: #ffb812; color: black;">Property</span>. If $A$ is an orthogonal matrix representing a linear map from an orthonormal basis $\{e_i\}$ to $\{Ae_i\}$, then the set $\{Ae_i\}$ is also orthonormal.

> <span style="background-color: #1eff12; color: black;">Proof</span>.
As previously observed, the columns of a matrix representing a linear map are $Ae_1, Ae_2, ..., Ae_n$. As the columns of an orthogonal matrix are orthonormal, the set $\{Ae_i\}$ must also be orthonormal.

Examples of orthonormal matrices include the rotation matrix and the reflection matrix, given in the last section (Examples of Linear Maps).

> <span style="background-color: #ffb812; color: black;">Property</span>. A transformation by a linear map represented by orthogonal matrix $A$ from two vectors $\mathbf{x, y}$ to $\mathbf{x', y' = Ax,\ Ay}$ preserve the real scalar product $\mathbf{x'\cdot y' = x\cdot y}$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. Using suffix notation, we write $\mathbf{x\cdot y} = x_i y_i$ and $\mathbf{x'}_i, \mathbf{y'}_i = A_{ij}x_j, A_{ij}y_j$. Thus we have $\mathbf{x'}\cdot \mathbf{y'} = A_{ij}x_j A_{ik}y_k$. Note that $A_{ij}A_{ik} = (AA^T)_{kj} = \delta_{kj}$ by $AA^T = I$. This leads to 
$$
\mathbf{x'\cdot y'} = \delta_{kj}x_jy_k = x_j y_j = x_i y_i = \mathbf{x\cdot y}
$$ 
> as the Delta symbol restricts us to $k = j$.

> <span style="background-color: #ffb812; color: black;">Property</span>. The same linear map preserves the distance between $\mathbf{x}$ and $\mathbf{y}$: $|\mathbf{x-y}|$. Such a property is termed an **isometry**.

> <span style="background-color: #1eff12; color: black;">Proof</span>. $|\mathbf{x'-y'}|^2=(\mathbf{x'-y')\cdot(x'-y'}) = \mathbf{(x-y)\cdot(x-y)}=|\mathbf{x-y}|^2$ by the above property.

As an added note, length-preserving transformations in $\mathbb{R}^3$ are either orthogonal matrices or outside the bounds of linear maps (e.g. translations).

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **unitary matrix** is the complex analogue to orthogonal matrices: if $A$ is unitary, then $U^{\dagger} = U^{-1}$. The above properties all hold for unitary matrices, except that they preserve the complex scalar product (with conjugates) instead of the real scalar product.

