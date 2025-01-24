---
id: i4nj9v4ltupnjuomf6c7vda
title: Rank and Nullity
desc: ''
updated: 1735372160232
created: 1735372160232
nav_order: 2
---

## Rank, Kernel and Nullity

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **rank** of a linear map $T: V \to W$ is the dimension of the image: $r(T) = \dim T(V)$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **kernel** or **null-space** of a linear map is the set of all vectors $\mathbf{v} \in V$ such that $T(\mathbf{v}) = 0$: essentially, it is the "zeroes" of the linear map. Denote the kernel as $K(T) = \{v \in V: T(v) = 0\}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. $K(T)$ is a subspace of $V$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. For any two elements $\mathbf{a,b}\in K(T)$, we have:
1. $T(a+b)=T(a)+T(b)=0+0$, and as such $a+b\in K(T)$ by definition.
2. $T(\lambda a) = \lambda T(a) = \lambda \times 0 = 0$, and as such $\lambda a \in K(T)$.
3. $\mathbf{0} \in K(T)$ because $T(0)=0$ for any $T$. Thus $K(T)$ is closed under linear combinations and is a subspace of $V$ by definition.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **nullity** of $T$ is the dimension of the kernel: $n(T) = \dim K(T)$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. (**Rank-Nullity Theorem**). ~~First proposed by famous mathematicians John Rank and Joe Nullity in 1869.~~ <br/><br/>
For any linear map $T$, we have:
$$
r(T) + n(T) = \dim V
$$
> or: the rank and the nullity of $T$ sum to the dimension of its domain. (This is personal for me, because $\dim T$ used to be my nickname in high school.)

