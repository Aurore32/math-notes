---
id: 8r1kh8kplkgwdnntxbb67zt
title: Suffix Notation and Tensors
desc: ''
updated: 1734762207965
created: 1734760849916
---
> <span style="background-color: #12ffd7; color: black;">Notation</span> (Suffix notation). For vectors $\mathbf{v}$, the suffix $\mathbf{v}_i$ is understood to be the $i$th component of $\mathbf{v}$; this enables us to convert vector equations to scalar form, e.g. $\mathbf{a=\lambda b}$ for two vectors can be written $\mathbf{a_i=\lambda b_i}$. <br/><br/>
Building on this, we introduce a notation that allows us to remove the summation symbol in equations such as e.g. $\mathbf{a\cdot b}=\sum a_i b_i$. We simply write, for instance, $\mathbf{a \cdot b} = a_i b_i$; if the suffix $i$ is repeated twice in a term, that means "sum over $i$" - $a_i b_i$ is understood to be $\sum_{i=1}^n a_i b_i$, $x_k y_k z_c$ is understood to be summing over $k$ and not $c$, etc. If a suffix appears only once in a term (e.g. $a_{ij}b_{jk}$, for $i$ and $k$), they are not summed over.

The last example - $a_{ij}b_{jk}$ - is an example of *tensors*, an important class of mathematical object prevalent in linear algebra:

> <span style="background-color: #03cafc; color: black;">Definition</span> (Tensors). Tensors are items with more than one index: for instance, $a_{ij}$ or $b_{ijk}$. They may represent entries in a matrix, or other things entirely. For instance:

> <span style="background-color: #03cafc; color: black;">Defintion</span> (Kronecker delta). Define the tensor $\delta_{ij}$ to be such that 
$$
\begin{cases}
\delta_{ij}=1,\ i =j \\
0 \text{ otherwise}
\end{cases}
$$
If the Kronecker delta represents the entries of a matrix, then that matrix is zero for $i\neq j$ (entries not on the diagonal) and one for $i = j$ (on the diagonal). Thus, the matrix represented by the Kronecker delta is an identity matrix.

The Kronecker delta can often be useful in writing suffix notation for vector sums; if it is present in a sum, it will eliminate the terms with unequal suffixes and leave only the terms with equal suffixes. For instance:
1. $a_i \delta_{ij} = a_j$ (note that this is a sum, not a single term; we are summing over $i$ per the above notation)
2. $a_p \delta_{pq} b_q = a_p b_p$ summing over both $p$ and $q$. This expression looks confusing, but remember that $a_p b_p$ denotes a sum over $p$, not a single term.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Alternating symbol). For numbers $(i,j,k)$, define an **even permutation** as a permutation of $(i, j, k)$ that can be reached with an even number of swaps of its elements (zero or two swaps): $(i, j, k)$ itself (zero swaps), $(k,i,j)$, $(j,k,i)$. Define an **odd permutation** analogously as a permutation that can be reached with an odd number of swaps (one swap): $(i,k,j)$, $(j,i,k)$, $(k,j,i)$. Thus define $\epsilon_{ijk}$, the **alternating symbol**, as
$$
\begin{cases}
\epsilon_{ijk}=1, \text{ $(i,j,k)$ is an even permutation} \\
\epsilon_{ijk}=-1, \text{ $(i,j,k)$ is an odd permutation} \\
\text{0 otherwise (repeated suffixes)}
\end{cases}
$$
For instance, $\epsilon_{231}=1$ and $\epsilon_{213}=-1$. $\epsilon_{112}=0$ as it is not a valid permutation.