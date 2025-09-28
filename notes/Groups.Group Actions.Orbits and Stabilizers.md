---
id: te6kuv5nxto47bx4vhu4z0y
title: Orbits and Stabilizers
desc: ''
updated: 1745849971642
created: 1745848360627
nav_order: 2
---

> (Insert really terrible yo mama joke about orbits here)

Orbits and stabilizers represent analogues to a function's range and its fixed-points for group actions. In particular, the two relate together in a way that gives us insight into the sizes of groups that act on particular sets.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **orbit** of an element $x \in X$, denoted $\text{orb}(x)$, is the set of all elements that $x$ can be mapped to by a group action from $G$ on $X$ represented by the homomorphism $\phi$:
$$
\text{orb}(x) = G(x) = \{y \in X\ |\ \phi(g)(x) = y,\ g \in G\}
$$

> Additionally, call the action defined above **transitive** if the orbit of all $x \in X$ is the entire set $X$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **stabilizer** of ane element $x \in X$, denoted $\text{stab}(x)$, is the set of all $g \in G$ that keep $x$ the same under the group action $\phi$ (as above).

$$
\text{stab}(x) = G_x = \{g\ |\ \phi(g)(x) = x,\ g\in G\}
$$

Incidentally, "stab $x$" is also what my sixth-grade self wanted to do after getting assigned one too many algebra worksheets for homework.

Just as the image and kernel of a homomorphism form subgroups, we have

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. The stabilizer of $x$ is a subgroup of $G$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $a, b \in \text{stab}(x)$. Then the element $a \cdot_G b^{-1}$ acts on $x$ via $\phi$ as follows:
$$
\phi(a\cdot_G b^{-1})(x) = \phi(a)\phi(b^{-1})(x) = \phi(a)(x) = x
$$
as $\phi(b^{-1})(x) = \phi(b)^{-1}(x) = x$ via
$$
b \in \text{stab}(x) \iff \phi(b)(x) = x \iff x =\phi(b)^{-1}(x) 
$$
by definition of an inverse. Thus $a \cdot_G b^{-1} \in \text{stab}(x)$. $\square$


> <span style="background-color: #12ffd7; color: black;">Lemma</span>. The orbits of all elements $x \in X$ partition $X$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

The definition of a partition is twofold:
1. The unions of the orbits of different $x$ is $X$. By definition, $\text{orb}(x)$ contains the element $\phi(e)(x) = x$ and so each orbit of $x$ contains $x$ itself. The union of all $x$ forms the entire set $X$.
2. The orbits of $x \in X$ do **not** have to be of the same size, but they have to be disjoint: the intersection of two orbits is the null set. Suppose that $a \in \text{orb}(x)$ and $a \in \text{orb}(y)$ for $x \neq y \in X$. Then we have
$$
a = \phi(g_1)(x) = \phi(g_2)(y)
$$
And thus
$$
\phi(g_2)^{-1}\phi(g_1)(x) = \phi(g_2^{-1}\cdot_G g_1)(x) = y
$$
yielding
$$
y \in \text{orb}(x)
$$
by definition. Thus for any $w \in \text{orb}(y)$, we have
$$
w = \phi(g)(y) = \phi(g)\phi(g_2^{-1}\cdot_G g_1)(x) \in \text{orb}(x)
$$
and $w \in \text{orb}(x)$; this means that $\text{orb}(y) \subset \text{orb}(x)$, but the same argument in reverse establishes $\text{orb}(x) \subset \text{orb}(y)$. $\square$

***

Now here's the big one. The larger the stablizer of an element $x \in X$, the lower the number of elements $g \in G$ that can move it around via the group action; and the lower the number of elements that move $x$ around, the lower the number of possibilities for where $x$ can be moved - i.e. the size of the orbit of $x$. As such, we expect that the size of the orbit is "inversely proportional" - in some vague, informal sense - to the size of the stabilizer; and indeed

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. (THE BIG ONE.) **Orbit-Stabilizer Theorem**, ~~named after co-discoverers John Orbit and Edward Stabilizer in 1887.~~ Let a group $G$ act on a set $X$ by means of a group action. Then the size of the orbit of an element $x \in X$ under that group action multiplied by the size of the stabilizer of $x$ is the size of $G$:
$$
|\text{orb}(x)||\text{stab}(x)| = |G|.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

**Proof sketch**. When a proof needs a TL;DR right before it, you know it's some hardcore stuff. We utilize Lagrange's Theorem along with the fact that $\text{stab}(x)$ is a subgroup of $G$ to obtain
$$
|\text{stab}(x)||G:\text{stab}(x)| = |G|
$$
where $|G:\text{stab}(x)|$ is the index of $\text{stab}(x)$, equal to the number of unique cosets formed by $\text{stab}(x)$. Comparing with the equation above necessitates showing that $|G:\text{stab}(x)| = |\text{orb}(x)|$, which can be demonstrated via a bijection between the cosets of $\text{stab}(x)$ and the elements of $\text{orb}(x)$.

To prove this bijection, we require

1. Every left coset of $\text{stab}(x)$ corresponds to exactly one element of $\text{orb}(x)$. Let $g\ \text{stab}(x)$ be a coset of $\text{stab}(x)$ with $g \in G$; any element $gh \in g\ \text{stab}(x)$ has 
$$
\phi(gh)(x) = \phi(g)\phi(h)(x) = \phi(g)(x)
$$
as $\phi(h)(x) = x$ by definition of the stabilizer. Thus the left coset $g\text{ stab}(x)$ corresponds to $\phi(g)(x)$, an element of $\text{orb}(x)$.

2. Every element of $\text{orb}(x)$ corresponds to exactly one element of $\text{stab}(x)$: $\phi(g)(x)$ corresponds only to $g\ \text{stab}(x)$, and no other coset. Suppose that an element $g'h \in g'\text{ stab}(x)$ with $g' \neq g$ has
$$
\phi(g' h)(x) = \phi(g)(x) \iff \phi(g') = \phi(g)
$$
And so
$$
\phi((g')^{-1}g) = e
$$
and thus
$$
\phi((g')^{-1}g)(x) = x,\ (g')^{-1}g \in \text{stab}(x)
$$
and as such
$$
g'\ \text{stab}(x) = g'(g')^{-1}g\ \text{stab}(x) = g\ \text{stab}(x)
$$
establishing the bijection. $\square$