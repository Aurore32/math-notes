---
id: pfvduov4dlnmrwikm39lsne
title: Change of Basis
desc: ''
updated: 1736992219293
created: 1736675317856
nav_order: 3
---
## Why change basis?

Is there an ideal type of matrix that's the easiest to work with: that's trivially easy to multiply, to take exponents of, to add, etc., and that we can convert all matrices to? The answer is yes - diagonal matrices satisfy all those properties - and the central purpose of changing basis for linear maps is to express them through the lens of such an easily-workable matrix.

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **diagonal** matrix is a matrix $D$ with all elements not on its diagonal equal to zero: more precisely, we have $D = \{D_{ij}\}$ and $D_{ij} = 0$ whenever $i \neq j$. As such, $D$ will look something like this:
$$
D = \begin{bmatrix}
D_{11} & 0 & 0 & \dots & 0 \\
0 & D_{22} & 0 & \dots & 0 \\
0 & 0 & D_{33} & \dots & 0 \\
0 & 0 & 0 & \ddots & 0 \\
0 & 0 & 0 & \dots & D_{nn}
\end{bmatrix}
$$
> or, in Delta notation, we have $D = \{D_{ii} \delta_{ij}\}$ (not invoking suffix/summation convention).

> <span style="background-color: #ffb812; color: black;">Property</span>. Diagonal matrices are extremely convenient to work around in part because it is easy to take their exponents. For instance, we have
$$
(D^2)_{ij} = \sum_{k}D_{ii}\delta_{ik}D_{kk}\delta_{kj} = D_{ii}^2 \delta_{ij} ^2 = (D)_{ij}^2
$$
> or, in other words, we have
$$
D^2 = \begin{bmatrix}
D_{11}^2 & 0 & 0 & \dots & 0 \\
0 & D_{22}^2 & 0 & \dots & 0 \\
0 & 0 & D_{33}^2 & \dots & 0 \\
0 & 0 & 0 & \ddots & 0 \\
0 & 0 & 0 & \dots & D_{nn}^2
\end{bmatrix}
$$
> and similarly
$$
D^n = \begin{bmatrix}
D_{11}^n & 0 & 0 & \dots & 0 \\
0 & D_{22}^n & 0 & \dots & 0 \\
0 & 0 & D_{33}^n & \dots & 0 \\
0 & 0 & 0 & \ddots & 0 \\
0 & 0 & 0 & \dots & D_{nn}^n
\end{bmatrix}
$$
> for any positive integer $n$. As such, raising a diagonal matrix to a power is equal to simply raising all its elements to that power.

## Eigenvectors as a Change of Basis

Up until this point, we've made passing references and sly allusions to the fact that the matrix representation for a linear map $A$ is "in terms of the standard basis". If we want to change the basis for that matrix representation, do we change the linear map itself? 

