---
id: ovco5v150uo99cv3au933vz
title: Permutations and Cycles
desc: ''
updated: 1749199117840
created: 1744798410818
nav_order: 1
---
> What happens when a mathematician tries to comb their perm? Nothing good; everything goes out of order.

### Permutations

A *permutation* is a way to arrange things in a line in order: students in a lunch line, pens in a pencilcase, people in your group of friends - no, wait, it turns out there's only one permutation for that, I'm sorry to say. Sometimes there are very few ways to do so; sometimes there are a lot, like there being more ways to organize my Magic: The Gathering collection then there are atoms in the universe. If lining things up and ordering them really is a sign of autism, then mathematicians truly embody the phrase, "I don't struggle with autism - I'm actually very good at it."

Permutations are very natural candidates for becoming group members because they swap things around but don't actually change anything substantial, they can and will backtrack on everything they do, and they can do ten different steps before realizing they could've done it in one step and saved all the effort. Groups involving permutations have a very simple definition:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define a **permutation** of a set $X = \{x_1, x_2, ..., x_n\}$ as a function $f(x)$ which re-orders $X$: for $i = 1, 2, ..., n$, $f$ maps $x_i$ to another element in the list $x_j$, with the condition that the set $\{f(x_1), f(x_2), ..., f(x_n)\}$ is identical to $X$ - i.e. $f$ changes the order of $X$ but does not change the elements themselves. We stipulate that $f$ is invertible; its inverse $g$ reverses the permutation, such that $(f\circ g) = (g \circ f) = Id$, the identity function that maps every element of the set to itself.<br/><br/>
> Call the list of all permutations of the set $X = \{1,2,...,n\}$ the **$n$th permutation group**, denoted $S_n$; for a general set $X$, instead denote this group by $\text{Sym}(X)$, called the **symmetric group** of $X$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. For any set $X$, the triple $(\text{Sym}(X), \circ, Id)$ indeed forms a group; if all the elements of $X$ are distinct, this group will have order $n!$ This arises directly from the definition of a permutation: a combination of two permutations is still a permutation, as is the inverse a permutation. 

