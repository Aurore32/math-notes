> <span style="background-color: #03cafc; color: black;">Definition</span>. Using the permutation sign and the precedent of the $3\times 3$ determinant, define the determinant of a $n \times n$ matrix $A$ as 
$$
\det A = \epsilon_{j_1 j_2 ... j_n}A_{j_1 1} A_{j_2 2} ... A_{j_n n}
$$
> corresponding to the $3\times 3$ and $2\times 2$ determinants. The epsilon sign is only nonzero when $j_1, j_2, ..., j_n$ are all chosen to be distinct, i.e. they are a permutation of $\{1,2,...,n\}$. As such, we can also rewrite the above as

$$
\det A = \sum_{\sigma(n)}\epsilon(\sigma(n))A_{\sigma(1) 1}A_{\sigma(2) 2} ... A_{\sigma(n) n}
$$
> summing over all possible permutations $\sigma(n)$ of $\{1,2,3,...,n\}$.

> <span style="background-color: #ffb812; color: black;">Property</span>. For any square matrix $A$, $\det A = \det A^T$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We have
$$
\det A^T = \sum_{\sigma(n)}\epsilon(\sigma(n))A_{1 \sigma(1)}A_{2 \sigma(2)} ... A_{n \sigma(n)}
$$
> with subscripts reversed from $\det A$. For every permutation $\sigma(n)$, the product $A_{1\sigma(1)}A_{2\sigma(2)}...A_{n\sigma(n)}$ is equivalent to $A_{\rho(1) 1}A_{\rho(2) 2}...A_{\rho(n) n}$, as it is simply a rearrangement of the order of the terms. Thus, $\det A^T = \det A$. (For instance, we could choose the permutation $\sigma(\sigma^{-1}(n))$.)

> <span style="background-color: #ffb812; color: black;">Property</span>. Let $A'$ be the square matrix $A$ with a **single** row or column multiplied by a scalar $\lambda$. Then $\det A' = \lambda \det A$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. As $\det A = \det A'$, it suffices to prove this property for rows. Suppose that row $j$ for $j \in \{1,2,...,n\}$ is multiplied by $\lambda$. Then 

$$
\det A' = \sum_{\sigma(n)}\epsilon(\sigma(n))A_{1 \sigma(1)}A_{2 \sigma(2)} ... (\lambda A_{j \sigma(j)}) ... A_{n \sigma(n)}
$$
> which is equal to $\lambda \det A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. Following from the above, $\det(\lambda A)=\lambda^n \det A$ for a $n\times n$ matrix $A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. If $A'$ is $A$ with two rows or columns interchanged, then $\det A' = - \det A$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Suppose that rows $i$ and $j$ are swapped, with $i < j$; once again, due to $\det A = \det A^T$, it suffices to prove this property for rows. Then we have
$$
\det A' = \sum_{\sigma(n)}\epsilon(\sigma(n))A'_{1 \sigma(1)}A'_{2 \sigma(2)} ... (A'_{i\sigma(i)})...(A'_{j\sigma(j)})...A'_{n\sigma(n)}
$$
> All the other $A'$s are left unchanged except $A'_{i\sigma(i)}$, which becomes $A_{j\sigma(i)}$ (and vice versa), so we have
$$
\det A' = \sum_{\sigma(n)}\epsilon(\sigma(n))A_{1\sigma(1)}A_{2\sigma(2)}...A_{i\sigma(j)}...A_{j\sigma(i)}...A_{n\sigma (n)}
$$
> Let the permutation $\{\sigma(1), \sigma(2),..,\sigma(j),...\sigma(i),...\sigma(n)\}$ be denoted $\sigma'$. $\sigma'$ is equal to $\sigma$ with one transposition ($\sigma(i) \to \sigma(j)$), and so $\epsilon(\sigma')=(-)\epsilon(\sigma)$. Thus $\det A' = \sum \epsilon(\sigma') ... = - \det A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. Following from the above, if $A$ has two identical rows or columns, $\det A = 0$ because swapping the identical rows results in $\det A' = \det A = - \det A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. If $A'$ is $A$ with a scalar multiple of one row added to another row (or a scalar multiple of one column added to another column), then $\det A' = \det A$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let row $r$ multiplied by a scalar $\lambda$ be added to row $s$ with $r \neq s$. By the above, we have
$$
\begin{cases}
A'_{ij}=A_{ij},\ i \neq s \\
A'_{ij} = A_{ij} + \lambda A_{rj},\ i = s
\end{cases}
$$
> and as such
$$
\begin{aligned}
\det A' &= \sum_{\sigma(n)}A_{1\sigma(1)}...(A_{s\sigma(s)}+\lambda A_{r\sigma(s)})...A_{n\sigma (n)} \\ 
&= \det A + \lambda\sum_{\sigma(n)}A_{1\sigma(1)}...(A_{r\sigma(r)}A_{r\sigma(s)})...A_{n\sigma (n)}
\end{aligned}
$$
> where the latter term is the determinant of a matrix which has two identical rows $A_r$ and $A_r$, and thus zero according to the above properties. Therefore $\det A' = \det A$.

> <span style="background-color: #ffb812; color: black;">Property</span>. If the rows or columns of $A$ are linearly dependent, then $\det A = 0$. 