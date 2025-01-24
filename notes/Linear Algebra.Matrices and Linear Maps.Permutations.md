---
id: kzc5fzc65b83qv97lrkuqff
title: Permutations
desc: ''
updated: 1736072951770
created: 1735611406974
nav_order: 7
---
## Permutation notation

Permutations are ways to arrange the order of $n$ distinct objects without stealing one of them, eating one of them, trying to make your newborn son blend in among them, or otherwise changing them in any way. They contain many of the most shocking results in mathematics; for instance, do you know how many distinct permutations the list $\{1,2,3,...,25\}$ has? only 25!

> <span style="background-color: #03cafc; color: black;">Disclaimer</span>. No, the factorial jokes do not get better from this point onwards.

> <span style="background-color: #bc42f5; color: black;">Notation</span>. Let $\rho$ be a permutation of the set $\{1,2,3,...,n\}$, such that the number in position 1 is $\rho(1)$, position 2 is $\rho(2)$, and so on. Then we write
$$
\rho = 
\begin{bmatrix}
1 & 2 & ... & n \\
\rho(1) & \rho(2) & ... & \rho(n)
\end{bmatrix}
$$
> where the order of the columns do not matter.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **inverse** of $\rho$ as 
$$
\rho^{-1} = 
\begin{bmatrix}
\rho(1) & \rho(2) & ... & \rho(n) \\
1 & 2 & ... & n
\end{bmatrix}
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. Define a **fixed point** $k \in \{1,2,...,n\}$ as a point where $\rho(k) = k$; it is unchanged by the permutation.

When these absurdly unsubstantiated definitions start coming, they don't stop coming. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Two permutations are **disjoint** if a point moved by one permutation is fixed by the other permutation; no point is moved by both permutations. In otherwords, if for permutations $\rho_1$ and $\rho_2$, $\rho_1(k)\neq  k$ implies $\rho_2(k) = k$ and vice versa, the two permutations are disjoint.

For instance, the permutations
$$
\rho_1=\begin{bmatrix}
1 & 2 & 3 \\
3 & 1 & 2
\end{bmatrix}
$$
and 
$$
\rho_2=\begin{bmatrix}
4 & 5 & 6 \\
6 & 4 & 5
\end{bmatrix}
$$
are disjoint over $\{1,2,3,4,5,6\}$ as they do not ever move the same number.

> <span style="background-color: #ffb812; color: black;">Property</span>. Disjoint permutations are commutative; $\rho_1 \rho_2 = \rho_2 \rho_1$. This can be intuitively felt, as they do not apply to the same numbers, meaning that applying them in any order yields the same result.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Cycles** of length $q$ ("q-cycles") refer to the permutation
$$
\rho_q  = \begin{bmatrix}
a_1 & a_2 & a_3 & ... & a_{q-1} & a_q \\
a_2 & a_3 & a_4 & ... & a_{q} & a_1
\end{bmatrix}
$$
> In other words, the top row is shifted to the left by one unit. We also denote this cycle by $(a_1, a_2, ..., a_q)$.


> <span style="background-color: #03cafc; color: black;">Definition</span>. A **transposition** is a 2-cycle $(a_1,a_2)$ that acts simply to swap the positions of $a_1$ and $a_2$. A transposition is its own inverse.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **The standard representation**. Any permutation can be written as a product of disjoint cycles, or a product of transpositions; this simply expresses the notion that you can arrange a list of items in any order by swapping the positions of elements one pair of a time. 

Note that such a representation is non-unique.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **sign** of a permutation as corresponding to the number of transpositions required to express it; if $\rho$ is a product of $r$ transpositions (i.e. we need $r$ swaps to bring about $\rho$), then the sign of $\rho$, $\epsilon(\rho)$, is defined to be $(-)^r$.

> <span style="background-color: #ffb812; color: black;">Property</span>. It follows that for permutations $\rho, \sigma$, $\epsilon(\rho\sigma)=\epsilon(\rho)\epsilon(\sigma)$ and $\epsilon(\rho^{-1})=\epsilon(\rho)$, as inverses simply reverse the permutation with the same amount of steps.

> <span style="background-color: #03cafc; color: black;">Definition</span>.  **Generalized $\epsilon$ Symbol**, or the **Levi-Civita Symbol**. If $(j_1,j_2,...,j_n)$ is a permutation, define $\epsilon_{(j_1,j_2,...,j_n)}$ as the sign of the permutation; otherwise, it is zero.

