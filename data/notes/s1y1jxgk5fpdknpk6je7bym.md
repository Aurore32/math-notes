Apparently there's a fun little pattern with how these Cum Breech Tripod courses are designed: they give you the world's most microscopic glimpse of the next course you'll be studying, but like Vince Gilligan, they end it right before the good part to pad viewer engagement. Cowards (Unvravo Bince).

## Defining groups
> ~~<span style="background-color: #03cafc; color: black;">Definition</span>. I'm done with this shit, yo. Just go take **Group Theory** or something.~~

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **group** is a set $G$ with a binary operation $*$ that satisfies the following four axioms:
1. **Closure**. If $a, b \in G$, $a * b \in G$ for all $a$, $b$.
2. **Associativity**. For all $a, b, c \in G$, $(a * b) * c = a * (b * c)$.
3. **Identity**. There exists an **identity element** $e\in G$ such that $a * e = e * a = a$ for all  $a \in G$.
4. **Inversibility**. For all $a \in G$, there exists an **inverse element** $a^{-1}$ such that $a * a^{-1} = a^{-1} * a = e$, the identity element.

## Matrix groups

### Orthogonal matrices

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The set $G$ of all $n\times n$ orthogonal matrices $Q$ such that $Q^T Q = I$ forms a group.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Define the binary operation $*$ over this group as matrix multiplication.

1. **Closure**. If $P$, $Q$ are both orthogonal ($P, Q \in G$), then $(PQ)^{T}(PQ) = Q^{T}P^{T}PQ = Q^{T}IQ = Q^{T}Q = I$. Thus $PQ \in G$.

2. **Associativity**. True by associativity of matrix multiplication.

3. **Identity**. True by existence of identity matrix $I$.

4. **Inversibility**. By definition, if $Q \in G$, then $Q^T = Q^{-1}$; if $Q$ exists, then $Q^T$ must exist. $Q^{-1}$ is also in $G$, as $(Q^{-1})^{-1} (Q^{-1}) = (Q^T)^{-1} (Q^{T}) = I$ by $Q^T = Q^{-1}$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Denote the group containing all $n\times n$ orthogonal matrices as $O(n)$.

### Orthogonal matrices with $\det$ 1

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The set $SO(n)$ of all $n\times n$ orthogonal matrics which have determinant 1 forms a group.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

1. **Closure**. Let $P, Q$ be orthogonal matrices with $\det 1$. Then $PQ$ is orthogonal, as shown above, and $\det (PQ) = \det P \det Q = 1 \cdot 1 = 1$.

2. **Associativity**. True by associativity of matrix multiplication.

3. **Identity**. True by existence of identity matrix $I$.

4. **Inversibility**. $P^{-1}$ is orthogonal as shown above; we also have $\det P^{-1} = \frac{1}{\det P} = \frac{1}{1} = 1$.

### Length-Preserving Matrices

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Let $P$ be a real $n\times n$ matrix. Then the following statements are equivalent:
1. $P$ is orthogonal.
2. The columns of $P$ are orthonormal.
3. $P$ preserves the scalar product: $\mathbf{x\cdot y} = (P\mathbf{x})\cdot (P\mathbf{y})$ for vectors $\mathbf{x,y}\in \mathbb{R}^n$.
4. $P$ is a *linear isometry*, i.e. it preserves the length of vectors: $|\mathbf{x}| = |P(\mathbf{x})|$.
5. If $\{v_1, ..., v_n\}$ form an orthonormal list, then $\{Pv_1, ..., Pv_n\}$ form an orthonormal list (and thus $P$ is a transformation matrix between two orthonormal bases).

Note that any two of the statements above form an "if-and-only-if"; one implies the other, and vice versa.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

**1 -> 2**. Let $P$ be an orthogonal matrix; we want to prove that its columns are orthonormal, i.e. if $P$ has columns 
$$
P = \begin{bmatrix}
p_1 & p_2 & ... & p_n
\end{bmatrix}
$$
then $p_i \cdot p_j = 0$ and $|p_i| = p_i \cdot p_i = 1$ for all $i \neq j = 1, 2, ..., n$. We also have $PP^T = I$, or, in suffix notation,
$$
P_{ik}P_{jk} = (p_i)_k (p_j)_k = p_i \cdot p_j = \delta_{ij}.
$$


