---
id: y4rxvs6ablmpkja3x83ttpp
title: Conjugacy Classes of Permutations
desc: ''
updated: 1749383496513
created: 1746408656017
nav_order: 4
---

> "Conjugacy" might just be the only word with enough power to traumatize a mathematician, a linguist, and a divorce lawyer all at once.

## Conjugate permutations

We know that group elements which are conjugate to one another share many properties: as a previous page described, if $g$ and $k$ are conjugate to one another via $k = hgh^{-1}$, then $k$ is nothing more than "performing $g$ in the context of $h$". In particular, they share a common order; however, with permutations, they share something much stronger.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. If a cycle is conjugate to another cycle via some $\sigma \in S_n$, then the two cycles are permutations of one another via $\sigma$:
$$
\sigma \in S_n,\ \sigma(a_1 a_2 ... a_k)\sigma^{-1} = (\sigma(a_1)\sigma(a_2) ... \sigma(a_k)).
$$
> <span style="background-color: #1eff12; color: black;">Proof</span>.

(For the rest of this section, permutations in $S_n$ act on the set $X = \{1, 2, ..., n\}$.)

The equality of the above two permutations hinges on whether they act the same way on each element $x \in X = \{1, 2, ..., n\}$. Consider the element $\sigma(x)$ for every $x \in X$; $\sigma$ is an invertible and thus a bijective mapping from $X$ to itself. 

For the left-hand side, we have
$$
\sigma(a_1 a_2 ... a_k)\sigma^{-1}(\sigma (x)) = \sigma(a_1 a_2 ... a_k)(x)
$$
by associativity. If $x= a_i$ for $i = 1, ..., k$, we thus have
$$
\sigma (a_{k+1})
$$
or, if $i = k$, then $\sigma(a_1)$. Alternatively, if $x$ is not one of the $a_i$s, then the output is simply $x$ itself. Thus, the left-hand side permutation acts on $X$ via
$$
\begin{cases}
\sigma(x_i) \to \sigma(x_{i+1}),\ i = 1, 2, ..., k-1\\
\sigma(x_k) \to \sigma(x_1),\ i = k \\
\sigma(x) \to \sigma(x), x \notin \{a_1, ..., a_k\}
\end{cases}
$$
which precisely defines the cycle $(\sigma(a_1), \sigma(a_2), ..., \sigma(a_k))$. (Considering how the permutations act on $\sigma(X)$ is equivalent to considering how they act on the set $X$, as $\sigma$ is a bijection from $X$ to $X$.)

The primary implication of this lemma is that

> <span style="background-color: #12ffd7; color: black;">Corollary</span>.
Any two cycles of the same length are conjugate to one another.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $\sigma = (a_1 a_2 ... a_k)$ and $\tau = (b_1 b_2 .. b_k)$ be two permutations in $S_n$. Then the permutation defined by the product of transpositions
$$
\rho = (a_1 b_1) (a_2 b_2) ... (a_k b_k)
$$
which, with the case $a_i = b_i$ being treated as a "do nothing" permutation,  maps $\sigma$ onto $\tau$ via $\tau = \rho\sigma\rho^{-1}$ by the above lemma.

This leads us to