> <span style="background-color: #1eff12; color: black;">Proof</span>. ~~Left as an exercise to the reader.~~ (Actually, not really. I have way too much free time on my hands, so I'll do it now.)<br/><br/>
Let $\dim V = n$ and $n(T) = m$, with $m \leq n$ as the null space is a subspace of the domain. We will discuss the following two cases to prove the theorem.<br/><br/>
**Case 1: $n=m$.** Then the null space of $T$ and the domain of $T$ are the same vector space; both vector spaces are real vector spaces, and if they have the same dimension, then they are necessarily both $\mathbb{R}^n = \mathbb{R}^m$. Thus inputting any vector $\mathbf{x}$ into $T$ gives 0, and the rank of $T$ is 0, as the image of $T$ only contains $\{0\}$.<br/><br/>
**Case 2: $n>m$**. Let $\{e_1, e_2, ..., e_m\}$ be the basis of the null space. As they are a linearly independent set of vectors, we can extend the basis to $\{e_1, e_2, ..., e_m, e_{m+1}, ..., e_n\}$: a set of $n$ vectors, all linearly independent. The details of this extension are as follows.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. (The **extension lemma**). Let $L = \{e_1, e_2, ..., e_m\}$ be a set of $m$ linearly independent vectors in $V$ with $\dim V = n \geq m$, and some basis $\{v_1, v_2, ..., v_n\}$. Then a basis of $V$ can be constructed which contains $L$, as follows:
1. Begin with $L$.
2. For every $i = 1, 2, ..., n$: if $v_i \in \text{span}(L)$, keep $L$ as is. Otherwise, addd $v_i$ to the set $L$.
<br/><br/>
We claim that $L$ is both linearly independent and spans $V$. <br/><br/>
First, linear independence: at every step, we ensure that the linear independence of $L$ is preserved because $v_i$ is only added to $L$ if it lies outside the span of $L$. <br/><br/>
Second, $L$ spans $V$; every time a $v_i$ is added to $L$ for $i = 1, 2, ..., n$ (Step 2), $v_i$ is in the span of $L$ because either (1) it already was before adding $v_i$ to $L$, or (2) if it wasn't, $v_i$ is added to $L$. Thus, as $\{v_1, v_2, ..., v_n\}$ forms a basis of $V$ and $L$ spans all $v_i$, $L$ spans $V$.

> As previously proven, any set of linearly independent vectors of length $n$ forms a basis for $V$ (a vector space with dimension $n$). <br/><br/>
In order to prove that $r(T) = \dim V - n(T) = n - m$, we need to prove that a set of $n-m$ linearly independent vectors spans the image of $T$. <br/><br/>
**Claim.** $\{T(e_{m+1}), T(e_{m+2}), ..., T(e_n)\}$ is such a set. We will first demonstrate that it spans $T(V)$, then demonstrate that it is linearly independent. <br/><br/>
**Span**. First, as $\{e_1, e_2, ..., e_m, ..., e_n\}$ is a basis of $V$, any $v \in V$ can be written as some linear combination $a_i e_i$. Thus any $T(v) \in T(V)$ can be written
$$
\begin{aligned}
T(a_i e_i) &= a_i T(e_i) \\
 &= a_1T(e_1) + ... + a_m T(e_m) + a_{m+1}T(e_{m+1}) ... + a_nT(e_n)
\end{aligned}
$$
> Where every term from $a_1T(e_1)$ to $a_mT(e_m)$ is zero because $e_1, ..., e_m$ lie in the null space of $T$. Thus, $T(v)$ is a linear combination of $T(e_{m+1}), ..., T(e_n)$. <br/><br/>
**Linear independence**. Suppose for the sake of contradiction that some linear combination 
$$
a_{m+1} T(e_{m+1}) + a_{m+2} T(e_{m+2}) + ... + a_n T(e_n)
$$
> equals zero. Then by the definition of a linear map, we have
$$
T(a_{m+1}e_{m+1} + a_{m+2} e_{m+2} + ... + a_n e_n) = 0
$$
> Or, in other words, the vector $v = a_{m+1} e_{m+1} + ... + a_n e_n$ lies in the null space of $T$. Thus, as $\{e_1, ..., e_m\}$ span the null space of $T$, there exist some $a_1, ..., a_m$ such that

$$
a_{m+1} e_{m+1} + ... + a_n e_n = a_1 e_1 + ... + a_m e_m
$$
> which implies
$$
a_1 e_1 + ... + a_m e_m - a_{m+1} e_{m+1} - ... - a_{n}e_n = 0 
$$
> i.e. that $e_1, ..., e_{n}$ are not linearly independent. This forms a contradiction with the fact that these vectors form a basis for $V$.

---

> <span style="background-color: #ffb812; color: black;">Proposition</span>. If ${e_1, e_2, ..., e_n}$ is a basis for $V$, then the image of the linear map $T: V \to W$, $T(V)$, is spanned by $T(e_1), T(e_2), ..., T(e_n)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. By definition, every vector $v \in V$ can be written as a linear combination of the $e_i$s. Thus $T(v)=T(a_1e_1 + a_2e_2 + ... + a_ne_n)$ for some scalars $a_1, a_2, ..., a_n$, and by the properties of a linear map, the right-hand side results in $a_1 T(e_1) + a_2 T(e_2) + ... + a_n T(e_n)$. Thus, every possible $T(v)$ can be written as a linear combination of $T(e_1)$, $T(e_2)$, ..., $T(e_n)$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span> (**Existence and uniqueness**).  If $\{\mathbf{e_j}\}$ ($j = 1, 2, ..., n$) is a basis of $V$, and $\{\mathbf{w_j}\}$ ($j=1,2,...,n$) is a set of $n$ vectors in $W$, then there is a unique linear map $T$ mapping $\{\mathbf{e_j}\}$ to $\{\mathbf{w_j}\}$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. **Existence**. Define the linear map $T: V \to W$ as $T(c_j e_j) = c_j w_j$ (using suffix notation), for any scalars $c_1, ..., c_n$. Then $T(e_j) = w_j$ for any $j$, as shown by setting $c_j = 1$ and all other $c_i = 0$, and the domain of T covers the entirety of $V$ as $\{e_j\}$ form a basis. Thus, $T$ satisfies the desired properties. <br/><br/>
It may also be verified that $T$ is closed under linear combinations:

$$
\begin{aligned}
T(c_1 v_1 + c_2 v_2) \text{ for any $v_1, v_2 \in V$ and $c_1, c_2 \in R$} \\
= T(c_1\sum_{i=1}^{n} a_i e_i + c_2\sum_{i=1}^{n} b_i e_i) \text{ for some $a_i, b_i$} \\
= T(\sum_{i=1}^{n} (c_1a_i + c_2b_i)e_i) \\
= \sum_{i=1}^{n} (c_1a_i + c_2b_i)w_i \text{ by definition} \\
= c_1\sum_{i=1}^{n} a_i w_i + c_2 \sum_{i=1}^{n} b_i w_i \\
= c_1T(v_1) + c_2 T(v_2) \text{ by definition}
\end{aligned}
$$
> where Step 2 is due to $\{e_i\}$ being a basis. Thus, as $T$ is closed under linear combinations and the domain of $T$ is $V$ (and $T(0)=0$), $T$ is a linear map from $V$ to $W$ that satisfy the given properties.

> **Uniqueness**. Suppose another linear map $S \neq T$ exists that maps $e_j$ to $w_j$. Then $S(e_j)=w_j$; by the definition of a linear map, for scalars $c_j$ we have $c_jS(e_j) = c_jw_j$ and thus, $S(c_j e_j)=c_jw_j$ using suffix notation. This matches the original definition of $T$, and so $S = T$, reaching a contradiction. Therefore $T$ is the unique linear map that maps $e_j$ to $w_j$ in $\text{span}(e_1, e_2, ..., e_n)$, and as the $e_j$s span $V$, $T$ is unique in $V$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Let $\mathcal{L}(V,W)$ denote all linear maps from $V \to W$. Then $\mathcal{L}(V,W)$ is a vector space, under the following definitions of addition and scalar multiplication for $S, T \in \mathcal{L}$:
1. $(S+T)(\mathbf{x}) = S(\mathbf{x})+T(\mathbf{x})$. 
2. $(\lambda S)(\mathbf{x}) = \lambda(S(\mathbf{x}))$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. It can be shown that both $(S+T)(\mathbf{x})$ and $(\lambda S)$ satisfy the properties of a linear map as well, demonstrating that $\mathcal{L}$ is closed under addition and scalar multiplication.

> <span style="background-color: #03cafc; color: black;">Definition</span>. For two linear maps $S: U \to V$ and $T: V \to W$, the **composite** map $TS: U \to W$ is such that $TS(\mathbf{x}) = T(S(\mathbf{x}))$ for $\mathbf{x} \in U$. Note that order matters here: $S$ acts first, then $T$.

For $TS$ to be well defined, $S(\mathbf{x})$ must be in the domain of $T$; in other words, the image of $S$ must be a subset of the domain of $T$. Furthermore, when $S$ and $T$ are linear maps, they obey the following identities:
1. **Associativity.** For linear maps $S$, $T$, $U$, $S(TU)$ = $(ST)U$ whenever the products are well-defined.
2. **Identity.** Suppose that the linear map $I$ maps vectors onto themselves. Then $TI = IT = T$.
3. **Distributivity.** $(S+T)(U) = SU+TU$, and $S(T+U)=ST+SU$ if all the products are well-defined.

However, linear maps do not satisfy commutativity; $ST$ does not necessarily equal $TS$.

All the above leads to the following result...