The answer is no. The linear map itself does not change - if $(1,0)$ was mapped to $(4,3)$ before, so will it remain even after a change of basis. But what will change is the **matrix representation** of that linear map; and as we will see, some bases result in far simpler matrices than others.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Suppose that the linear map $A: \mathbb{F^n} \to \mathbb{F^n}$ has $n$ linearly independent eigenvectors $\mathbf{x_1, x_2, ..., x_n}$. Then using these eigenvectors as a basis for its matrix representation results in a diagonal matrix for $A$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. What we mean by a **change of basis** is as follows. Any vector $\mathbf{x} \in \mathbb{F}^n$ can be written in terms of a linear combination of the standard basis $(1,0,...,0),...,(0,...,0,1) = e_1, ..., e_n$. As previously defined, the matrix representation of a linear map $A$ in terms of the standard basis is
$$
\begin{bmatrix}
A(e_1) & A(e_2) & ... & A(e_n)
\end{bmatrix}
$$
> where the columns are $e_1, ..., e_n$ under transformation by $A$. If we instead use the basis of eigenvectors $\mathbf{x_1}, \mathbf{x_2}, ..., \mathbf{x_n}$, which span $\mathbb{F^n}$, we obtain the matrix representation
$$
\begin{bmatrix}
A(\mathbf{x}_1) & A(\mathbf{x}_2) & ... & A(\mathbf{x}_n)
\end{bmatrix}
$$
> which, as $A(\mathbf{x_i}) = \lambda_i \mathbf{x}_i$ by definition, yields
$$
\begin{bmatrix}
\lambda_1(\mathbf{x}_1) & \lambda_2(\mathbf{x}_2) & ... & \lambda_n(\mathbf{x}_n)
\end{bmatrix}
$$
> However, as we are using $\mathbf{x_1}, \mathbf{x_2}, ..., \mathbf{x_n}$ as our basis, each column must be expressed in terms of a linear combination of these vectors:
$$
\begin{cases}
\lambda_1\mathbf{x_1} = \lambda_1\mathbf{x_1} + 0\mathbf{x_2} + ... + 0\mathbf{x_n} \\
\lambda_2\mathbf{x_2} = 0\mathbf{x_1} + \lambda_2\mathbf{x_2} + ... + 0\mathbf{x_n} \\
\vdots
\end{cases}
$$
> This yields the matrix
$$
A = \begin{bmatrix}
\lambda_1 & 0 & 0 & ... & 0 \\
0 & \lambda_2 & 0 & ... & 0 \\
0 & 0 & \lambda_3 & ... & 0 \\
0 & 0 & 0 & \ddots & 0 \\
0 & 0 & 0 & \dots & \lambda_n
\end{bmatrix}
$$
> which is diagonal.

On a more intuitive level: the basis for a linear map is the "axes" on which it is acting; if we choose the standard basis, for instance, these axes are simply, in the case of $\mathbb{R}^3$, the x-, y-, and z-axis. Eigenvectors are vectors along which the linear map preserves direction; if you apply the linear map to its eigenvector, you get a constant multiple of that eigenvector. Thus, if you let the eigenvectors of the linear map be its axes, then all it does along each axis is scale that axis by a constant multiple - yielding a diagonal matrix, as above.

Such a change of basis - transforming an ordinarily complex matrix into a simple diagonal one - can be useful in the case of repeated applications of the linear map; as exponentiating a diagonal matrix is relatively painless, if we apply $A$ multiple times with eigenvectors as the basis, then our result should also be relatively simple.

## Change of Basis: The General Formula

Let's step outside the bounds of eigenvalues and eigenvectors, and consider the case where we want to change the basis of a linear map $A$ from **any** basis $\{\mathbf{e}_i\}$ of $\mathbb{F}^n$, $i=1,...,n$, to another basis $\{\mathbf{\tilde{e}}_i\}$ of $\mathbb{F}^n$, $i=1,...,n$ (with the funny little hat).

As displayed above, a change of basis from $\{e_i\}$ to $\{\tilde{e}_i\}$ is essentially rewriting a linear combination of $e_n$s
$$
\mathbf{x} = a_1e_1 + a_2e_2 + ... + a_n e_n
$$
to the linear combination of $\tilde{e}_n$s
$$
\mathbf{x} = b_1 \tilde{e}_1 + b_2 \tilde{e}_2 + ... + b_n \tilde{e}_n.
$$
(You can pinpoint the exact moment where the amount of shits I gave about bolding out all the vectors dropped irrevocably to zero.)

In the basis $\{e_i\}$, we have
$$
e_i = 0e_1 + 0e_2 + ... + 1e_i + ... + 0e_n
$$
for any $i = 1, 2, ..., n$; in matrix form, this can be written as
$$
\begin{bmatrix}
1 & 0 & ... & 0 \\
0 & 1 & ... & 0 \\
0 & 0 & \ddots & 0 \\
0 & 0 & ... & 1
\end{bmatrix}
\begin{bmatrix}
e_1 & e_2 & ... & e_n
\end{bmatrix}
= 
\begin{bmatrix}
e_1 & e_2 & ... & e_n
\end{bmatrix}
$$
where the first matrix is just the identity matrix. In this case, call the identity matrix the **transformation matrix** from the basis $\{e_i\}$ to the basis $\{e_i\}$; it represents what linear combinations you have to do to go from $e_i$ to $e_i$. (Never has the visceral urge to scream "no shit, Sherlock" at myself in front of the computer screen been so unbearably strong.) 

