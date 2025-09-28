---
id: q7gca6v82fgdg2nc4vddc8n
title: Conjugation
desc: ''
updated: 1749275756793
created: 1745848383573
nav_order: 3
---
## Examples of group actions

### Left regular action

Some group actions act on the group themselves: that is to say, a function $\phi$ can be defined that takes every element $g\in G$ to a permutation of the elements of $G$. The simplest such action is the

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Left regular action**. For a group $G$, define the **left regular action** of $G$ on itself via the function $\phi(g)(x) = g\cdot_G x$: the action of $g$ on $x$ is just $g$ multiplied by $x$. This action is faithful and transitive.

The fact that this *is* an action at all derives from the group axioms; its faithfulness derives from $gx = x$ implying necessarily that $g = e$, by the uniqueness of the identity; and its transitiveness derives from $\phi(yx^{-1})(x) = y$ for any $x, y\in G$.

Through the framework of a regular action, we are now equipped to prove

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Cayley's Theorem.** **Every single group** is isomorphic to a subgroup of some symmetric group.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Via the left regular action, a homomorphism $\phi: G \to \text{Sym}(G)$ can be defined whose kernel is $\{e\}$; by the **<sup>FIRST</sup> ISOMORPHISM THEOREM!!!**, we then have
$$
G/\text{Ker}(\phi) = G/\{e\} = G \cong \text{Im}(\phi) \leq \text{Sym}(G).
$$

***

On the surface, Cayley's theorem seems like a surprising result; symmetric groups just describe ways of swapping the order of things around, after all - so how can groups of all kinds, from quaternions to the integers to a dihedral group acting on polygons, be encapsulated in nothing more than those permutations? Once you think about it, though, it's not really that weird! Let's say $g \in G$ is a product of two elements $g_1 g_2$:
$$
g = g_1 g_2
$$
All that Cayley's theorem says is that multiplication by $g_1$ can be thought of as the permutation that makes $g_2$ swap places with $g$ - something which holds true for all combinations of elements in $G$, as per the left regular action.

***

### Left coset action

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $G$ be a group and $H$ its subgroup. Define the transitive **left coset action** of $G$ on the left cosets of $H$ via the function
$$
\phi(g_1)(gH) = g_1gH,\ g_1, g \in G
$$
> i.e. left multiplication by $g_1$ on the coset $gH$. 

This satisfies the definitions for a group action via closure ($\phi(g_1)(gH) = g_1gH$ is still a left coset of $H$), identity ($\phi(e_G) (gH) = gH$), and the homomorphism property
$$
\phi(g_1 g_2)(gH) = g_1g_2(gH) = g_1(g_2 (gH)) = \phi(g_1)\phi(g_2)(gH).
$$
Transitivity can be shown via
$$
\phi(ab^{-1})(bH) = aH,\ \forall a, b \in G
$$
with the left coset action reducing to the left regular action when $H = \{e\}$.

## The conjugation action

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $a, b$ both be elements of a group $G$. Define the **conjugation** of $a$ by $b$ as the group element given by $c= bab^{-1} \in G$; conversely, if there exists some $b \in G$ such that $c = bab^{-1}$, call $a$ and $c$ **conjugates**.

What is the point of conjugation? If we interpret multiplication by an element in a group as "doing something" - e.g. multiplication by a permutation is switching the order of a set, and multiplication by a cyclic group element is a rotation - then the expression $bab^{-1}$ just means "doing $b$ first, then $a$, then reversing $b$". In non-abelian groups, this is markedly different from just doing $a$; we are *placing $a$ in the context of having done $b$ first*.

