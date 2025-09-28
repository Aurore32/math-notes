
## Matrices

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **matrix** is an array of elements; if $A$ is a $n \times m$ matrix for positive integers $n$, $m$, it has $n$ rows and $m$ columns. The notation $A_{ij}$ denotes the element of the matrix in the $i$th row and $j$th column; occasionally we write $A = {A_{ij}}$.


$$

A=\begin{bmatrix}
A_{11} & A_{12} & ... & A_{1m} \\
A_{21} & A_{22} & ... & A_{2m} \\
\vdots & \vdots & \ddots & \vdots \\
A_{n1} & A_{n2} & ... & A_{nm}
\end{bmatrix}
$$

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define **scalar multiplication** of matrices as follows, where $\lambda \in R$ and $A$ is a matrix: $\lambda A$ is simply $\{\lambda A_{ij}\}$, or

$$

\lambda A=\begin{bmatrix}
\lambda A_{11} & \lambda A_{12} & ... & \lambda A_{1m} \\
\lambda A_{21} & \lambda A_{22} & ... & \lambda A_{2m} \\
\vdots & \vdots & \ddots & \vdots \\
\lambda A_{n1} & \lambda A_{n2} & ... & \lambda A_{nm}
\end{bmatrix}
$$


> <span style="background-color: #03cafc; color: black;">Definition</span>. Define **matrix multiplication** as follows:
1. Matrix multiplication is only valid between a $n \times m$ matrix and a $m \times p$ matrix for any positive integers $n$, $m$, $p$: the number of columns of the first matrix must match the number of rows of the second.
2. Let $A$ be a $n\times m$ matrix and $B$ be $m \times p$; write $C$ as the matrix resulting from the multiplication $AB$. Then $C$ has dimensions $n \times p$, and $C_{ij} = \sum_{k=1}^{m} A_{ik}B_{kj}$. Alternatively, it is sum of the product of the elements of the $i$th row of $A$ and the $j$th column of $B$ (which have the same length, as we insisted).

Note that matrix multiplication often does not satisfy commutativity: $AB \neq BA$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define **matrix addition** between two matrices $A$ and $B$ **of the same size** as the matrix formed out of the sums of their elements:
$$
(A+B)_{ij} = A_{ij}+B_{ij}
$$

## Linear maps

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $A$, $B$ be sets. A **map** $T$ (not necessarily linear) from $A$ to $B$ assigns each element $x \in A$ a unique $x' \in B$. We write
$$
T: A \to B \text{ and/or } x\to x' = T(x)
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. $A$ is the **domain** of $T$, $B$ the **range** (codomain), $T(x)=x'$ the **image** of $x$ under $T$, and $A \to T(A)$ is the **image of $A$** under $T$ (i.e. the entire set $A$ transformed to $T(A)$). 

While it is true that $T(A)$ is a subset of $B$, $B$ may have elements that are not in $T(A)$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. (**Linear maps**). Let $V$ and $W$ be real vector spaces ($\mathbb{R^n}$ and $\mathbb{R^m}$ respectively). $T$ is a **linear map** from $V$ to $W$ if it satisfies the following properties:
1. $T(\mathbf{a+b}) = T(\mathbf{a}) + T(\mathbf{b})$, for vectors $\mathbf{a, b}\in \mathbb{R^n}$. (Linearity)
2. $T(\lambda \mathbf{a})=\lambda T(\mathbf{a})$ for a scalar $\lambda \in \mathbb{R}$. (Scalar multiplicity)

Combined together, we have $T(\lambda \mathbf{a} + \mu \mathbf{b})=\lambda T(\mathbf{a})+ \mu T(\mathbf{b})$: $T$ can be distributed across a linear combination.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $T(V)$ is a subspace of $W$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. By the above properties, $T(V)$ is a subset of $W$ and is closed under any linear combinations. Thus it is a subspace by definition.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. For **any** linear map $T$, $T(\mathbf{0}) = 0$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We do a little functional manipulation: (that's what my therapist used to say to me)
$$
\begin{aligned}
T(\mathbf{a + 0}) &= T(\mathbf{a}) + T(\mathbf{0}) \text{ by the above properties} \\
T(\mathbf{a}) &= T(\mathbf{a}) + T(\mathbf{0}) \\
T(\mathbf{0}) &= 0
\end{aligned}
$$
However, it is not necessarily true that if $T(\mathbf{b}) = 0$, then $\mathbf{b} = 0$.

> Insert random linear map joke here 