But what if we wanted to change our basis to $\{\tilde{e}_i\}$? Suppose, then, that
$$
\tilde{e}_j = \sum_{i=1}^{n} P_{ij}e_i
$$
for all $i = 0, 1, ..., n$, and some matrix of scalars $P = P_{ij} \in \mathbb{F}$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **transformation matrix** representing a change of basis from $\{e_i\}$ to $\{\tilde{e}_i\}$ is the matrix $P = \{P_{ij}\}$. Note that these $P_{ij}$ can always be found, as $e_i$ and $\tilde{e}_i$ span the same space.

If we write
$$
P = \begin{bmatrix}
P_{11} & P_{12} & ... & P_{1n} \\
P_{21} & P_{22} & ... & P_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
P_{n1} & P_{n2} & ... & P_{nn}
\end{bmatrix}
$$
we can observe that column $j$ represents the coefficients in the linear combinations for $\tilde{e}_j$, in terms of the basis $\{e_i\}$.

The same procedure can be applied in reverse to yield a transformation matrix $Q$, mapping from the basis $\{\tilde{e}_i\}$ back to $\{e_i\}$:

$$
Q = \begin{bmatrix}
Q_{11} & Q_{12} & ... & Q_{1n} \\
Q_{21} & Q_{22} & ... & Q_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
Q_{n1} & Q_{n2} & ... & Q_{nn}
\end{bmatrix}
$$
where we have
$$
e_j = \sum_{i=1}^n Q_{ij}\tilde{e}_i.
$$


> <span style="background-color: #ffb812; color: black;">Property</span>. $Q$ is the inverse of $P$: $PQ = QP = I$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Given the following:
$$
\begin{cases}
\tilde{e}_j = \sum_{i=1}^{n} P_{ij}e_i \\
e_j = \sum_{i=1}^n Q_{ij}\tilde{e}_i.
\end{cases}
$$
Substituting the first equation into the second yields
$$
e_j = \sum_{i=1}^n Q_{ij}(\sum_{k=1}^n P_{ki}e_k)
$$
or, in summation notation,
$$
e_j = Q_{ij}P_{ki}e_k
$$
However, we also have
$$
e_j = \sum_{k=1}^n \delta_{kj}e_k = \delta_{kj}e_k
$$
and so $Q_{ij}P_{ki} = P_{ki}Q_{ij} = \delta_{kj}$; however, $P_{ki}Q_{ij}$ equals $(PQ)_{kj}$, and so $(PQ)_{kj} = \delta_{kj}$ and $PQ = I$. The argument is equivalent for proving $QP = I$, and thus proving that $P = Q^{-1}$.

## Transformation laws

### Transforming the components of a vector from one basis to another

Suppose some vector $\mathbf{u} \in \mathbb{F}^n$ can be written in terms of a basis $\{e_i\}$ of $\mathbb{F}^n$, as follows:
$$
\mathbf{u} = \sum_{i=1}^n u_i e_i,
$$
or, in matrix form,
$$
\mathbf{u}_{\{e_i\}} = \begin{bmatrix}
u_1 \\
u_2 \\
\vdots \\
u_n
\end{bmatrix}
$$
If we instead want to express $\mathbf{u}$ through the basis $\{\tilde{e}_i\}$, i.e.
$$
\mathbf{u} = \sum_{i=1}^n \tilde{u}_i \tilde{e}_i,
$$
or, in matrix form,
$$
\mathbf{u_{\{\tilde{e}_i\}}} = \begin{bmatrix}
\tilde{u}_1 \\
\tilde{u}_2 \\
\vdots \\
\tilde{u}_n
\end{bmatrix}
$$
then using the entries of $P$ and $Q$ as above, we have
$$
e_i = Q_{ki}\tilde{e}_k
$$
using summation convention, and thus
$$
\mathbf{u} = Q_{ki} a_i \tilde{e}_k
$$
where $Q_{ki} a_i$ represents the vector $Q\mathbf{u}$. Thus: 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Transformation law for vector components**. The components of $\mathbf{u}$ in the basis $\{\tilde{e}_i\}$ are given by
$$
\mathbf{u}_{\{\tilde{e}_i\}} = Q\mathbf{u}_{\{e_i\}}.
$$
Conversely, $\tilde{\mathbf{u}} = P\mathbf{u}$ - i.e. the components of $\mathbf{u}$ in terms of $\tilde{e}_i$ is the components of $\mathbf{u}$ in terms of $e_i$, multiplied by the transformation matrix from $\tilde{e}_i$ to $e_i$ (on the left).

