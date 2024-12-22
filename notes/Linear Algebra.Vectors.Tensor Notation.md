---
id: 8r1kh8kplkgwdnntxbb67zt
title: Tensor Notation
desc: ''
updated: 1734854545968
created: 1734760849916
nav_order: 7
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

We can use these tensors to simplify a few proofs:

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $(\mathbf{a\times b})_i=\epsilon_{ijk}a_j b_k$ (note the suffix notation here: $j$ and $k$ are both present twice and are thus summed over, while $i$ is present once and is thus fixed). 

> <span style="background-color: #1eff12; color: black;">Proof</span>.
$$
\begin{aligned}
\mathbf{a \times b} &= \begin{vmatrix} i & j & k \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{vmatrix} \\
&= (a_2b_3-a_3b_2)i-(a_1b_3-a_3b_1)j+(a_1b_2-a_2b_1)k \\
&= \begin{bmatrix} 
a_2b_3-a_3b_2 \\
a_1b_3-a_3b_1 \\
a_1b_2-a_2b_1
\end{bmatrix}
\end{aligned}
$$
> As such, we can write $(\mathbf{a\times b})_1 = a_2b_3-a_3b_2=\epsilon_{123}a_2b_3+\epsilon_{132}a_3b_2$, with the terms containing $j$ and $k$ not equal to 2 or 3 in any order evaluating to zero by the definition of $\epsilon$. Examining the other two terms demonstrates the validity of the statement. $\square$

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. $\epsilon_{ijk}\epsilon_{ipq}=\delta_{jp}\delta_{kq}-\delta_{jq}\delta_{kp}$ where $\delta$ denotes the Kronecker delta.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $\mathbf{a\cdot (b\times c)=b\cdot (c\times a)}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Using the previous proposition, we have $\mathbf{(b \times c)}_i=\epsilon_{ijk}b_j c_k$ and thus the dot product $\mathbf{a} \cdot \mathbf{(b \times c)} = \epsilon_{ijk}a_i b_j c_k$. On the other hand, $\mathbf{b\cdot (c\times a)} = \epsilon_{ijk}b_i c_j a_k = \epsilon_{ijk}a_k b_i c_j = \epsilon_{kij}a_i b_j c_k$ as all of $i$, $j$, $k$ are simply dummy subscripts that can be replaced by other variables. $\epsilon_{kij}$ represents the permutation $(k,i,j)$, which is two swaps away from $(i,j,k)$ and thus $\epsilon_{kij}=\epsilon_{ijk}$. $\square$

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $\mathbf{a\times(b\times c) = (a\cdot c)b - (a\cdot b)c}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We have $\mathbf{b\times c} = \begin{bmatrix}\epsilon_{1jk}b_j c_k \\ \epsilon_{2jk}b_j c_k \\ \epsilon_{3jk}b_j c_k\end{bmatrix}$. Thus, we have 
$$
\begin{aligned}
\mathbf{(a\times (b\times c))}_i &= \epsilon_{ijk}a_j(\mathbf{b\times c})_k \\
&= \epsilon_{ijk}a_j\epsilon_{kpq}b_pc_q
\end{aligned}
$$
> Using the above theorem, we have
$$
\begin{aligned}
\epsilon_{ijk}a_j\epsilon_{kpq}b_pc_q &= \epsilon_{kij}\epsilon_{kpq}a_jb_pc_q \\
&= (\delta_{ip}\delta_{jq}-\delta_{iq}\delta_{jp})a_j b_p c_q \\
&= a_j b_i c_j - a_j b_j c_i
\end{aligned}
$$
as the $\delta$ terms are only nonzero when $p=i, q=j$ and when $q=i, p=j$ respectively. Note that this is the $i$th term and $i$ is fixed; both terms are a sum over $j$. By the definition of the dot product, this is thus $\mathbf{(a\cdot c)b_i - (a\cdot b)c_i}$. $\square$

> <span style="background-color: #ffb812; color: black;">Proposition</span> (Spherical geometry). $\mathbf{(a\times b)\cdot (a\times c)= (a\cdot a)(b\cdot c)-(a\cdot b)(a\cdot c)}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. The left-hand side can be expanded in scalar form as
$$
\begin{aligned}
\mathbf{(a\times b)\cdot (a\times c)} &= (\epsilon_{ijk}a_jb_k)(\epsilon_{ipq}a_p c_q) \\
&= \epsilon_{ijk} \epsilon_{ipq} a_j b_k a_p c_q \\
&= (\delta_{jp}\delta_{kq} - \delta_{jq}\delta_{kp})a_jb_ka_pc_q \\
&=a_j^2 b_k c_k - a_ja_kb_kc_j
\end{aligned}
$$
> The right-hand side can be expanded in scalar form as
$$
\begin{aligned}
\mathbf{(a\cdot a)(b\cdot c)-(a\cdot b)(a\cdot c)} &= (a_i a_i)(b_j c_j) - (a_i b_i)(a_j c_j) \\
&=a_j^2 b_k c_k - a_j a_k b_k c_j
\end{aligned}
$$
> And thus the two expressions are equal. $\square$

