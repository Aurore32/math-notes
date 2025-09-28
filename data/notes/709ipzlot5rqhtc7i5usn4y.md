> A lright, who let the linear algebra nerds out of the insane asylum again??

## The general linear group

> <span style="background-color: #03cafc; color: black;">Remark</span>. In the following section, $\mathbb{F}$ will denote either $\mathbb{R}$ or $\mathbb{C}$ in statements that are applicable to both real and complex matrices. This fits in nicely: $\mathbb{R}$ stands for "real numbers", $\mathbb{C}$ stands for "complex numbers", and $\mathbb{F}$ stands for "f*ck group theory".

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **general linear group** of $n\times n$ matrices, denoted $GL_{n}(\mathbb{F})$, as a group with binary operation equal to matrix multiplication, identity equal to the $n\times n$ identity matrix $I_n$, and elements encompassing the set of all invertible $n\times n$ matrices
$$
\{A \in M_{n\times n}(\mathbb{F}): \det A \neq 0\}
$$
> where $M_{n\times n}(\mathbb{F})$ denotes the set of all $n\times n$ matrices with entries in $\mathbb{F}$, and non-zero determinants imply invertibility.

As always, we'll churn out the group axioms at breakneck speed like we're Cardi B churning out flops for her new album: identity holds for $I_n$, invertibility holds because $\det A \neq 0$, closure holds from multiplicativity of the determinant, and associativity is inherited from matrix multiplication. (I'm now presenting to the emergency room with acute-onset left lung collapse.)

We note that the determinant serves as a convenient map between $GL_n(\mathbb{F})$ and $\mathbb{F}$ excepting $0$; in fact, we have

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. The determinant function $\det: GL_n(\mathbb{F}) \to \mathbb{F}\backslash\{0\},\ A \to \det A$ is a surjective homomorphism between the groups $GL_n(\mathbb{F})$ and $\mathbb{F} \backslash 0$, both defined under multiplication.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

We have, for matrices $A, B \in GL_n(\mathbb{F})$ and $A\cdot_{GL}B$ denoting their product under matrix multiplication,
$$
\det (A\cdot_{GL}B) = \det A \cdot \det B
$$
where $\cdot$ denotes scalar multiplication. This satisfies the definition of a homomorphism, as $\cdot$ is the binary operation defined for the group $\mathbb{F} \backslash \{0\}$. 

Surjectiveness derives by construction from the matrix
$$
A = \begin{bmatrix}
x & & & \\
& 1 & & \\
& & \ddots & \\
& & & 1
\end{bmatrix}
$$
i.e. the identity matrix with its top-left element replaced by an arbitrary $x \in \mathbb{F}$; the determinant of this matrix is $x$ regardless of which $x \in \mathbb{F}$ is chosen (except zero), so its image encompasses all of $\mathbb{F}$.

In particular, the kernel of this homomorphism defined by the determinant is a subgroup of $GL_n(\mathbb{F})$ with special properties; in a flash of inspiration borne from the fruits of their infinite wisdom, mathematicians have deemed it fit to be called

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **special linear group**. Denote by $SL_n(\mathbb{F})$ the kernel of the determinant homomorphism mapping between $GL_n(\mathbb{F}) \to \mathbb{F} \backslash \{0\}$; as the identity of $\mathbb{F} \backslash \{0\}$ is $1$ under multiplication, $SL_n(\mathbb{F})$ encompasses all $n\times n$ matrices that have determinant $1$.

As $SL_n(\mathbb{F})$ is the kernel of a homomorphism, it is a normal subgroup; an application of the **<sup>FIRST</sup> ISOMORPHISM THEOREM!!!** shows that
$$
GL_n(\mathbb{F}) / SL_n(\mathbb{F}) \cong \text{Im}(\det) = \mathbb{F}\backslash \{0\}.
$$

## Group actions of matrix groups

> <span style="background-color: #ffb812; color: black;">Proposition</span>. **Left matrix multiplication action.** $GL_n(\mathbb{C})$ (not $\mathbb{F}!$) acts faithfully on $\mathbb{C^n}$, the set of complex vectors in $n$-dimensional space, via left matrix multiplication:
$$
\forall A \in GL_n(\mathbb{C}), \mathbf{v} \in \mathbb{C^n}:\ \phi(A, \mathbf{v}) = A\mathbf{v}.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

There are three requirements for defining a group action from a group $G$ on a set $X$: 1) the identity does not change any element it acts on (identity), 2) it maps all elements in $X$ to another element in $X$ (closure), and 3) it is associative (associativity).