### Transforming the basis of a linear map
Consider a linear map $A: \mathbb{F^n} \to \mathbb{F^n}$ in which $\mathbf{u} \to \mathbf{u}' = A(\mathbf{u})$. Suppose that in the basis $\{e_i\}$, $\mathbf{u}$ and $\mathbf{u}'$ have vector components $\mathbf{u}_e$ and $\mathbf{u}'_{e}$ respectively, such that 
$$
\mathbf{u}'_e = A\mathbf{u}_e.
$$
Now suppose that we want to change the basis of $A$ to another basis of $\mathbb{F}^n$, which we call $\{\tilde{e_i}\}$. Suppose that in this basis, $\mathbf{u}$ and $\mathbf{u}'$ have vector components $\mathbf{u}_{\tilde{e}}$ and $\mathbf{u}'_{\tilde{e}}$ respectively, such that 
$$
\mathbf{u}'_{\tilde{e}} = A\mathbf{u}_{\tilde{e}}.
$$
Let $P$ be the transformation matrix from $e$ to $\tilde{e}$. Then, by the transformation laws for vector components above, we have
$$
\mathbf{u}'_{e} = P\mathbf{u}'_{\tilde{e}}
$$
and
$$
\mathbf{u}_{e} = P\mathbf{u}_{\tilde{e}}
$$
As such
$$
\mathbf{u}'_e = P\mathbf{u}'_{\tilde{e}} = AP\mathbf{u}_{\tilde{e}}
$$
which yields
$$
\mathbf{u}_{\tilde{e}}' = P^{-1}AP\mathbf{u}_{\tilde{e}}
$$
As the columns of the matrix representation of $A$ in terms of the basis $\tilde{e}$ is the components of $\tilde{e}_1, \tilde{e}_2, ..., \tilde{e}_n$ transformed by $A$, we conclude that 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Under a change of basis from $\{e_i\}$ to $\{\tilde{e}_i\}$ represented by a transformation matrix $P: \tilde{e}_i \to e_i$, the matrix representation of a linear map $A$, $A_{\tilde{e}}$, is given by
$$
A_{\tilde{e}}=P^{-1}A_eP.
$$
If instead $A$ was a linear map from $\mathbb{F}^n$ to $\mathbb{F}^m$, with bases $\{e_i\}$ and $\{f_i\}$ respectively, then a change of basis to $\{\tilde{e}_i\}$ and $\{\tilde{f}_i\}$ (spanning $\mathbb{F}^n$ and $\mathbb{F^m}$) works in a largely similar manner. Suppose that $P$ is the transformation matrix from $e \to \tilde{e}$, and $S$ from $f \to \tilde{f}$. Then if
$$
\mathbf{u}'_{\tilde{f}} = A_{\tilde{e},\tilde{f}}\mathbf{u}_{\tilde{e}}
$$
under bases $\tilde{e}, \tilde{f}$, we have
$$
S\mathbf{u}'_{\tilde{f}} = \mathbf{u}'_{f} = A_{e, f} \mathbf{u}_{e} = A_{e, f} P \mathbf{u}_{\tilde{e}}
$$
and so
$$
S\mathbf{u}'_{\tilde{f}} = A_{e, f} P \mathbf{u}_{\tilde{e}}
$$
yielding
$$
\mathbf{u}'_{\tilde{f}} = S^{-1}A_{e, f} P \mathbf{u}_{\tilde{e}}.
$$

