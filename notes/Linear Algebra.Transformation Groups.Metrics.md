---
id: k0f8nh1skx99x6b1efjfbdi
title: Metrics
desc: ''
updated: 1737867321284
created: 1737792751447
---
### Metrics (or how to confuse me completely about scalar products)

Let $\{u_1, ..., u_n\}$ be a basis of $\mathbb{R}^n$, **not necessarily orthogonal or orthonormal**. If we were to write the components of vectors $\mathbf{x,y}\in\mathbb{R^n}$ in terms of $u_1, u_2, ..., u_n$, we would have
$$
\begin{cases}
\mathbf{x} = \sum_{i=1}^n x_i \mathbf{u}_i \\
\mathbf{y} = \sum_{i=1}^n y_i \mathbf{u}_i
\end{cases}
$$
for components $x_i$ of $\mathbf{x}$ and $y_i$ of $\mathbf{y}$. Thus, we write the dot product $\mathbf{x\cdot y}$ as
$$
\begin{aligned}
&\mathbf{x}\cdot \mathbf{y} \\
&= (\sum_{i=1}^n x_i \mathbf{u}_i)\cdot (\sum_{j=1}^n y_i \mathbf{u}_i) \\
&= \sum_{i=1}^n\sum_{j=1}^n x_i y_j (\mathbf{u_i} \cdot \mathbf{u_j}) \\
&= \sum_{i=1}^n\sum_{j=1}^n x_i G_{ij} y_j
\end{aligned}
$$
where we define the matrix $G$ as $G_{ij} = \mathbf{u_i \cdot u_j}$; note that $G$ is symmetric by commutativity of the real dot produdct. In matrix form, we can also write
$$
\mathbf{x}\cdot\mathbf{y} = \mathbf{x}^T G \mathbf{y}
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. For the basis $\{u_1,...,u_n\}$ defined above, call $G$ its **metric**. A **metric** is - at least in the context of this course - an application of changes of basis upon scalar products; call the scalar product $\mathbf{x}^T G \mathbf{y}$ a scalar product **with respect to the metrix $G$**.

> <span style="background-color: #ffb812; color: black;">Remark</span>. If $\mathbf{u_1, u_2, ..., u_n}$ are orthonormal, then $\mathbf{u_i\cdot u_j} = \delta_{ij}$, implying that $G = I$. Thus, orthonormal bases have their scalar products with respect to the metric $I$ (as expected); from previous results, we know that the group of matrices that preserve the scalar product with respect to $I$ form a group (orthogonal matrices).

## Lorentz transformations 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **Minkowski metric** in $\mathbb{R}^2$ to be
$$
J = \begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}
$$
> and the corresponding **Minkowski inner product** with respect to this metric as
$$
\langle\mathbf{x, y}\rangle  = \mathbf{x}^T J \mathbf{y} = x_1y_1 - x_2y_2.
$$

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The set of $2\times 2$ transformations $M$ that preserve the Minkowski inner product, i.e. that ensure
$$
\langle\mathbf{x, y}\rangle = \langle M\mathbf{x}, M\mathbf{y} \rangle
$$
> for vectors $\mathbf{x}$ and $\mathbf{y}$ in $\mathbb{R^2}$, are of the form
$$
J = M^T J M
$$
> where $J$ is as above.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