For identity, we have $I\mathbf{v} = \mathbf{v}$ by definition of $I$; for closure, any $n\times n$ matrix multiplied by a $n \times 1$ vector yields a $n\times 1$ vector still in $\mathbb{C^n}$; and for associativity, $(AB)\mathbf{v} = A(B\mathbf{v})$ by associativity of matrix multiplication.

As for faithfulness, we need to prove that if a matrix keeps every vector in $\mathbb{C^n}$ the same after multiplication, then it must be the identity matrix:
$$
A \mathbf{v} = \mathbf{v},\ \forall \mathbf{v} \implies A = I_n.
$$
A matrix is uniquely determined by how it acts on a basis of $\mathbb{C^n}$, e.g. on the standard normal basis $(1,0,0,..,0),...,(0,0,0,..,1)$. If $A\mathbf{v} = \mathbf{v}$ for any $\mathbf{v}$, then $A$ must map all the elements of this basis to themselves; and is thus the matrix with columns  $(1,0,0,..,0),...,(0,0,0,..,1)$, which is the identity matrix. Thus the left matrix multiplication action only acts as the identity when it *is* the identity, and is faithful.

This group action has two possible orbits. The first is formed by the zero vector $\mathbf{0}$ alone: $A\mathbf{0} = \mathbf{0}$ for any matrix $A \in GL_n(\mathbb{C})$, and if $A\mathbf{v} = \mathbf{0}$, then we have $\mathbf{v} = \mathbf{0}$ because $A$ is invertible. The second involves every other vector, i.e. $\mathbb{C^n} \backslash \{\mathbf{0}\}$: the general equation for any two $\mathbf{v, w} \in \mathbb{C^n}$ and $A \in GL_n(\mathbb{C})$
$$
A\mathbf{v} = \mathbf{w}
$$
has an infinite number of solutions, because there are $n \times n = n^2$ different entries in $A$ and only $n$ equations to be solved for, i.e.
$$
\begin{cases}
A_{11}v_1 + A_{12}v_2 + ... + A_{1n}v_n = w_1  \\
A_{21}v_1 + A_{22}v_2 + ... + A_{2n}v_n = w_2  \\
\vdots \\
A_{n1}v_1 + A_{n2}v_2 + ... + A_{nn}v_n = w_n  \\
\end{cases}
$$
There are $n^2$ variables and only $n$ equations, so a possible matrix $A$ will always exist as long as $\mathbf{v, w} \neq \mathbf{0}$.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. **Change of basis action.** $GL_n(\mathbb{C})$ acts on the set of all complex $n\times n$ matrices $M_{n\times n}(\mathbb{C})$ by conjugation (i.e. a change of basis): for $P \in GL_n(\mathbb{C})$ and $A \in M_{n\times n}(\mathbb{C})$, the following group action
$$
P \bullet A = PAP^{-1}
$$
> represents a change of basis of the matrix $A$ via the change of basis matrix $P$, and is well-defined.

The well-definedness of this group action originates from conjugation; changing the basis of a matrix $A$ via a change-of-basis matrix $P$ can be thought of as conjugating $A$ with $P$. The orbits of this action are matrices who represent the same linear map under different orthonormal bases.

## Orthogonal matrix groups
### The orthogonal group

