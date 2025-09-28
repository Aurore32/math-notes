---
id: z5qq1tdda9971j27ds5ys49
title: Sign of a Permutation
desc: ''
updated: 1749202412153
created: 1744876345956
---
### Transpositions

> A mathematician and a musician walk into an instrument shop and see an upright clarinet on display. "Why, that's a clarinet transposed to E-Flat!" the musician exclaims. But the mathematician remains unconvinced; after all, an upright clarinet transposed always becomes A Flat clarinet.

~~(dear god how is this joke even worse than the last one i wrote)~~

> <span style="background-color: #03cafc; color: black;">Definition</span>. Recall that a **transposition** is the same thing as a $2$-cycle: it is denoted $(a_1 a_2)$ for some $a_1$, $a_2$, and it swaps the positions of these two elements and these two elements alone.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Every permutation can be written as a (not necessarily unique, and not necessarily disjoint) product of transpositions.

To paraphrase almost verbatim from my textbook, this is "one of these theorems which seem deep and mysterious until you realize all it's telling you is that you can get things in a list into some order you want by swapping these things around two at a time." Excluding elbow nudges, headbutts and dropkicks, swapping two at a time is also the only way the human body permits us to swap things around.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

We know already from disjoint cycle decomposition that any permutation $\sigma$ is expressible as a product of cycles; it thus suffices to show that any general $k$-cycle
$$
(a_1 a_2 ... a_k)
$$
can be written as a product of permutations. This is shown to be true via the construction
$$
(a_1 a_2 ... a_k) = (a_1 a_2) (a_3 a_4) ... (a_{k-1} a_k).
$$
To prove this equality, we propose the following: 
> <span style="background-color: #12ffd7; color: black;">Lemma</span>. For the distinct numbers $a_1, ..., a_k$ pictured above, we have
$$
(a_1 a_2)(a_2a_3...a_{k}) = (a_1a_2...a_k).
$$
> <span style="background-color: #1eff12; color: black;">Proof</span>. 
$$
(a_2 a_3 ... a_k)(j) = \begin{cases}
a_2, j = a_k \\
a_{i+1}, j = a_2, ..., a_{k-1} \\
j, j\neq a_2,..., a_k
\end{cases}
$$
> and thus
$$
(a_1 a_2)(a_2 a_3 ... a_k)(j) = \begin{cases}
(a_1 a_2)(a_2) = a_1, j = a_k \\
a_{i+1}, j = a_2, ..., a_{k-1} \\
a_2, j = a_1 \\
j, j \neq a_1, ..., a_k
\end{cases}
$$
which matches the definition of the $k$-cycle $(a_1 a_2 ... a_k)$. Given this lemma, we have
$$
(a_{k-2} a_{k-1})(a_{k-1} a_k) = (a_{k-2} a_{k-1} a_k)
$$
and
$$
(a_{k-3} a_{k-2}) (a_{k-2} a_{k-1} a_k) = (a_{k-3} a_{k-2} a_{k-1} a_k)
$$
and so on, resulting in the desired equality. This decomposition is intuitively understood as "moving all things to the left by one position equals swapping $1$ with $2$ (so that $2$ is now at $1$), then swapping $2$ with $3$ (so that $3$ is now at $2$), ...".

### The sign of a transposition

> <span style="background-color: #03cafc; color: black;">Definition</span>. Writing $\#(\sigma)$ as the number of transpositions making up the transposition decomposition of $\sigma$, define the **sign** of $\sigma$ as $(-1)^{\#(\sigma)}$ - $1$ when $\sigma$ can be decomposed into an even number of transpositions, $-1$ if instead that number is odd.

The well-definedness of $\#(\sigma)$ is predicated on the following theorem:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The decomposition of a permutation into transpositions is, in general, not unique; however, its **sign** is. The number of transpositions present in the transposition decomposition of a permutation $\sigma \in S_n$ will either be always odd or always even, yielding either $1$ (in the even case) or $-1$ (the odd case) as the sign of $\sigma$ across all possible decompositions.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

