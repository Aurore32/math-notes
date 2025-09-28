
> PUBLIC SERVICE ANNOUNCEMENT: DO NOT, under ANY circumstances, search the word "subgroup" on Urban Dictionary. DO NOT search the word "subspace" on Urban Dictionary. DO NOT <br/><br/>
~~Domgroup uwu nyaaaaa :3 sorry~~

## Subgroups

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call the group $(H,\cdot_H,e_H)$ a **subgroup** of $(G, \cdot_G, e_G)$ - denoted $(H, \cdot_H, e_H) \leq (G, \cdot_G, e_G)$ - if $H$ and $G$ satisfy the following three conditions:

1. $H \subset G$. ($H$ is a subset of $G$)
2. $e_H = e_G$.
3. For all pairs of elements $a, b\in H$, $a\cdot_H b = a\cdot_G b$.
   
Subgroups are a natural extension of the notion of a subset to groups: they inherit the group's identity and binary operation while also inheriting a subset of its set. Examples of subgroups: $(\mathbb{Z}, +)$ to $(\mathbb{R}, +)$; $(e, *)$, a group involving only the identity, to any group with the same operation $*$ and identity $e$; the group of divorced Hollywood actors to the group of Hollywood actors.

An easy way to check whether a given group is a subgroup of another is

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. The **subgroup lemma**: let $(G, \cdot_G, e_G)$ be a group and $H$ be a non-empty subset of $G$. It is possible to find a unique binary operation $\cdot_H$ and an identity $e_H$ such that $H \leq G$ if and only if the following conditions are satisfied:
1. $e_G \in H$.
2. For any $a, b \in H$, $a \cdot_G b \in H$.
3. For any $a \in H$, $a^{-1} \in H$.

> Alternately, simply the condition that for any $a, b \in H$, the element $a \cdot_G b^{-1} \in H$ suffices.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

The three given conditions are equivalent to stating that the four group axioms - closure, associativity, inverse, and identity - hold for $H$.

1. **Closure**. Given by requirement (2) by definition.
   
2. **Associativity**. Suppose that $a, b, c$ are elements of $H$; as $H$ is a subset of $G$, $a, b, c$ are also elements of $G$, in which the binary operation $\cdot_G$ is associative. Thus, the associativity of $\cdot_G$ is inherited from $G$.
   
3. **Inverse**. Given by requirement (3).
   
4. **Identity.** Our requirement for $H$ forming a subgroup is that $H$ and $G$ have the same identities. Denote the identity of a group formed by $H$ as $e_H$; then 
    $$
    e_H \cdot_G e_H = e_H
    $$
    in the group $H$. In the group $G$, $e_H$ has an inverse $e_H^{-1}$ where $e_H e_H^{-1} = e_G$, the identity of group $G$. Then
    $$
    e_H e_H e_H^{-1} = e_H e_H^{-1}
    $$
    and as such
    $$
    e_H e_G = e_G
    $$
    leading to $e_H = e_G$.<br/>

Now we prove that these three conditions can be condensed into the condition that, for non-empty $H$, any $a, b \in H$ satisfy $a\cdot_G b^{-1} \in H$.

First, suppose that $b = a$ (this element must exist as $H$ is non-empty). Then we have $a \cdot_G a^{-1} \in H$, and as $a$ is an element of $G$, $a \cdot a^{-1} = e_G \in H$. This is equivalent to the first given condition. 

Supposing that $a = e_G$, we have
$$
e_G \cdot_G b^{-1} = b^{-1} \in H
$$
if $b \in H$. This gives rise to the third condition, and leads directly to
$$
a, b\in H \to b^{-1} \in H \to a\cdot_G (b^{-1})^{-1} = a \cdot_G b \in H
$$
satisfying the second given condition. $\square$

***

> <span style="background-color: #ffb812; color: black;">Proposition</span>. Every subgroup of $(\mathbb{Z}, +)$ is described by $(n\mathbb{Z}, n)$ for some integer $n$, where the set $n\mathbb{Z} = \{nk | k \in \mathbb{Z}\}$ is the set of integer multiples of $n$: for instance, $2\mathbb{Z}$ describes the even integers while $3\mathbb{Z}$ describes integer multiples of $3$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

First we prove the forward statemeent: that $n\mathbb{Z}$ indeed satisfies the definition of a subgroup. Suppose that $a = nx$ and $b = ny$ for some $x, y \in \mathbb{Z}$. The inverse of $b$ under the operation $+$ is the additive inverse: $b^{-1} = -ny$, yielding
$$
a + b^{-1} = nx - ny = n(x-y)
$$
which by definition is an element of $n\mathbb{Z}$. By the lemma above, this indicates that $n\mathbb{Z} \leq \mathbb{Z}$. 

Conversely, suppose that $H$ is a subgroup of $\mathbb{Z}$ and that $H \neq \{0\}$, the trivial subgroup; then by the above lemma, we have

1. The identity element $0 \in H$.
2. For $a, b \in H$, $a+b\in H$.
3. For $a \in H$, $a^{-1} = -a \in H$.

Suppose that $n$ and $m$ are elements of $H$ that have the smallest and second-smallest absolute values out of all non-identity elements in $H$, not necessarily uniquely; as $H$ is not the trivial subgroup, $H$ has at least two elements $n$ and $m$ such that $m>n$. 

Without loss of generality, assume that they are both positive (as any element of $H$ must have their additive inverses also a part of $H$, by condition (3)). Now consider the element of $H$ given by
$$
m - n = m + n^{-1} \in H
$$
with $m > n$ leading to $0 < m - n < m$. Consider whether $m-n$ is smaller than $n$. If $m-n$ is smaller than $n$, $n$ would no longer be the smallest positive element; this would lead to a contradiction. Thus, $m-n \geq n$; if $m - n$ was strictly larger than $n$, it would be the second-smallest positive number in $H$, not $m$ as we assumed - also a contradiction. The only remaining option is $m - n =n, m = 2n$; a similar argument on the $k$th and $k+1$th largest positive elements in $H$ yields that $H$ can only take the form
$$
H = n\mathbb{Z}.\ \square
$$