> <span style="background-color: #03cafc; color: black;">Definition</span>. Denote $O(n)$ by the group of all $n\times n$ (real) orthogonal matrices under matrix multiplication: $O(n) = \{P \in GL_n(\mathbb{R}): PP^{T} = I_n\}$, where $T$ denotes matrix transposition.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. $O(n)$ is a subgroup of $GL_n(\mathbb{R})$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $A$ and $B$ be two $n\times n$ orthogonal matrices: $A, B \in O(n)$. If we can prove that $O(n)$ is non-empty (which is isn't, because the identity matrix $I_n$ is orthogonal), and that $AB^{-1} \in O(n)$, $O(n)$ is a subgroup of $GL_n(\mathbb{R})$ (as it is a group of real invertible matrices, and thus already a subset of $GL_n(\mathbb{R})$).

We have
$$
(AB^{-1})^{-1} = BA^{-1} = BA^T = (B^T)^T A^T = (AB^T)^T = (AB^{-1})^T
$$
and thus $AB^{-1} \in O(n)$. (For any matrix $P \in GL_n(\mathbb{R})$, we have
$$
(PP^T)_{ij} = P_{ik}P_{jk} = \delta_{ij},
$$
using the dreaded summation notation, as our condition for $P \in O(n)$.)

> <span style="background-color: #ffb812; color: black;">Proposition</span>. Left matrix multiplication by an orthogonal matrix on two vectors $\mathbf{x}$ and $\mathbf{y}$ is an **isometry** of $\mathbf{x}$ and $\mathbf{y}$ under the dot product:
$$
(A\mathbf{x}) \cdot (A\mathbf{y}) = \mathbf{x} \cdot \mathbf{y}.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>. (What is this "Vectors and Matrices" nonsense? Is this what the paupers are learning in school nowadays? Jeeves, take it away!)

We have
$$
(A\mathbf{x}) \cdot (A\mathbf{y}) = (A\mathbf{x})^T (A\mathbf{y}) = \mathbf{x}^T A^TA\mathbf{y} = \mathbf{x}^T \mathbf{y} = \mathbf{x\cdot y}
$$
as, by definition of orthogonal matrices, $A^T A = I$. Furthermore we have
$$
(A\mathbf{x}) \cdot (A\mathbf{x}) = |A\mathbf{x}|^2 = \mathbf{x}\cdot \mathbf{x} = |\mathbf{x}|^2
$$
and since magnitudes are non-negative, taking the square root of both sides gives $|A\mathbf{x| = |x|}$. 

As an aside, multiplication by $A$ also preserves both the distance and the angle between $\mathbf{x}$ and $\mathbf{y}$. This originates from
$$
\begin{aligned}
|A(\mathbf{x - y})|^2 &= (A(\mathbf{x-y}))^T(A(\mathbf{x-y})) \\
&= (\mathbf{x-y})^T A^TA(\mathbf{x-y}) \\
&= (\mathbf{x-y})^T(\mathbf{x-y}) \\
&= |\mathbf{x-y}|
\end{aligned}
$$
and
$$
\begin{aligned}
\cos(\angle(A\mathbf{x},A\mathbf{y})) = \frac{(A\mathbf{x})\cdot(A\mathbf{y})}{|A\mathbf{x}||A\mathbf{y}|} = \frac{\mathbf{x}\cdot \mathbf{y}}{|\mathbf{x}||\mathbf{y}|} = \cos(\angle(\mathbf{x},\mathbf{y}))
\end{aligned}
$$
with equality between the angles because $\cos$ is a one-to-one function between $0$ and $\pi$.

### Rotations and reflections

> <span style="background-color: #03cafc; color: black;">Definition</span>. We observe that, much like the general linear group, the determinant $\det A$ is again a surjective homomorphism between $O(n) \to \{-1,1\}$; define the **special orthogonal group** as the group of matrices which form the kernel of this homomorphism, i.e. all orthogonal matrices $A$ such that $\det A = 1$. This group is denoted by $SO(n)$.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. $SO(2)$ is the group of rotation matrices in $\mathbb{R^2}$ about the origin.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Suppose that $A \in SO(2)$; then $AA^T = I$ and $\det A = 1$. Brute-forcing these conditions on an arbitrary matrix $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$ yields
$$
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} a & c \\ b & d \end{bmatrix} = \begin{bmatrix} 
a^2 + b^2 & ac + bd \\
ac + bd & c^2 + d^2
\end{bmatrix} = \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
$$
to achieve orthogonality, yielding
$$
\begin{cases}
a^2 + b^2 = c^2 + d^2 = 1\\
ac+ bd = 0 \\
\det A = ad - bc = 1
\end{cases}
$$
with the last equation originating by definition of $SO(2)$. As $a, b, c,d$ are real, their squares are non-negative; and thus all of $a, b, c, d \in [-1, 1]$, and can be parameterized by $\pm \sin \theta$ and $\pm \cos \theta$. ($\sin$ and $\cos$ map onto $[-1, 1]$ surjectively and $\pm \cos \theta$ is the only solution for $x$ to $\sin^2 \theta + x^2 = 1$ among the real numbers.)