The proof relies on two distinct parts: 1) that a transposition $\sigma \in S_n$ is equal to the identity permutation $e$ multiplied by a number of transpositions; and 2) multiplying a permutation by a transposition causes its sign to remain unchanged.

The first statement is true by the existence of transposition decompositions for every $\sigma$. For the second statement, let us consider the composition $\sigma(ab)$ for a transposition $(ab)$ where, without loss of generality, we assume $a<b$; denoting the number of disjoint cycles $\sigma$ can be decomposed into (a number which is unique, by the Disjoint Cycle Decomposition Theorem) by $l(\sigma)$, we have either

1) That $a$ and $b$ lie in different cycles in the cycle decomposition of $\sigma$:
$$
\sigma = (...)(aa_1 a_2 ... a_k)(bb_1 b_2 ... b_l)...(...)
$$
cycling $a$ and $b$ to position $1$ if necessary. By the lemma of multiplying a cycle and a transposition above, we have
$$
\begin{aligned}
(aa_1 ... a_k)(b b_1 ... b_l)(ab) &= (aa_1)... (a_{k-1} a_k) (b b_1) ... (b_{l-1}b_l)(ab) \\
&= (aa_1)... (a_{k-1} a_k) (b b_1) (ab) ... (b_{l-1}b_l) \\
\end{aligned}
$$
as disjoint cycles are commutative; this results in
$$
\begin{aligned}
(aa_1)... (a_{k-1} a_k) (b b_1) (ab) ... (b_{l-1}b_l) &= (aa_1)... (a_{k-1} a_k) (b_1 b) (b a) ... (b_{l-1}b_l) \\
&= (aa_1)... (a_{k-1} a_k) (b_1 b a) ... (b_{l-1}b_l) \\
&= (aa_1)... (a_{k-1} a_k) (bab_1) (b_1 b_2)... (b_{l-1}b_l) \\
&= (aa_1)... (a_{k-1} a_k) (bab_1...b_{l-1}b_l) \\
&= (a a_1) (bab_1...b_{l-1}b_l) ...(a_{k-1} a_k) \\
&= (a_1 a)(a b_1 ... b_l b)... (a_{k-1} a_k) \\
&= (a_1 a b_1 ... b_l b) ... (a_{k-1} a_k) \\
&= (a b_1 ... b a_1) (a_1 a_2) ... (a_{k-1} a_k) \\
&= (ab_1 ... b a_1 ... a_{k})
\end{aligned}
$$
and thus $l(\sigma(ab))$, the number of disjoint cycles in the decomposition of $\sigma(ab)$, is $1$ less than $l(\sigma)$ (as the two distinct cycles $(aa_1... a_k)$ and $(bb_1 ... b_l)$ are now a single cycle.) Thus we have $l(\sigma(ab)) = l(\sigma) - 1$.

2) If $a$ and $b$ instead lie in the same cycle $(a a_1 ... a_k b b_1 ... b_l)$, we have
$$
\begin{aligned}
(a a_1 ... a_k b b_1 ... b_l)(ab) &= (a_1 ... a_k b b_1 ... b_l a)(ab) \\
&= (a_1 ... a_k b b_1) (b_1 ... b_l a b) \\
&= (a_1 ... a_k b)(bb_1) (b_1 ... b_l a b) \\
&= (a_1 ... a_k b)(bb_1) (b b_1 ... b_l a) \\
&= (a_1 ... a_k b)(bb_1) (b b_1) (b_1 ... b_l a) \\
\end{aligned}
$$
As permutation products are associative and a transposition is its own inverse, the $(bb_1)$s cancel out, leaving 
$$
(a_1 ... a_k b) (ab_1 ... b_l)
$$
which means that multiplying by $(ab)$ increases the number of cycles composing $\sigma$ by 1 - $l(\sigma(ab)) = l(\sigma) + 1$. In either of the two above cases, $l(\sigma(ab)) \equiv l(\sigma) + 1\ (\text{mod}\ 2)$.
As any $\sigma$ can be written as a product of transpositions with the identity permutation $e$, we thus have
$$
l(\sigma) \equiv l(e) + \#(\sigma)\ (\text{mod}\ 2)
$$
where $\#(\sigma)$ is the number of transpositions composing $\sigma$; as $l(\sigma)$ and $l(e)$ is unique with respect to $\sigma$ and $e$, so is $\#(\sigma)\ (\text{mod}\ 2)$. $\square$