(If at any time there is ambiguity between me being excited about something and me writing a factorial, it's always a factorial.)

### Cycles

A very specific type of permutation is

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **$k$-cycle**. Let $\{a_1, a_2, ..., a_k\}$ be a subset of $\{1, 2, ..., n\}$, all unique and in any order. The $k$-**cycle** of these elements, denoted $(a_1a_2...a_k)$, is a permutation that changes the order of these elements in the following ways:
1. Initially, the element at position $i$ in the set is $a_i$. (Assumed with loss of generality; we simply label the element in the $i$th position $a_i$, not caring about sorting them in ascending order.) (~~I had to physically restrain myself from typing position $i-1$ instead of position $i$. Words cannot describe how much I loathe Python for this.~~)
2. If $i$ is not the final position $k$, the element that will occupy position $i$ is the next element $a_{i+1}$ instead: $(a_1a_2...a_k)(i) = a_{i+1}$. In essence, every element is shifted leftward by one position: $a_{i+1}$ is shifted to position $i$.
3. If $i$ is the final position $k$, the element that will occupy it under the $k$-cycle is $a_1$, the first element; it's gone so far left it has nowhere else to go and finds itself on the extreme right instead, which is a sentence usually reserved for describing the lifecycles of most political Reddit forums.
4. The $k$-cycle does not change the positions of any elements outside of $\{a_1, a_2, ..., a_k\}$; if $m=1, 2, ..., n$ is not part of this aforementioned set, $(a_1a_2...a_k)(m) = m$. 

More formally, we write 
$$
(a_1a_2 ... a_k)(i) = \begin{cases}
a_{i+1},\ i \neq k,\ i \in \{a_1, a_2, ..., a_k\} \\
a_1, i = k,\ i \in \{a_1, a_2, ..., a_k\}  \\
i, i \notin \{a_1, a_2, ..., a_k\}
\end{cases}
$$
treating the $k$-cycle as a function of position $i$ (which it certainly is). 

What a revolution does to the entrenched social hierarchies of a thousand-year monarchy, a $k$-cycle does to $\{a_1, a_2, ..., a_k\}$. Every layer of the social stratosphere, from the lowly servant $a_k$ to the well-born $a_3$, join forces to topple the vile despot $a_1$ into poverty and obscurity; freedom and democratic governance are promised until the scheming $a_2$ snabs the crown.

> Note that a $k$-cycle repeated $k$ times returns the list to its original order!

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call a $2$-cycle $(a_1 a_2)$, whose only purpose is to swap the two elements back and forth, a **transposition**. (My professor tells me I'm not allowed to call them bicycles anymore.)

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $(a_1 a_2 ... a_k)$ and $(b_1 b_2 ... b_l)$ be two cycles (of possibly different lengths). If $\{a_1, a_2, ..., a_k\}$ and $\{b_1, b_2, ..., b_l\}$ do not share any common elements - i.e. their intersection is the null set - call the two cycles **disjoint:** they act on entirely different elements, and thus do not interfere with one another.

### Compositions of cycles

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Composition of cycles.** Cycles are functions; as such, if $\sigma$ and $\tau$ denote two cycles, the notation $\sigma \tau(i)$ is understood to be $\sigma(\tau(i))$ - first the cycle $\tau$ applied to $i$, then $\sigma$.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Disjoint cycles are commutative.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $\sigma = (a_1 a_2 ... a_k)$ and $\tau = (b_1 b_2 ... b_l)$ be two disjoint cycles, with none of the $a_i$s and $b_j$s equalling one another (by definition of disjoint cycles). By the definition of a cycle given above, we have $\sigma(i)$ if $i \neq a_1, ..., a_k$ and $\tau(i)$ if $i \neq b_1, .., b_l$; any $i$ cannot be part of both $\{a_1, ..., a_k\}$ and $\{b_1, b_2, ..., b_l\}$ at once as they have intersection $\emptyset$. Thus, either $\sigma(i) = i$ or $\tau(i) = i$; in addition, if $i$ is not in $\{a_1, ..., a_k\}$, then neither is $\tau(i)$ (as $\tau$ maps from $b_i$ to $b_i$, none of which are in $\{a_1, ..., a_k\}$.)

In the first case where $\sigma(i) = i$, we have
$$
\begin{aligned}
\sigma(\tau(i)) &= \tau(i)\text{ as $\tau(i) \notin a_i$} \\
&= \tau(\sigma(i)) \text{ as $\sigma(i) =i$}.
\end{aligned}
$$
Similarly, for $\tau(i) = i$ we have
$$
\begin{aligned}
\tau(\sigma(i)) &= \sigma(i)\text{ as $\sigma(i) \notin b_i$} \\
&= \sigma(\tau(i)) \text{ as $\tau(i) =i$}.
\end{aligned}
$$
This completes the proof; the statement can be intuitively understood as saying that if two actions act on different parts of something, then the order in which they are performed does not affect the outcome. This is true for groups and less true for open-heart surgery.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Cycles can be cycled: $(a_1a_2a_3...a_k)(i) = (a_2a_3 ... a_k a_1)(i)$, and so on.

>  <span style="background-color: #1eff12; color: black;">Proof</span>.

This follows directly from the definition of a cycle:
$$
(a_2 a_3 ... a_k a_1)(i) = \begin{cases}
a_{i+1},\ i \neq 1, k \\
a_2, i = 1 \\
a_1,  i =k \\
i,\ i \neq a_i
\end{cases}
$$
which corresponds exactly with the original definition of $(a_1 a_2 ... a_k)$.

***

All of the above leads to the following result:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Disjoint cycle decomposition**. Every permutation $\sigma$ in $S_n$ can be written as a composition of disjoint cycles in which $1, ..., n$ all appear, including $1$-cycles $(a_i)(i)$ which do not modify the position of any element. The expression
$$
\sigma = (a^1_1 a^1_2 ... a_{k_1}^1) (a^2_1 a^2_2 ... a^2_{k_2}) ... (a^r_1 a^r_2 ... a^r_{k_r})
$$
> is unique barring a reordering of the elements within a cycle, or a reordering of the cycles themselves.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Proceed by induction on $S_n$. 

The base case, $S_1$, consists of permutations on a set with a single element - this is already a $1$-cycle.

Assume that all permutations in $S_{k}$, $k \in \mathbb{Z^+}$ and $k < n$, can be written as a composition of disjoint cycles. In order to prove that all permutations $\sigma \in S_n$ can be thus decomposed, our goal is to write
$$
\sigma = \tau \circ \rho
$$
where $\tau$ is a disjoint cycle and $\rho$ is a permutation on $S_{n-1}$ (or fewer elements), which by our strong induction assumption can be decomposed.

To proceed, write $\tau = \sigma \circ \rho^{-1}$. Consider the sequence
$1, \sigma(1), \sigma(\sigma(1)) = \sigma^2(1), \sigma^3(1), ..., \sigma^n(1)$; what is the minimum value of $k$ such that $\sigma^k(1) = 1$, and the sequence repeats?

As $1, 2, ..., n$ is a finite sequence of numbers, it is impossible that $\sigma(1), ..., \sigma^k(1), ...$ are distinct for all $k$; the sequence must repeat at some point. Suppose that $\sigma^a(1) = \sigma^b(1)$ for some $a,b$, assuming without loss of generality that $a > b$; then $\sigma^a(1) = \sigma^{a-b}\sigma^b(1) = \sigma^{a-b}\sigma^a(1) = \sigma^{a} \sigma^{a-b}(1)$, yielding $\sigma^{a-b}(1) = 1$ (as a permutation $\sigma$ is one-to-one, and $\sigma(a) = \sigma(b)$ implies $a = b$.)

In addition to this sequence being finite, by the Pigeonhole Principle there are $n$ numbers from $1$ to $n$ and $k$ members of the sequence $\sigma(1), ..., \sigma^k(1)$; if $k > n$ there are $n+1$ numbers to fit into $n$ holes, and at least one value must be repeated. Thus $a, b < n+1$, and $a - b \leq n$. $a-b$ is the first positive number satisfying $\sigma^{a-b}(1) = 1$; call this number $k$, with $\sigma^k(1) = 1$.

The sequence obtained from the above - $1, \sigma(1), ..., \sigma^{k-1}(1)$ - is a distinct sequence of numbers, of maximum length $n$ (as above): if we had $\sigma^a(1) = \sigma^b(1)$ with $k > a > b$, then as before $\sigma^{a-b}(1) = 1$ with $a-b<k$, violating the assumption that $k$ is minimal.

Returning to $\tau = \sigma \circ \rho^{-1}$, let $\rho$ be the $k$-cycle given by the sequence
$$
\rho = (1, \sigma(1), ..., \sigma^{k-1}(1)). 
$$
As all permutations have an inverse, $\tau$ is well-defined for all $\sigma$. In addition, for $m = 0, 1, ..., k-1$ we have
$$
\tau(\sigma^m(1)) = \sigma(\rho^{-1}(\sigma^m(1))) = \sigma(\sigma^{m-1}(1)) = \sigma^m(1)
$$
Meaning that $\tau$ is a permutation upon the subset of $\{1, ..., n\}$ that excludes $\{1, \sigma(1), ..., \sigma^{k-1}(1)\}$ - a subset of size strictly less than $n$. By our strong induction assumption, $\tau$ is thus a composition of disjoint cycles whose expression contains all of $\{1, ..., n\}$ barring $\{1, \sigma(1), ..., \sigma^{k-1}(1)\}$ - and so is $\sigma = \tau \circ \rho$, $\rho$ itself being a cycle whose expression contains all of $\{1, \sigma(1), ..., \sigma^{k-1}(1)\}$. The two combined give a composition of disjoint cycles where $\{1, ..., n\}$ appears in its entirety.
***

To demonstrate that this decomposition is indeed unique, consider the following equality:
$$
(a^1_1 a^1_2 ... a^1_{k_1})...(a^r_1 a^r_2 ... a^r_{k_r}) = (b^1_1 b^1_2 ... b^1_{l_1}) ... (b^s_1 b^s_2 ... b^s_{l_s})
$$
where the two sides are each a decomposition of the permutation $\sigma \in S_n$. By the above, such a decomposition must contain all of $1, ..., n$; as such, $a^1_1 = b^{i_1}_{j_1}$ for some $i_1$, $j_1$. As permutations can be cycled, we have
$$
\begin{aligned} 
a^1_2 &= b^{i_1}_{j_1 + 1} \\
a^1_3 &= b^{i_1}_{j_1 + 2} \\
\vdots \\
a^1_{k_1} &= b^{i_1}_{j_1 + k_1 - 1} \\
a^1_{k_1 + 1} = a^1_1 &= b^{i_1}_{j_1 + k_1}
\end{aligned}
$$
cycling the indices if necessary; as such, $b^{i_1}_{j_1 + k_1} = b^{i_1}_{j_1}$ and all the terms in-between the two are unique, meaning that the cycle $b^{i_1}$ is also a $k_1$-cycle - in fact, by the above equalities, the cycle $b^{i_1}$ is the exact same cycle as the cycle $a^{1}$. As disjoint cycles are commutative, the two cycles can be cancelled off from the equality; the same logic applied to all the above cycles yields the uniqueness of a single decomposition. $\square$

***

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. If the permutation $\sigma$ has disjoint cycle decomposition $(a^1_1 a^1_2 ... a^1_{k_1})...(a^r_1 a^r_2 ... a^r_{k_r})$, then the order of $\sigma$ - i.e. the minimum value of $k$ such that $\sigma^k$ is the identity permutation - is the least common multiple of $k_1, ..., k_r$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $\text{ord}(\sigma) = k$; consider $\sigma^k = (a^1_1 a^1_2 ... a^1_{k_1})^k...(a^r_1 a^r_2 ... a^r_{k_r})^k$ (as disjoint cycles are commutative). A $k_i$-cycle has order $k_i$, and as such, for $\sigma^k$ to be the identity we must have
$$
(a^{i}_1 a^i_2 ... a^i_{k_i})^k = \text{identity}
$$
for all $i$, meaning that all of $k_1, ..., k_r$ divide $k$. 

(The above is true as if one of $(a^{i}_1 a^i_2 ... a^i_{k_i})^k$ is** not** the identity, $\sigma$ would necessarily modify the numbers $a^i_1, a^i_2, ..., a^i_{k_i}$ to have different order, leaving $\sigma$ not equal to the identity.)

All that's left is to prove that $k$ is the lowest such common multiple. Let $l = \text{lcm}(k_1, ..., k_r)$; then we have
$$
\sigma^l = (a^1_1 a^1_2 ... a^1_{k_1})^l...(a^r_1 a^r_2 ... a^r_{k_r})^l
$$
with
$$
(a^{i}_1 a^i_2 ... a^i_{k_i})^l = ((a^{i}_1 a^i_2 ... a^i_{k_i})^{k_i})^a = \text{identity}
$$
for some integer $a$, by definition of the least common multiple. Thus $l$ satisfies $\sigma^l = \text{identity}$; as the order of $\sigma$ is defined as the **minimum** value of $k$ such that $\sigma^k$ is the identity, and any multiple of the LCM yields the identity, the lowest possible value of $k$ is the LCM itself. $\square$