(To get a sense for why these two things might be different, compare "undressing in your own home" vs. "driving to the closest kindergarten in your neighborhood, undressing once you've gotten there, and driving back home." Though I suspect you probably won't be getting to the "driving back home" part if you do this.)

But that doesn't mean the conjugates $bab^{-1}$ and $a$ are *completely* different; we've placed the action $a$ in a different context, but it's still the action $a$. For that reason, several similarities arise; for instance, the conjugate of an element has the same order as the element itself, with
$$
(bab^{-1})^k = ba^k b^{-1} = e \iff a^k = e.
$$

Through conjugation, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **conjugation action** of a group $G$ on itself is defined via the function
$$
\phi(g)(x) = gxg^{-1},
$$
> i.e. conjugating the element $x \in G$ by the element $g \in G$.

This is a well-defined group action by virture of closure ($gxg^{-1} \in G$ by group closure), identity ($exe^{-1} = x$), and multiplicativity with
$$
\begin{aligned}
\phi(g_1g_2)(x) &= (g_1 g_2)(x)(g_1 g_2)^{-1} \\
&= g_1 g_2 x g_2^{-1} g_1^{-1} \\ 
&= g_1(g_2 x g_2^{-1})g_1^{-1} \\
&= \phi(g_1)(\phi(g_2)(x)).
\end{aligned}
$$

The orbits and stabilizers of $G$ under the conjugacy action have special names: in particular, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Conjugacy classes**. The **conjugacy class** of a group element $a \in G$ is its orbit under the conjugacy action (which partition $G$, by a previous result):
$$
\text{ccl}(a) = \{g' \in G: (\exists g\in G)\ gag^{-1} = g' \}
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. **Centralizers.** The centralizer of an element $a \in G$ is its stabilizer under the conjugacy action:
$$
C_G(a) = \{g \in G:ga=ag\}
$$
>i.e. the elements which commute with $a$ (as $ga = ag$ implies $gag^{-1}=a$, or invariance under conjugation). The set of elements in $G$ which commute with **all** other elements of $G$ is called the **center** of $G$:
$$
Z(G)\ (\text{or }C_G) = \{g \in G:\forall a, ga=ag\}
$$

From the expression $gag^{-1}$ alone - also the expression for a change of basis in linear algebra - we immediately observe some connection between conjugation and normal subgroups, themselves defined as subroups $H < G$ where $gHg^{-1} = H$. And indeed; not only do conjugation actions provide the most natural way for a group to act on normal subgroups, normal subgroups themselves are *formed* out of conjugacy classes.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. If $H \triangleleft G$, then $G$ acts on $H$ through a conjugation action.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

We've already proven above that the conjugation action satisfies properties of identity and multiplicativity; by definition of a normal subgroup we have $ghg^{-1} \in H$ for any $g \in G$, so the conjugation action defined by
$$
\phi(g)(h) = ghg^{-1}
$$
is also an element of $H$, thus satisfying closure. $\square$

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. If $H \triangleleft G$, then $H$ is a union of some number of conjugacy classes of $G$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

By definition of a normal subgroup, we have $ghg^{-1} \in H$ for every $h \in H$ and $g \in G$; this exactly matches the definition of a conjugacy class $\text{ccl}(h)$, and so $\text{ccl}(h) \subset H$ for every $h \in H$. Thus, $H$ is the union of conjugacy classes of its elements.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. A group $G$ acts on the set of subgroups of $G$, denoted $X$, through a conjugation action.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

We need to prove that the function defined by
$$
\phi(g)(H) = gHg^{-1}
$$
for $g, g_1 \in G$ and $H \in X$, where $gHg^{-1}$ is understood to be a coset, is a well-defined group action. If $H$ is a subgroup of $G$, then for any $a, b \in H$, we have $a\cdot_G b^{-1} \in H$; therefore, $gHg^{-1}$ has the property that
$$
(gag^{-1}) \cdot_G (gbg^{-1}) = g(ab)g^{-1} \in H
$$
but $g(ab)g^{-1}$ is an element of $gHg^{-1}$ as $ab \in H$, so $gHg^{-1}$ is also a subgroup of $G$. The identity property and the multiplicativity property are inherited from the conjugation action itself. $\square$

In particular, we call the stabilizer of this group action the

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Normalizer**. For a subgroup $H < G$, call the **normalizer** of $H$ the set of all elements $g \in G$ such that the conjugate of $H$ by $g$ is still $H$: in other words, it is the stabilizer of $H$ under the conjugation action
$$
N_G(H) = \{g \in G: gHg^{-1} = H\}
$$
> or the set of all elements $g \in G$ such that $H$ can be seen as a normal subgroup. The normalizer of a normal subgroup is the entire group $G$.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. The normalizer $N_G(H)$ of a subgroup $H< G$ is itself a subgroup of $G$; seen this way, it is the largest subgroup of $G$ which $H$ is a normal subgroup.

> <span style="background-color: #1eff12; color: black;">Proof</span>. If $a, b \in N_G(H)$, then we have
$$
ab^{-1}(H)(ab^{-1})^{-1} = ab^{-1}(H)ba^{-1}=a(b^{-1}Hb)a^{-1}
$$
> where $b^{-1}Hb$ and $aHa^{-1}$ are both $H$ by definition of $b \in N_G(H)$ and thus $b^{-1} \in N_G(H)$, resulting in
$$
a(b^{-1}Hb)a^{-1} = aHa^{-1} = H
$$
> and thus $ab^{-1} \in N_G(H)$, proving it is a subgroup. $\square$

***

## Cauchy's Theorem

As a final farewell to group actions, we prove

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Cauchy's Theorem.** Let $G$ be a finite group and $p$ be a prime number that divides the order of $G$, $|G|$. Then $G$ has at least $p-1$ elements of order $p$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

**TL;DR**: Define a set of elements $X = \{(g_1, g_2, ..., g_p)\}$ based on $G$ with the property that $g_1g_2...g_p = e$; if $g_1 = g_2 = ... = g_p = g \in G$, then $g^p = e$ and so $g$ is of order $p$ or $1$ (if $p$ is prime). Consider a group action that takes the form of a permutation on $X$ and use the orbit-stabilizer theorem to find the number of elements of orbit size $1$, i.e. are unpermutable and thus have the form $(g,g,g,g,...,g)$. These elements $g$, excepting the identity, have order $p$ in $G$.

Let $G$ have order $n$, and suppose that a prime number $p$ divides $n$. Define the set $X$ as a subset of the group $G^p = G \times G \times ... \times G$, the direct product of $G$ with itself $p$ times, as follows:
$$
X = \{(g_1, g_2, ..., g_p) \in G^p: g_1g_2...g_p = e_G\}
$$
i.e. all elements in $G^p$ whose product is the identity of $G$. Due to group inverses, the first $p-1$ elements of $G$ within any element of $X$ can be chosen arbitrarily; the last element $g_p$ is thus defined uniquely by
$$
g_p = (g_1g_2...g_{p-1})^{-1}
$$
which always exists as an element of group $G$. As such, there are a total of $n^{p-1}$ unique elements of the set $X$: $p-1$ elements to choose, and $n$ elements total in group $G$ to choose from without replacement. 

Now define the group action of the cyclic group $C_p$, generated by the powers of a generator element $c$, on an element $x = (g_1, g_2, ..., g_p) \in X$ as a single application of a $p$-cycle on $x$:
$$
\phi(c^k) = (g_1g_2...g_p)^k(g_1, g_2, ..., g_p)
$$
where $(g_1g_2...g_p)$ denotes a $p$-cycle in the sense of a permutation, i.e.
$$
(g_1g_2...g_p)(g_1, g_2, ..., g_p) = (g_2, ..., g_p, g_1).
$$
This satisfies the conditions for a group action because it is innately multiplicative (due to the composition of cycles), has $\phi(c^0) = \phi(e)$ equalling the identity permutation, and maps from $X$ to $X$ as any permutation of an element of $x$ still multiplies to the identity of $G$. 

By the Orbit-Stabilizer Theorem, the size of the orbit of any $x \in X$ under this group action multilied by the size of its stabilizer is the size of $C_p$, which is $p$:

$$
|\text{orb}(x)||\text{stab}(x)| = p
$$

As $p$ is prime, we have either $\text{orb}(x) = 1$ or $\text{orb}(x) = p$. Suppose that in $X$, there are $r$ elements with orbits of size $1$ and $s$ elements with orbits  of size $p$; the orbits of elements of $X$ partition $X$, yielding
$$
r + sp = n
$$
But $n$ is a multiple of $p$, so we have
$$
r + sp = kp
$$
for some $k > s$ (as the identity element of $X$, given by $(e,e,e,e,e,...,e)$, has an orbit of size $1$ as it cannot be permuted, and so $r$ is positive and $kp$ is larger than $sp$). THus we have
$$
r = (k-s)p
$$
with $k-s$ at least $1$; there are at least $p$ elements with an orbit of size $1$ under a group action by cyclic group $C_p$. This means that they are invariant under any permutation; in other words, these elements are of the form
$$
(a,a,a,a,...,a)
$$
and by definition of $X$ - the product of all elements of $x \in X$ yields the identity of $G$, $e_G$ - we have
$$
a \cdot a \cdot ... \cdot a = a^p = e_G.
$$
The identity of $G$ itself is one of these $p$ elements, but it has order $1$; if $a^p = e_G$, we can be sure that no positive integer $k$ has $a^k = e_G$ because $p$ is a prime and so $k$ cannot divide $p$, unless $k$ is $1$. The identity is the only element with order $1$ in $G$, and so there are (at least) $p-1$ total elements with order $p$. $\square$