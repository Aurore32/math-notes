---
id: n417qwzj6g9sqx0h2tcpsoo
title: Matrix Rank
desc: ''
updated: 1736483314568
created: 1736395254359
---
## Matrix Rank 2: Electric Boogaloo
In the context of a linear map, we defined the rank of a matrix $A$ as the dimension of its image: $r(A)=\dim A(\mathbb{R}^n)$. We previously derived two conclusions: 

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. 
1. In the context of $A$ representing a linear map from $\mathbb{R}^n$ to $A(\mathbb{R}^n)$ under the standard basis $\{e_j\} = \{(1,0,...,0),...,(0,0,...,1)\}$, the vectors that $e_j$ are mapped to under $A$ - $A(e_j)$ - are represented by the columns of $A$. 
2. $A(e_1), A(e_2), ..., A(e_n)$ spans the image of $A$.

Building upon the second statement and the notion of rank, we further note that

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Within the spanning set $\{A(e_1),A(e_2),...,A(e_n)\}$ spanning the image of $A$, the number of vectors which are linearly independent to each other must equal $r(A)$. This derives organically from the definition of dimension and rank.

As Lemma 1 notes that $A(e_i)$ are the columns of $A$, this is equivalent to stating that $r(A)$ is the number of linearly independent columns of $A$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **row rank** of a matrix as its number of linearly independent rows; define the **column rank** as its number of linearly independent columns. 

But sike! You've been successfully duped, tricked, deceived, and possibly even bamboozled, because

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The row rank of any matrix is equal to its column rank. Denote this rank by $\text{rank} A$, or if $A$ also represents a linear map, $r(A)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $A$ be a $m\times n$ matrix, where $m$ need not equal $n$. Suppose that $A$ has row rank $r$; that is, it has $r$ linearly independent rows. Let $A^T_{(i)}$ denote the $i$th row of $A$ and $A_{(j)}$ denote the $j$th column of $A$. <br/><br/>
If $A$ has row rank $r$, then there is a set of row vectors $v = \{v^T_{(1)}, v^T_{(2)}, ..., v^T_{(r)}\}$ corresponding to $r$ different rows of $A$ that are linearly independent. All rows of $A$ can be written as a linear combination of the elements of $v$ by definition of linear independence; these rows are either in $v$, or are linearly dependent with the elements of $v$. Thus, we write
$$
A^T_{(i)} = \sum_{k=1}^r a_{ik} v^T_{(k)}
$$
> for certain scalars $a_i$. In scalar form, this becomes
$$
A_{ij} = \sum_{k=1}^r a_{ik} v^T_{(k)j}
$$
> and if $j$ is fixed, this becomes
$$
\begin{aligned}
\begin{bmatrix}
A_{1j} \\ A_{2j} \\ \vdots \\ A_{mj}
\end{bmatrix} &= \begin{bmatrix}
\sum_{k=1}^r a_{1k} v^T_{(k)j} \\
\sum_{k=1}^r a_{2k} v^T_{(k)j} \\
\vdots \\
\sum_{k=1}^r a_{mk} v^T_{(k)j}
\end{bmatrix}  \\
&= v^T_{(1)j}\begin{bmatrix}a_{11} \\ a_{21} \\ \vdots \\ a_{m1} \end{bmatrix} + 
v^T_{(2)j}\begin{bmatrix}a_{12} \\ a_{22} \\ \vdots \\ a_{m2} \end{bmatrix} + ... + 
v^T_{(r)j}\begin{bmatrix}a_{1r} \\ a_{2r} \\ \vdots \\ a_{mr} \end{bmatrix}
\end{aligned}
$$
> and thus any column of $A$ can be written as a linear combination of $r$ distinct column vectors. We deduce that the column rank of $A$ is less than or equal to $r$ by definition. <br/><br/>
As the exact same argument can be applied to $A^T$ to prove that the row rank is less than or equal to the column rank, we conclude that equal to each other. $\square$