By definition of the Minkowski inner product, we have
$$
\langle M\mathbf{x}, M\mathbf{y} \rangle = (M\mathbf{x})^T J (M\mathbf{y}) = \mathbf{x}^T (M^T J M) \mathbf{y}
$$
which equals $\mathbf{x}^T J \mathbf{y}$, leading to $M^T J M = J$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. All such matrices $M$ come in one of the following two forms:
$$
M = \begin{bmatrix}
\cosh u & \sinh u \\
\sinh u & \cosh u
\end{bmatrix},\ M = \begin{bmatrix}
\cosh u & -\sinh u \\
\sinh u & -\cosh u
\end{bmatrix}
$$
> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $M$ be the general $2\times 2$ matrix
$$
M = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}.
$$
If $M$ satisfies $J = M^T J M$, then
$$
\begin{aligned}
\begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix} &= 
\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix} \\
&= \begin{bmatrix}
a & c \\
b & d
\end{bmatrix}\begin{bmatrix}
a & b \\
-c & -d
\end{bmatrix} \\
&=
\begin{bmatrix}
a^2 - c^2 & ab - cd \\
ab - cd & b^2 - d^2
\end{bmatrix}
\end{aligned}
$$
Allowing for
$$
\begin{cases}
a^2-c^2 = 1 \\
ab = cd \\
b^2 - d^2 = 1
\end{cases}
$$
Where we can parametrize $a^2-c^2 = 1$ as $a = \cosh u, c=\sinh u$ (which encompasses all real solutions to $a^2-c^2=1$.) As $ab$ and $cd$ have the same sign, we must have either $b = \sinh u, d = \cosh u$ (both positive) or $b = -\sinh u, d = -\cosh u$, matching the two cases shown above.

> <span style="background-color: #ffb812; color: black;">Remark</span>. The above two forms for $M$ look remarkably similar to rotation matrices and reflection matrices, except for the fact that they use hyperbolic cosines and sines instead of regular cosines and sines; they represent rotations and reflections respectively for numbers parametrized by hyperbolic angles.

Denote the **hyperbolic rotation** counterclockwise by hyperbolic angle $u$ as
$$
H_u = \begin{bmatrix}
\cosh u & \sinh u \\
\sinh u & \cosh u
\end{bmatrix}
$$
and the **hyperbolic reflection** over the line $\sinh(u/2)x = \cosh(u/2)y$ as
$$
H_{u/2.} = \begin{bmatrix}
\cosh u & -\sinh u \\
\sinh u & -\cosh u
\end{bmatrix}
$$

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **Lorentz boost** is a transformation represented by a matrix of the form
$$
B_v = \frac{1}{\sqrt{1-v^2}}\begin{bmatrix}
1 & v \\
v & 1
\end{bmatrix}.
$$ 
> Note that a Lorentz boost by **velocity** $\tanh u$, denoted $B_{\tanh u}$, is identicala to a hyperbolic rotation by $u$:
$$
\begin{aligned}
B_{\tanh u} &= \frac{1}{\sqrt{1-\tanh^2 u}}\begin{bmatrix}
1 & \tanh u  \\
\tanh u & 1
\end{bmatrix} \\
&= \frac{1}{\text{sech } u}
\begin{bmatrix}
1 & \tanh u  \\
\tanh u & 1
\end{bmatrix} \\
&= \begin{bmatrix}
\cosh u & \sinh u  \\
\sinh u & \cosh u
\end{bmatrix} \\
\end{aligned}
$$

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The set of Lorentz boosts form a group.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Lorentz boosts are identical to hyperbolic rotations of the form $\begin{bmatrix}
\cosh u & \sinh u  \\
\sinh u & \cosh u
\end{bmatrix}$.

**Closure**. 
$$
\begin{aligned}
&\begin{bmatrix}
\cosh u & \sinh u  \\
\sinh u & \cosh u
\end{bmatrix}
\begin{bmatrix}
\cosh w & \sinh w \\
\sinh w & \cosh w
\end{bmatrix} \\
&= \begin{bmatrix}
\cosh u \cosh w + \sinh u \sinh w & \cosh u \sinh w + \sinh u \cosh w  \\
\cosh u \sinh w + \sinh u \cosh w   & \cosh u \cosh w + \sinh u \sinh w
\end{bmatrix}  \\
&= 
\begin{bmatrix}
\cosh (u+w) & \sinh (u+w) \\
\sinh (u+w) & \cosh (u+w)
\end{bmatrix}
\end{aligned}
$$
which is also a hyperbolic rotation by angle $u+w$.

**Associativity** by corresponding associativity matrix multiplication.

**Identity** by $B_0 = \frac{1}{\sqrt{1-0^2}}\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} = I$. And finally,

**Inverse** by $H_{u}H_{-u} = I$: two rotation matrices of opposite angles cancel out.

$\square$

> Fin!