**2 -> 3**. We know that $P$ has orthonormal columns; we want to prove that it preserves the scalar product with $(P\mathbf{x})\cdot (P \mathbf{y}) = \mathbf{x\cdot y}$ for all vectors $\mathbf{x,y}\in\mathbb{R^n}$. From above, we know that if the columns of $P$ are orthonormal, then $P$ is orthogonal. We thus have
$$
(P\mathbf{x})\cdot (P\mathbf{y}) =(P\mathbf{x})^T (P\mathbf{y}) = \mathbf{x}^T P^T P \mathbf{y} 
$$
where $P^T P = I$ by definition of orthogonality, which means
$$
(P\mathbf{x})\cdot (P\mathbf{y}) = \mathbf{x}^T \mathbf{y} = \mathbf{x\cdot y}
$$
by definition of the real scalar product.

**3 -> 4**. For any vector $\mathbf{x} \in \mathbb{R^n}$, we have
$$
|P(\mathbf{x})| = (P\mathbf{x})\cdot (P\mathbf{x}) = \mathbf{x\cdot x} = |\mathbf{x}|
$$
by preservation of the scalar product.


**4 -> 5**. If $P$ preserves lengths, then $Pv_1$ has the same length as $v_1$, $Pv_2$ as $v_2$, etc. Thus if $v_1, ..., v_n$ are each of unit length, then $Pv_1, ..., Pv_n$ are also each of unit length. Now consider
$$
(Pv_i) \cdot (Pv_j)
$$
which, by scalar product preservation, is equal to $v_i \cdot v_j = 0$ by orthonormality. Thus $Pv_i$ form an orthonormal list.

**5 -> 1**. Proven in "Hermitian Matrices and their Eigenvalues" (transformation matrices between orthonormal bases are orthogonal).

****

These equivalent statements directly lead to

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The set of all (real) $n\times n$ length-preserving transformation matrices form a group.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 
 By the previous theorem, real length-preserving transformation matrices are orthogonal matrices and vice versa. As orthogonal matrices form a group, so must length-preserving transformation matrices.

 ****

In fact, particularly in the 2-dimensional group of orthogonal matrices $O(n)$ - and their subgroup $SO(n)$, which are such matrices with determinant 1 -  length-preserving/orthogonal matrices serve very specific purposes:

 > <span style="background-color: #12ffd7; color: black;">Theorem</span>. A two-dimensional length-preserving (orthogonal) matrix $P \in O(2)$ is equivalent to either one of the following: the rotation matrix
$$
P = \begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
$$
> or the reflection matrix
$$
P = \begin{bmatrix}
\cos \theta & \sin \theta \\
\sin \theta & -\cos \theta
\end{bmatrix}
$$
> which is a reflection in the line $y \cos  (\theta/2) = x\sin (\theta/2)$. 