Suppose, without loss of generality, that $a = \cos \theta$ and $b = \pm \sin \theta$; a quick substitution into the second equation gives
$$
c \cos \theta \pm d \sin \theta = 0
$$
which leads to $d = \pm c \cot \theta$, and thus $c^2 + d^2 = c^2 \csc^2 \theta = 1$ yielding $c = \pm \sin \theta$ and $d = \pm \cos \theta$. To determine their signs, consider the second equation again: $ac$ and $bd$ must multiply to opposite signs, so either $c$ is $\sin \theta$ and $b$ and $d$ have opposite signs or $c$ is $-\sin \theta$ and $b$ and $d$ have the same sign. Checking the last equation shows that $ad = \cos^2 \theta$, and $bc = -\sin^2 \theta$; $d$ must be $\cos \theta$ and $b$ and $c$ have opposite sign. Combining this information gives us either
$$
\begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
$$
or
$$
\begin{bmatrix}
\cos \theta & \sin \theta \\
-\sin \theta & \cos \theta
\end{bmatrix}
$$
which describe a rotation about the origin by an angle $\theta$ counterclockwise and clockwise, respectively.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. A matrix in $O(2)$ is either a rotation about the origin or a reflection across a line through the origin.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

From the above, we know that a subgroup of $O(2)$ - $SO(2)$ - is a group of all rotation matrices in $\mathbb{R^2}$ about the origin; $SO(2)$ must be half the order of $O(2)$ as the bijection
$$
\phi(\begin{bmatrix}
a & b \\
c& d
\end{bmatrix}) = \begin{bmatrix}
-a & -b \\
c & d
\end{bmatrix}
$$
establishes a one-to-one correspondence between $SO(2)\backslash O(2)$ and $O(2)$, where the determinant of the matrix on the right-hand side is $-ad - bc = -(ad - bc)$, equalling $-1$ times the determinant of the left-hand side matrix. Thus, the left cosets of $SO(2)$ partition $O(2)$ into two sets of equal size, with the other coset being matrices of determinant $-1$; these matrices are in the general form
$$
\begin{bmatrix}
\cos \theta & -\sin \theta \\
-\sin \theta & -\cos \theta
\end{bmatrix}.
$$
Consider the effects of left multiplication of this matrix on a vector in $\mathbb{R^2}$, $\mathbf{x} = \begin{bmatrix}
x \\
y
\end{bmatrix}$:
$$
\begin{bmatrix}
\cos \theta & -\sin \theta \\
-\sin \theta & -\cos \theta
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix} = \begin{bmatrix}
x \cos \theta - y \sin \theta \\
-x \sin \theta - y\cos \theta
\end{bmatrix}
$$ 
We know that a reflection over a line normal to some vector $\mathbf{a} = \begin{bmatrix}a \\ b \end{bmatrix}$ takes the form
$$
R_{\mathbf{a}}(\mathbf{x}) = \mathbf{x} - 2(\mathbf{x \cdot a})\mathbf{a} = \begin{bmatrix}
x - 2(ax+by)a \\
y - 2(ax+by)b
\end{bmatrix} = 
\begin{bmatrix}
(1-2a^2)x - 2aby\\
(1-2b^2)y - 2abx
\end{bmatrix} 
$$
where setting $2ab = \sin \theta$, $1 - 2a^2 = \cos \theta$, and $1 -2b^2 = -\cos\theta$ yields the desired result that the matrix represents a reflection.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. As every orthogonal matrix in $O(2)$ is thus either a reflection or a rotation, all rotations are products of two reflections (as if $\det A = \det B = -1$, then $\det (AB) = 1$ and $AB \in SO(2)$, making $AB$ a rotation).