To calculate the rank of a matrix, Gaussian elimination once again comes in handy; the number of linearly independent row vectors does not change under elementary row operations or reordering of columns, as adding a linear multiple of one row to another retains linear independence. Thus, the rank of a matrix is the number of non-empty rows it has after Gaussian elimination.

> <span style="background-color: #bc42f5; color: black;">Observation</span>. As previously proven, the determinant of a square matrix is the product of the elements on its diagonal after Gaussian elimination multiplied by a sign. Thus if $\det A = 0$, then at least one of these elements must be zero; this would indicate that at least one row is zero after Gaussian elimination, and that the rows of $A$ are linearly dependent.

## Homogeneous systems of linear equations

This section will analyze $n\times n$ matrices $A$, which represent linear systems of the form $A\mathbf{x=0}$, deemed **homogeneous systems**. As the inverse of a square matrix $A$ involves the reciprocal of $\det A$, the condition for invertibility is $\det A \neq 0$; thus if $\det A \neq 0$, then $A$ is invertible and $\mathbf{x=0}$ is the unique solution to the system. If $\det A = 0$, however, we're screwed.

Wait, hang on, we're not screwed. Let's take a closer look at $A\mathbf{x=0}$, under the condition $\det A = 0$ - now with a renewed understanding of rank!