><span style="background-color: #12ffd7; color: black;">Theorem</span>.
Two permutations are conjugate if and only if their disjoint cycle decompositions feature permutations of the same length: for instance, two permutations in $S_4$ comprised of disjoint cycles of length $1, 1, 2$ are conjugate.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $\sigma$ and $\tau$ be two permutations in $S_n$, with $\sigma$ having disjoint cycle decomposition
$$
\sigma = (a_1^1 a_2^1 ... a_{k_1}^1) ... (a_1^m a_2^m ... a_{k_m}^m)
$$
with cycles of lengths $k_1$, $k_2$, ..., $k_m$. If $\sigma$ and $\tau$ are conjugates via some permutation $\rho \in S_n$, i.e. $\rho \sigma \rho^{-1} = \tau$, then we have
$$
\begin{aligned}
\rho \sigma \rho^{-1} &= \rho (a_1^1 a_2^1 ... a_{k_1}^1) ... (a_1^m a_2^m ... a_{k_m}^m) \rho^{-1} \\
&= (\rho (a_1^1 a_2^1 ... a_{k_1}^1) \rho^{-1}) ... (\rho(a_1^m a_2^m ... a_{k_m}^m)\rho^{-1}) \\
&= (\rho(a_1^1) \rho(a_2^1) ... \rho(a_{k_1})^1)...(\rho(a_1^m) \rho(a_2^m) ... \rho(a_{k_m})^m) = \tau
\end{aligned}
$$
by the above lemma. The cycles of a disjoint cycle decomposition must contain all of $X$, i.e. $a_1^1, ..., a^1_{k_1}, a_2^1, ..., a^m_1, ..., a_{k_m}^m$ are exactly the elements of $X$; and as any permutation $\rho$ is a bijective mapping from $X$ to $X$, the set given by 
$$
\rho(a_1^1), ..., \rho(a_{k_1}^1),..., \rho(a_1^m), ..., \rho(a_{k_m}^m)
$$
are also exactly the elements of $X$. Therefore, $\rho \sigma \rho^{-1}$ in the form expressed above is a disjoint cycle decomposition; and as disjoint cycle decompositions are unique, and given that $\rho \sigma \rho^{-1} =\tau$, the above must also be the unique disjoint cycle decomposition of $\tau$. Thus, $\sigma$ and $\tau$ have disjoint cycle decompositions involving cycles of equal lengths.

Conversely, suppose that $\sigma, \tau \in S_n$ are two permutations with disjoint cycle decompositions involving cycles of equal lengths:
$$
\sigma = (a_1^1 a_2^1 ... a_{k_1}^1) ... (a_1^m a_2^m ... a_{k_m}^m)
$$
and
$$
\tau = (b_1^1 b_2^1 ... b_{k_1}^1) ... (b_1^m b_2^m ... b_{k_m}^m).
$$
Define the permutation
$$
\rho(a^i_{j}) = b^i_j
$$
which satisfies the properties of a permutation because the $a^i_j$s and the $b^i_j$s are both the set $X$, and no two $a^i_j$s nor any two $b^i_j$s are equal by the Disjoint Cycle Decomposition theorem. Thus $\rho$ is a bijection from $X$ to $X$, and is a permutation in $S_n$. By this construction we directly obtain
$$
\rho \sigma \rho^{-1} = \tau
$$
through the above lemma, proving the statement. $\square$

## Cycle types and conjugacy classes

> <span style="background-color: #03cafc; color: black;">Definition</span>. From the above statements, we know that two permutations with disjoint cycle decompositions whose cycles are of equal lengths are conjugate; call the number of $1$-cycles, $2$-cycles, ..., $n$-cycles in the disjoint cycle decomposition of a permutation $\sigma \in S_n$, denoted $\sigma_1$, $\sigma_2$, ..., $\sigma_n$ respectively, the **cycle type** of $\sigma$. This is usually written $1^{\sigma_1} 2^{\sigma_2}...n^{\sigma_n}$.

By construction, two permutations with the same cycle type are conjugate; in other words, they belong to the same *conjugacy class* (i.e. the same orbit under the conjugation action). Moreover, we also have the following:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Recall that the **centralizer** of an element $g$ in a group $G$ as its stabilizer under the conjugation action:
$$
C_G(g) = \{h \in G: hgh^{-1} = g\}
$$
> or, alternatively, as all the elements in $G$ that commute with $g$.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. 
> Suppose that a permutation $\sigma \in S_n$ has cycle type $1^{\sigma_1} 2^{\sigma_2}...n^{\sigma_n}$. Then the order of the centralizer of $\sigma$ is
$$
|C_{S_n}(\sigma)| = 1^{\sigma_1}(\sigma_1!)2^{\sigma_2}(\sigma_2!) ... n^{\sigma_n}(\sigma_n!).
$$
> <span style="background-color: #1eff12; color: black;">Proof</span>.