Rotations in $\mathbb{R^3}$ are also characterized by the special orthogonal matrix group $SO(3)$:

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Every matrix $A \in SO(3)$, i.e. all orthogonal $3\times 3$ matrices with determinant $1$, jis a rotation when viewed through some basis in $\mathbb{R^3}$: in other words, it is conjugate to the general rotation matrix about the $z$-axis
$$
\begin{bmatrix}
\cos \theta & -\sin \theta & 0 \\
\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
> <span style="background-color: #1eff12; color: black;">Proof</span>. TL;DR - Prove that any matrix $A$ in $SO(3)$ has $1$ as an eigenvalue; consider $A$ through its basis of eigenvectors; show that this matrix under an eigenvector change of basis is a rotation matrix.

First, we would like to show that any matrix $A \in SO(3)$ has the eigenvalue $1$; supposing that this eigenvector is $v$, in an orthonormal basis $(v_1, v_2, v)$ we have (without loss of generality)
$$
Av = v
$$
and so the last column of $A$ is in the form $(0,0,1)$; furthermore, we have
$$
(Av_1) \cdot (v) = (Av_1) \cdot (Av) = v_1 \cdot v = 0
$$
by orthonormality and isometry, with a similar result for $v_2$, leading to $Av_1$ and $Av_2$ being independent of $v$. Thus, the expression for the first two columns of $A$ in this basis have no entry in the third row (representing $v$).

Showing that $A$ has an eigenvalue $1$ is equivalent to showing that $\det (A - I) = 0$; recalling that $A^T A = I$, this is accomplished via
$$
\begin{aligned}
\det (A - I) &= \det (A - AA^T) \\
&= \det (A (I - A^T)) \\
&= \det A \det (I - A^T) \\
&= \det (I - A^T),\ \text{as $A \in SO(3)$} \\
&= \det ((I-A)^T) \\
&= \det (I - A),\ \text{as $\det A^T = \det A$} \\
&= -\det(A - I)
\end{aligned}
$$
leading to $\det (A - I) = 0$. Thus $A$ has the form
$$
\begin{bmatrix}
a & b & 0 \\
c & d & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
with $\det A = 1$ leading to $ad - bc = 1$; and so the matrix formed by
$$
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
$$
is an element of $SO(2)$, and can thus be written
$$
\begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
$$
as desired.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. Every element in $O(3)$ can be written as the product of at most three reflections.

> <span style="background-color: #1eff12; color: black;">Proof</span>

As with $O(2)$, $SO(3)$ is a subgroup of index $2$ of $O(3)$ and thus partitions $O(3)$ into two left cosets: $SO(3)$ itself, which includes all matrices with determinant $-1$, and $O(3)\backslash SO(3)$, which includes all matrices with determinant $1$.

If a matrix $A \in SO(3)$, then we have
$$
A = \begin{bmatrix}
\cos \theta & -\sin \theta & 0 \\
\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{bmatrix} = 
\begin{bmatrix}
1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 1
\end{bmatrix} 
\begin{bmatrix}
\cos \theta & \sin \theta & 0 \\
\sin \theta & -\cos \theta & 0 \\
0 & 0 & 1
\end{bmatrix} 
$$
which is a composition of two reflections, one about the $y$-axis and the other a reflection as verified for $SO(2)$ (except holding the $z$-axis constant). If instead a matrix $B$ lies in the other left coset $O(3)\backslash SO(3)$, then it can be written in the form
$$
B= \begin{bmatrix}
1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 1
\end{bmatrix} A
$$
where $A \in SO(3)$ (as this matrix has determinant $-1$, and is thus in $O(3)\backslash SO(3)$.) $A$ is a product of two reflections, and so $B$ is a product of at most three reflections. 