> <span style="background-color: #03cafc; color: black;">Definition</span>. If $\det A = 0$, which implies the non-existence of $A^{-1}$, then the matrix $A$ is **non-invertible** or **singular** (not to be confused with **single**, which describes

> A **non-singular** matrix is such that $\det A \neq 0$ (an inverse exists).

### The Geometrical View

Consider the special case where $A$ is a **real** $3\times 3$ matrix, such that our realm of existence is $\mathbb{R}^3$ and our puny brains can actually comprehend what we're doing. Denote the rows of $A$ as $r^T_{(i)}$, such that
$$
A = \begin{bmatrix}
r^T_{(1)} \\
r^T_{(2)} \\
r^T_{(3)}
\end{bmatrix}
$$
where each $r_{(i)}$ is a row matrix rather than a single component. Thus, $A\mathbf{x=0}$ can be rewritten in scalar form as
$$
r_{(i)}^T \mathbf{x} = r_{(i)} \cdot \mathbf{x} = 0
$$
which represent three planes perpendicular to the vector $r_{(i)}$ in $\mathbb{R^3}$. As such, the set of solution vectors $\mathbf{x}$ lies at the intersection of these three planes, which takes one of the following three forms:
1. $r(A) = 3 \iff$ The planes intersect at a single point. As $\mathbf{x=0}$ is a solution to $A\mathbf{x=0}$, the point of intersection is necessarily the origin $O$.

    As stated previously, this is contingent upon $\det A \neq 0$, implying that Gaussian elimination on $A$ results in a full diagonal; this would mean that $r(A) = 3$ (all of the rows are linearly independent). This can also be demonstrated by the determinant being equivalent to the triple product $(r_{(1)}^T \times r_{(2)}^T)\cdot r_{(3)}^T$ in $\mathbb{R}^3$, which implies linear independence.

    If $\mathbf{x}$ lies in the intersection of the three planes, then we simultaneously have
    $$
    \begin{cases}
    r_{(1)} \cdot \mathbf{x} = 0 \\
    r_{(2)} \cdot \mathbf{x} = 0
    \end{cases}
    $$
    which implies that $\mathbf{x}$ is perpendicular to both $r_{(1)}$ and $r_{(2)}$, and thus $\mathbf{x} = \lambda (r_{(1)}\times r_{(2)})$, the cross-product of the two vectors. We also have
    $$
    r_{(3)}\cdot \mathbf{x} = r_{(3)}\cdot (\lambda(r_{(1)}\times r_{(2)})) = 0
    $$
    which implies $\lambda = 0$, as $\det A \neq 0$ implies that the above triple product is nonzero. Thus $\mathbf{x = 0}$ only, and $n(A)$, the nullity of $A$, is the dimension of the zero vector (which is zero). 

    (As an added bonus, we confirm that $r(A)+n(A)=\dim A = 3$.)

2. $r(A) = 2 \iff$ The planes intersect in a line. $r(A) = 2$ implies that exactly two rows of $A$ are linearly independent; without loss of generosity, assume that $r_{(1)}$ and $r_{(2)}$ are linearly independent, meaning that they do not lie on the same line and $(r_{(1)}\times r_{(2)}) \neq 0$. 

    In this case $\det A = 0$, because Gaussian elimination results in a diagonal with one zero. Following upon the above, we have $\mathbf{x} = \lambda (r_{(1)}\times r_{(2)})$; as $\det A = 0$, the triple product $(r_{(1)}\times r_{(2)})\cdot r_{(3)} = 0$, meaning that $\mathbf{x}\cdot r_{(3)}$ is already satisfied for all $\mathbf{x}$. Thus, $\mathbf{x}$ need only lie on the line $\mathbf{x} = \lambda (r_{(1)}\times r_{(2)})$. This would imply that $n(A)$, the dimension of the set of vectors $\mathbf{x}$, is 1 (a line). ($r(A) + n(A)$ is again 3).

3. $r(A) = 1 \iff$ The planes are all the same plane; all the rows of $A$ are linearly independent, implying that they are all parallel. This would mean that $r_{(i)} \times \mathbf{x}$ all describe the same plane, and thus the solution space is a plane with dimension $2$ ($n(A) = 2$ and $r(A)+n(A)=3$).

### The Linear Map View

As previously defined, the kernel or null-space of a matrix $A$ (now a $n\times n$ matrix, no longer restricted to the particular $3\times 3$ case) is the set of all vectors $\mathbf{x}$ such that
$$
A\mathbf{x} = 0,
$$
matching our definition for the homogeneous system of equations. As such $K(A)$ is the solution space of the system, with dimension given by $n(A)$, the nullity of $A$; by the rank-nullity theorem, $r(A) + n(A) = n$. This can be demonstrated through the following two cases; in essence, this constitutes a proof of the rank-nullity theorem.

> <span style="background-color: #1eff12; color: black;">Proof</span>. **Alternate proof of the rank-nullity theorem**.

**Case 1**. $n(A) = 0$; the solution space for $A\mathbf{x=0}$ is a single vector. We will claim that $r(A) = n$ in this case, meaning that all the columns (and, therefore, all the rows) of $A$ are linearly independent. If $\{e_j\}$ is the standard basis for $\mathbb{R}^n$, then, as shown previously, the $A(e_j)$ represent the columns of $A$.

**Claim**. The columns of $A$ are linearly independent: if $\sum_{j=1}^{n} a_{j} A(e_j) = \mathbf{0}$, then all of $a_1, ..., a_n = 0$.

**Proof**. 
$$
\begin{aligned}
\sum_{j=1}^{n} a_{j} A(e_j) &= \mathbf{0} \\
A(\sum_{j=1}^{n} a_{j} (e_j))&= \mathbf{0} \\
\sum_{j=1}^{n} a_{j} (e_j) &= \mathbf{0}
\end{aligned}
$$
and thus all of $a_j$ are zero, as the $e_j$ form a basis and are thus linearly independent. This implies that $r(A) = n$.

**Case 2**. $0< n(A) = r \leq n$. We claim that $r(A) = n-r$. Let $\{u_j\}$ for $j = 1, ..., r$ form a basis for the solution space of $A$, or equivalently the kernel of $A$, $K(A)$; let $\{v_i\}$ for $i=1,...,n$ form a basis for $A$ itself. By the extension lemma given in "Rank and Nullity", we extend $\{u_j\}$ to the set of vectors
$$
u=\{u_1, u_2, ..., u_r, v_{r+1}, ..., v_n\}
$$
which is a basis of $\mathbb{R}^n$, as proven previously. (The details of this extension are as follows: take every one of $v_1, ..., v_n$ and proceed in steps. For step $i$, append $v_i$ onto $u$ if it is not in $text{span} u$, and ignore $v_i$ otherwise).

We then claim that $\{A(v_{r+1}), A(v_{(r+2)}), ..., A(v_n)\}$ is a basis of the image of $A$, $A(\mathbb{R^n})$; this necessitates proving linear independence and span. 

**Span**. 
As
$$
u=\{u_1, u_2, ..., u_r, v_{r+1}, ..., v_n\}
$$
is a basis of $\mathbb{R^n}$, any vector $\mathbf{x} \in \mathbb{R}^n$ can be written as a linear combination of these vectors:
$$
\mathbf{x} = a_1 u_1 + a_2 u_2 + ... + a_r u_r + a_{r+1} v_{r+1} + ... + a_n v_n
$$
and thus any $A(\mathbf{x})$ can be written
$$
A(\mathbf{x}) = A(a_1 u_1 + a_2 u_2 + ... + a_r u_r + a_{r+1} v_{r+1} + ... + a_n v_n)
$$
however, as $\{u_1, u_2, ..., u_r\}$ form a basis for the null-space of $A$, we have
$$
 A(a_1 u_1 + a_2 u_2 + ... + a_r u_r) = 0
$$
and thus all $A(\mathbf{x})$ can be written
$$
A(\mathbf{x}) = A(a_{r+1} v_{r+1} + ... + a_n v_n)
$$
for some $a_{r+1}, ..., a_n$.

**Linear independence**. Suppose that $A(v_{i})$ for some $i = r+1, ..., n$ can be written as a linear combination of the other $A(v_{j})$:
$$
A(v_{i}) = \sum_{j\neq i} a_j A(v_{j}).
$$
This would imply that
$$
A(\sum_{j\neq i} a_j(v_{j}) - v_i) = 0
$$
and thus that $\sum_{j\neq i} a_j(v_{j}) - v_i \in K(A)$. As $\{u_i\}$ span $K(A)$, it is possible to find $a_i$ for $i = 1, ..., r$ such that
$$
a_1 u_1 + ... + a_r u_r = \sum_{j\neq i} a_j(v_{j}) - v_i
$$
which contradicts the set 
$$
u=\{u_1, u_2, ..., u_r, v_{r+1}, ..., v_n\}
$$
being a linearly independent basis. $\square$

## Inhomogeneous systems of linear equations
For a $n\times n$ matrix $A$ and a column vector $\mathbf{d}$ with $n$ rows, 
$$
A\mathbf{x} = \mathbf{d}
$$
describes an inhomogeneous system of linear equations. We've already commented on the **invertible case**: if $\det A \neq 0$, $A$ has an inverse and $\mathbf{x}$ has a unique solution $\mathbf{x} = A^{-1}\mathbf{d}$. However, if $\det A = 0$, then $n(A) > 0, r(A) < n$ and either:
1. $\mathbf{d}$ is not in the image of $A$; as such, there are no solutions and the system is *inconsistent*.
2. $\mathbf{d}$ is in the image of $A$. There are at least one solution and the system is *consistent*.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If $\mathbf{d} \in I(A)$, the image of $A$, then all solutions to $A\mathbf{x}=\mathbf{d}$ can be written in the form
$$
\mathbf{x} = \mathbf{x_0+y}
$$
> where $\mathbf{x_0}$ is a **particular solution** of the system and $\mathbf{y}$ is the solution to the corresponding homogeneous equation, $A\mathbf{x=0}$.

Note the similarities to homogeneous and inhomogeneous differential equations!

> <span style="background-color: #1eff12; color: black;">Proof</span>. If $\mathbf{y}$ satisfies $A\mathbf{y=0}$ and $\mathbf{x_0}$ satisfies $A\mathbf{x_0=d}$, then

$$
A(\mathbf{x_0+y})=A\mathbf{x_0}+A\mathbf{y}=\mathbf{d}+\mathbf{0}=\mathbf{d}.
$$

> <span style="background-color: #ffb812; color: black;">Proposition</span>.
1. If $n(A) = 0$, then the solution is unique (by definition). For a system in $\mathbb{R}^3$, this implies that the solution is a single point in space.
2. If $n(A) = 1$, the solution space is a line $\mathbf{x_0 +} \lambda\mathbf{t}$.
3. If $n(A)=2$, the solution space is a plane.