The centralizer of $\sigma$ is all permutations $\tau \in S_n$ such that $\tau \sigma \tau^{-1} = \sigma$. Suppose that $\sigma$ has disjoint cycle decomposition
$$
\sigma = (a_1^1 a_2^1 ... a_{k_1}^1) ... (a_1^m a_2^m ... a_{k_m}^m)
$$
leading to
$$
\tau \sigma \tau^{-1} = (\tau(a_1^1) \tau(a_2^1) ... \tau(a_{k_1}^1)) ... (\tau(a_1^m) \tau(a_2^m) ... \tau(a_{k_m}^m)).
$$
Cycles remain the same if a permutation acts on them in two ways: 1) if the permutation cycles them, i.e.
$$
(\tau(a_1)\tau(a_2) ... \tau(a_k))
$$
is a cycle of $(a_1 a_2 ... a_k)$, or 2) if the permutation swaps them with another cycle of the same length, e.g. a $3$-cycle with another $3$-cycle. For a $k$-cycle ($k = 1, 2, ..., n$), there are $\sigma_k!$ ways to permute the $\sigma_k$ cycles in the disjoint cycle decomposition of $\sigma$; for each of these ways, there are $k^{\sigma_k}$ ways to cycle all $\sigma_k$ of these cycles. Thus, we obtain
$$
|C_{S_n}(\sigma)| = 1^{\sigma_1}(\sigma_1!)2^{\sigma_2}(\sigma_2!) ... n^{\sigma_n}(\sigma_n!)
$$
in total.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. Let $\sigma \in S_n$ have cycle type $1^{\sigma_1} 2^{\sigma_2}...n^{\sigma_n}$. Then the size of the conjugacy class of $\sigma$, denoted $|\text{ccl}(\sigma)|$, is 
$$
|\text{ccl}(\sigma)| = \frac{n!}{1^{\sigma_1}(\sigma_1!)2^{\sigma_2}(\sigma_2!) ... n^{\sigma_n}(\sigma_n!)}.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>. $S_n$ has order $n!$; an application of the Orbit-Stabilizer theorem on the orbit of $\sigma$, which is $\text{ccl}(\sigma)$, and the stabilizer of $\sigma$, which is $C_{S_n}(\sigma)$, yields the above expression.

We know that normal subgroups only arise from the unions of conjugacy classes; as such, knowing exactly *what* the conjugacy classes are (permutations of the same cycle type) and *how big* each conjugacy class is grants us valuable insight in searching for normal subgroups.

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the normal subgroups of $S_4$.

The possible cycle types of a permutation $\sigma \in S_4$ are $1^42^0 3^0 4^0$ (the identity permutation); $1^2 2^1 3^0 4^0$ (a single transposition); $1^1 2^0 3^1 4^0$ (a $3$-cycle); $1^0 2^2 3^0 4^0$ (two transpositions); and $1^0 2^0 3^0 4^1$ (a $4$-cycle). 

The identity permutation stands alone as a conjugate class; using the formula above, the sizes of the other four conjugacy classes are $6$, $8$, $3$, and $6$ respectively. By Lagrange's Theorem, subgroups are of order 1, 2, 3, 4, 6, 8, 12 and 24; any subgroup will contain the identity conjugacy class.

The union of the identity conjugacy class and the class of two transpositions is size $4$, which is $C_2\times C_2$ and a normal subgroup.

If a normal subgroup contains the conjugacy class of single transpositions, then it must be $S_4$ itself as any symmetric group is generated out of single transpositions.

If a normal subgroup contains the conjugacy class of $3$-cycles - which, when combined with the identity conjugacy class, yields a set of size $9$, and must then be either a subgroup of size $12$ or $24$ by Lagrange's Theorem - then we would have (for size $12$)
$$
1 + 8 + 3 = 12
$$
through the union of the identity conjugacy class, the class of $3$-cycles, and the class of two transpositions of size $3$; this is $A_4$. For size $24$, we simply have $S_4$.