### Alternating groups

The well-definedness of the **sign of a permutation** $\sigma$, written $\text{sign}(\sigma)$, allows us to classify permutations into two types based on their sign.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call $\sigma$ an **even permutation** if $\text{sign}(\sigma) = 1$; call $\sigma$ an **odd permutation** if instead $\text{sign}(\sigma) = -1$. (Note the similarity to the alternating Levi-Civita symbol $\epsilon_{...}$!)

More interesting still is 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. $\text{sign}(\sigma)$ for $\sigma \in S_n$ is a group homomorphism from $S_n$ to the cyclic group $C_2 = \{-1, 1\}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

As multiplication is the binary operation common to both sets, our condition for a group homomorphism is 
$$
\text{sign}(\sigma \tau) = \text{sign}(\sigma) \text{sign}(\tau)
$$
for any two permutations $\sigma, \tau \in S_n$. Suppose that $\sigma$ is composed of $k$ transpositions, and $\tau$ of $l$; by the well-definedness of the sign function, we know that as $k$ and $l$ are constant $\text{mod }2$ no matter the decomposition used, $k + l$ will also be constant $\text{mod }2$ - exactly the number of transpositions making up $\sigma \tau$ (of course, this is not the only decomposition possible for $\sigma \tau$). This leads to
$$
\text{sign}(\sigma \tau) = (-1)^{k+l}=(-1)^k (-1)^l = \text{sign}(\sigma) \text{sign}(\tau)
$$
satisfying the condition for a homomorphism. $\square$

This leads directly to

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **alternating group** $A_n$ consists of all permutations in $S_n$ that have sign $1$ (or, equivalently, are even).

Why define such a group - which, by the way, we haven't even shown to be a group yet - at all? There are probably many, many reasons, the vast majority of which I have no hopes of comprehending or communicating, but two stand out as most immediate:

1. > <span style="background-color: #12ffd7; color: black;">Theorem</span>. $A_n$ is a subgroup of $S_n$; the set of odd permutations in $S_n$ is not.

    This follows from the fact that 1) every permutation has an inverse, including even ones, and inverted even permutations are still even by virtue of the identity permutation $e$ being even; and 2) two even permutations composed together are still even (as $\text{sign})$ is a multiplicative function). The same is not true for odd permutations; the identity permutation is not odd, and the product of two odd permutations is even ($-1 \cdot -1 = 1$.)

2. Even permutations preserve *orientation*: if $x$, $y$ and $z$ were the coordinate axes with right-handed orientation, and $\sigma$ was an even permutation on these axes, then the resulting set of axes would remain right-handed. Importantly, this finds an application both in the formula for the cross product
    $$
    \mathbf{a \times b} = \epsilon_{ijk}a_jb_k
    $$
    where $\epsilon$ is just the sign function in a trench coat after several cosmetic surgeries in Korea, as well as for the determinant
    $$
    \det A = \sum_{\sigma}\text{sign}(\sigma)a_{\sigma(i) i}.
    $$

One last result to cap things off! The sign of a permutation is the product of the signs of the cycles in its disjoint cycle decomposition. This much we know already, but we further propose that

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The sign of any $k$-cycle $(a_1 a_2 ... a_k)$ is $(-1)^{k-1}$. This directly follows from $(a_1a_2... a_k) =(a_1 a_2)(a_2 a_3) ... (a_{k-1} a_k)$ totaling $k-1$ transpositions.

As such, if $k$ is even, then the $k$-cycle is odd; if $k$ is odd, then the $k$-cycle is even. Fantastic.

This results in

> <span style="background-color: #ffb812; color: black;">Proposition</span>. A permutation is even if there is an even number of odd cycles in its disjoint cycle decomposition, per the above.

which amounts to a fairly convenient way to check the sign of any permutation, all things considered.