A little tangent on the reflection matrix. To derive it, consider the following. If a reflection about the line
$$
y =x \tan \theta
$$
(which encompasses all real lines through the origin, as $\tan \theta$ has a range over all the reals) sends a general vector 
$$
\mathbf{x} = \begin{bmatrix}
x \\ y
\end{bmatrix}
$$
to 
$$
\mathbf{x'} = \begin{bmatrix}
x' \\ y'
\end{bmatrix}
$$
what are $x'$ and $y'$ in terms of $x$ and $y$? A reflection of $\mathbf{x}$ in a line with direction vector $\mathbf{d}$ can be understood as $\mathbf{x}$ minus two times its perpendicular vector onto the line. This perpendicular vector is given by $\mathbf{x}$ minus its projection onto the direction $\mathbf{d}$:
$$
\mathbf{x' = x} - 2(\mathbf{x} - P_{\mathbf{d}}(\mathbf{x})) = 2P_{\mathbf{d}}(\mathbf{x}) - \mathbf{x}
$$
As previously found, this projection is equivalent to
$$
P_{\mathbf{d}}(\mathbf{x}) = \frac{\mathbf{d\cdot x}}{\mathbf{d\cdot d}}\mathbf{d}
$$
And in the case $y = x \tan \theta$, which has direction vector 
$$
\mathbf{d} = \begin{bmatrix}
1 \\
\tan \theta
\end{bmatrix}
$$
we thus have 
$$
\begin{aligned}
P_{\mathbf{d}}(\mathbf{x}) &= \frac{\mathbf{d\cdot x}}{\mathbf{d\cdot d}}\mathbf{d} \\
&= \frac{x+(\tan \theta) y}{1^2 + \tan^2 \theta}\begin{bmatrix}
1 \\
\tan \theta
\end{bmatrix} \\
&= \frac{x+(\tan \theta) y}{\sec^2 \theta}\begin{bmatrix}
1 \\
\tan \theta
\end{bmatrix} \\
&= \begin{bmatrix}
(\cos^2 \theta)x + (\sin \theta \cos \theta)y \\
(\sin \theta \cos \theta)x + (\sin^2 \theta)y
\end{bmatrix}

\end{aligned}
$$
Plugging this into
$$
\mathbf{x'} = 2P_{\mathbf{d}}(\mathbf{x}) - \mathbf{x}
$$
gives
$$
\mathbf{x}' = \begin{bmatrix}
(2\cos^2 \theta - 1)x + 2(\sin\theta \cos\theta) y \\
2(\sin\theta \cos\theta) x + (2\sin^2 \theta - 1)y
\end{bmatrix} = \begin{bmatrix}
(\cos 2\theta) x + (\sin 2\theta) y\\
(\sin 2\theta) x + (-\cos 2\theta)y
\end{bmatrix} 
$$
which can be written in matrix form as
$$
\mathbf{x'} = \begin{bmatrix}
\cos 2\theta & \sin 2\theta \\
\sin 2\theta & -\cos 2\theta
\end{bmatrix} \mathbf{x}
$$
giving the reflection matrix
$$
P = \begin{bmatrix}
\cos 2\theta & \sin 2\theta \\
\sin 2\theta & -\cos 2\theta
\end{bmatrix}.
$$

****

With this in mind, let's prove that all $2\times 2$ orthogonal matrices are either reflections or rotations.

> <span style="background-color: #1eff12; color: black;">Proof</span> by brute force.

Let
$$
P = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
with $a, b, c, d$ real, i.e. $P$ is any general real matrix. Suppose that $P \in O(2)$, and thus that $P$ satisfies $PP^T = I$:

$$
\begin{aligned}
PP^T &= \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}\begin{bmatrix}
a & c \\
b & d
\end{bmatrix} \\
&= \begin{bmatrix}
a^2 +b^2 & ac + bd \\
ac + bd & c^2 + d^2
\end{bmatrix} \\
&= \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}.
\end{aligned}
$$
Thus, $a, b, c, d$ must satisfy
$$
\begin{cases}
a^2 + b^2 = 1 \\
ac+bd = 0 \iff ac = -bd\\
c^2 + d^2 = 1
\end{cases}
$$
However, $P$ must also satisfy $PP^T = I$, yielding the equations
$$
\begin{cases}
a^2 + c^2 = 1 \\
ab+cd = 0 \iff ab = -cd\\
b^2 + d^2 = 1
\end{cases}
$$
If $a^2 + c^2 = 1$, we can parametrize $a = \cos \theta$ and $c = \sin \theta$ for some real $\theta$ (this is representative of every possible pair $(a,c)$.) Thus, as $a^2 + b^2 = 1$ and $c^2 + d^2 = 1$, we also have $b = \pm \sin \theta$ and $d = \pm \cos \theta$. However, as $ac = -bd$, $b$ and $d$ have opposite signs; thus either $b = \sin \theta, d = -\cos\theta$, resulting in
$$
P = \begin{bmatrix}
\cos \theta & \sin \theta \\
\sin \theta & -\cos \theta
\end{bmatrix}
$$
which is a reflection, or $b = -\sin\theta, d = \cos\theta$, resulting in
$$
P = \begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
$$
which is a rotation.

> <span style="background-color: #ffb812; color: black;">Remark</span>. The determinant of a rotation matrix (as above) is $1$; the determinant of a reflection matrxi is $-1$. Thus we conclude that if $P \in SO(2)$, the group of orthogonal matrices with determinant 1, then it is a rotation matrix.