Finally, if a normal subgroup contains the conjugacy class of $4$-cycles, then by
$$
(1234)(1324) = (142)
$$
we know that it must also contain at least one $3$-cycle, and by the requirement that normal subgroups are unions of entire conjugacy classes, it must contain every single $3$-cycle. This yields $S_4$, as it would lead to a subgroup of size $1 + 6 + 8 = 15$ which can only be $S_4$ by Lagrange's Theorem.

Therefore, we yield the normal subgroups
$$
(\{e\}, C_2\times C_2, A_4, S_4)\triangleleft S_4. 
$$

## Conjugacy classes in alternating groups

In $S_n$, the conjugacy classes are formed simply by all permutations of a certain cycle type; in $A_n$, things are muddied by the fact that odd permutations are no longer accessible to us for conjugation. For instance, any two $3$-cycles are conjugate in $S_3$ by virtue of having the same cycle type, e.g. $(123)$ and $(213)$; however, they are not conjugate in $A_3 \cong C_3$ because $A_3$ is an abelian group, and elements in an abelian group are conjugate if and only if they are equal via
$$
gag^{-1} = gg^{-1}a = a.
$$

Closer inspection gives us the following result:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Suppose that $\sigma \in A_n$; denote the conjugacy classes of $\sigma$ in $S_n$ and $A_n$ by $\text{ccl}_{S_n}(\sigma)$ and $\text{ccl}_{A_n}(\sigma)$ respectively. Then $\text{ccl}_{A_n}(\sigma)$ is either half the size or the same size as $\text{ccl}_{S_n}(\sigma)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>


 We have $|S_n| = 2|A_n|$; by the Orbit-Stabilizer theorem, we have
$$
\begin{cases}
|S_n| = |\text{ccl}_{S_n}(\sigma)||C_{S_n}(\sigma)| \\
|A_n| = |\text{ccl}_{A_n}(\sigma)||C_{A_n}(\sigma)|
\end{cases}
$$
and thus
$$
|\text{ccl}_{S_n}(\sigma)||C_{S_n}(\sigma)| = 2|\text{ccl}_{A_n}(\sigma)||C_{A_n}(\sigma)|.
$$
We know that $|C_{A_n}(\sigma)|$ is also a factor of $|C_{S_n}(\sigma)|$ ($A_n$ is a subgroup of $S_n$, and so $C_{A_n}$ is a subgroup of $C_{S_n}$); in fact, we know very precisely that $C_{A_n}$ is either half the size of $C_{S_n}$ or exactly the same size as $C_{S_n}$: every subgroup of $S_n$ is either half even or completely even, i.e. either half in $A_n$ or completely in $A_n$, with the former resulting in 
$$
|C_{A_n}| = \frac{1}{2}|C_{S_n}|
$$
and the latter in
$$
|C_{A_n}| = |C_{S_n}|.
$$
Substituting this into the equation above results in
$$
|\text{ccl}_{A_n}(\sigma)| = 2|\text{ccl}_{S_n}(\sigma)|
$$
or 
$$
|\text{ccl}_{A_n}(\sigma)| = |\text{ccl}_{S_n}(\sigma)|
$$
as desired. $\square$

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. Call a conjugacy class $\text{ccl}_{S_n}(\sigma)$ that is halved in size in $A_n$ a **split** conjugacy class. If the stabilizer of $\sigma$ in $S_n$ is completely even, the conjugacy class splits; otherwise, it does not split.

This is derived directly from the proof above.

> <span style="background-color: #03cafc; color: black;">Example</span>. Describe the conjugacy classes of $A_4$ and derive its normal subgroups.

To start with, let's describe the conjugacy classes of $S_4$. From the above example, we have

| Conjugacy class | Order of class |
| --------------- | -------------- |
| $1$-cycle, $\{e\} | 1 |
| Single transpositions | 6 |
| Double transpositions | 3 |
| $3$-cycles | 8 |
| $4$-cycles | 6 |
<br/>

