---
id: ixvynw05twlgbw1og9o09jc
title: Matrices as Linear Maps
desc: ''
updated: 1735372189451
created: 1735372184694
nav_order: 3
---

## Matrices as linear maps

Suppose $T$ is a linear map from $V$ to $W$, each with basis $\{\mathbf{v_i}\}$ ($i = 1, ..., n$) and $\{\mathbf{w_j}\}$ ($j=1, ..., m$).

Consider the set of vectors that $\mathbf{v_i}$ maps to under $T$: $\{T(\mathbf{v_i})\}.$ As shown above, this set spans the image $T(V)$; furthermore, as $T(\mathbf{v_i}) \in W$, every $T(\mathbf{v_i})$ can be written uniquely as the linear combination
$$
T(\mathbf{v_i}) = \sum_{i=1}^{m} A_{ij} \mathbf{w}_i
$$
by definition of a basis. It thus follows that for any general $\mathbf{x} = \sum_{j=1}^{n} x_i \mathbf{v}_i \in V$, we have 
$$
T(\mathbf{x}) = \sum_{j=1}^{n} \mathbf{x}_i \sum_{i=1}^{m} A_{ij} \mathbf{w}_i
$$
and thus
$$
T(\mathbf{x}) = \sum_{i=1}^{m} (\sum_{j=1}^{n} x_i A_{ij}) \mathbf{w}_i
$$
by swapping order of summation.
> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **matrix** of the linear map $T$ as $\{A_{ij}\}$. 

As the above equations hold for any $\mathbf{x} \in V$, the matrix of $T$ - uniquely defined, by definition of a basis - is sufficient for determining all the mappings of $T$. 

> <span style="background-color: #ffb812; color: black;">Proposition</span>. First notice that $T(\mathbf{x})$ as defined above is equivalent to writing $T(\mathbf{x}) = \mathbf{x}' = \mathbf{x}'_i \mathbf{w}_i$, where $\mathbf{x}_i' = \sum_{j=1}^{n} A_{ij} x_j$. Thus we have
$$
\begin{aligned}
\mathbf{x}' &= \begin{bmatrix}
\mathbf{x}'_1 \\
\mathbf{x}'_2 \\
\vdots \\
\mathbf{x}'_n
\end{bmatrix}
\end{aligned} = \begin{bmatrix}
A_{1j}\mathbf{x}_j \\
A_{2j}\mathbf{x}_j \\
\vdots \\
A_{nj}\mathbf{x}_j
\end{bmatrix} = A\mathbf{x}
$$
> by the definition of matrix multiplication found above. Therefore, the linear map $\mathbf{x} \to \mathbf{x}': T$ can be written in **matrix form** as $\mathbf{x}' = A\mathbf{x}$. Note that $A$ is a $m \times n$ matrix.

> <span style="background-color: #bc42f5; color: black;">Observation</span>. $V$ and $W$ are not restricted to a single basis; when different bases are used, the matrix form of $T$ will be different. It is sometimes necessary to specify which two bases $T$ is mapping between: $\{v_i\} \to \{w_i\}$.

> <span style="background-color: #bc42f5; color: black;">Observation</span>. If we take the basis $\{w_i\}$ to be the standard basis $\{(1,0,...,0), (0,1,...,0), ..., (0,0,...,1)\}$ of $\mathbb{R}^m$, we have
$$
T(\mathbf{v}_i)=\begin{bmatrix}
A_{1i} \\
A_{2i} \\
\vdots \\
A_{mi}
\end{bmatrix}
$$
> which is the $i$th column of the matrix form of $T$. 

The crucial takeaway from this section is that matrices are a way to **express linear maps**; everything, from the definition of matrix multiplication to all the operations we will see in the following section, is derived from this fact.