In which:
- The identity conjugacy class is not split (as all its elements are also in $A_4$)
- The conjugacy class of single transpositions are odd, and are not in $A_4$.
- The conjugacy class of double transpositions lie in $A_4$. Their centralizers contain an odd element (e.g. $(12)(34)$ is stabilized by $(12)$), and as such we know they are half odd; thus, this conjugacy class is not split in $A_4$.
- The conjugacy class of $3$-cycles lie in $A_4$. The Orbit-Stabilizer theorem shows that the size of their centralizer is $24 / 8 = 3$ (there are $8$ $3$-cycles); as such, every element in this subgroup has order $3$ and is therefore a $3$-cycle (which is even). Thus the centralizer of this conjugacy class lies entirely in $A_4$, and so this class is split into two classes of size $4$. 
- The conjugacy class of $4$-cycles are odd and do not lie in $A_4$.

Thus, the conjugacy classes of $A_4$ are:
- The identity conjugacy class (not split, order $1$)
- The conjugacy class of double transpositions (not split, order $3$)
- The two conjugacy classes formed from $3$-cycles (split, each of order $4$)

By Lagrange's Theorem, the normal subgroups of $A_4$ can be of order $1$, $2$, $3$, $4$, $6$ or $12$; our conjugacy classes have orders $1, 3$ and $4$. Thus we either have
$$
1 = 1
$$
which is the identity normal subgroup $\{e\}$; 
$$
1 + 3 = 4
$$
i.e. the union of the identity subgroup and the double transposition conjugacy class. This is $C_2 \times C_2$, and forms a normal subgroup. Finally, any normal subgroup including a single split conjugacy class of $3$-cycles (of order $4$) must also include the identity; and so it has order
$$
1+ 4= 5
$$
But all other conjugacy classes in $A_4$ are either of order $4$ or order $3$, which cannot add to $5$ to result in $6$; thus, the normal subgroup corresponding to this case must have order $12$ by Lagrange's Theorem, and will be $A_4$. Therefore, the normal subgroups of $A_4$ are $\{e\}, C_2 \times C_2, A_4 \triangleleft A_4$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. $A_5$ is simple.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

$S_5$ has the following conjugacy classes:

| Conjugacy class | Size |
|-|-|
|$\{e\}$|$1$|
| Single transpositions (e.g. $(12)$)| $5 \choose 2$ $= 10$| 
| $3$-cycles (e.g. $(123)$) | $15$ 
| $4$-cycles (e.g. $(1234)$) | $30$
| $5$-cycles (e.g. $(12345)$) | $24$ 
| Double transpositions (e.g. $(12)(34)$) | $5 \choose 2$ $3 \choose 2$ $=15$
<br/>

Of these conjugacy classes, $\{e\}$, $3$-cycles, $5$-cycles and double transpositions are in $A_5$; double transpositions are not split, $5$-cycles are split (as they are centralized by a group of order $5$, which must be the cyclic group of $5$-cycles, which are even), and $3$-cycles are not split because $(12)$, which is odd, centralizes $(345)$. This leads to the following conjugacy classes for $A_5$:


| Conjugacy class | Size |
|-|-|
|$\{e\}$|$1$|
| $3$-cycles (e.g. $(123)$) | $15$ 
| $5$-cycles, class $1$ | $12$ 
| $5$-cycles, class $2$ | $12$ 
| Double transpositions (e.g. $(12)(34)$) | $5 \choose 2$ $3 \choose 2$ $=15$
<br/>

If $G$ is a normal subgroup of $A_5$, then by Lagrange's Theorem $|G|$ must divide $5!/2=60$; moreover we see from the size of the conjugacy classes that, excepting the identity subgroup $\{e\}$, the minimal size of a normal subgroup (formed from the union of conjugacy classes) is $12 + 1 = 13$. The possible values for the order of $G$ are thus all the divisors of $60$ greater than $13$: $15, 30$ and $60$. None of these can be formed from the sums of the orders of the above conjugacy classes excepting $60$, which is the union of all of them at once; thus, the only normal subgroups of $A_5$ is $\{e\}$ and itself, and so $A_5$ is simple. $\square$