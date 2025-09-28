> I ![alt text](./assets/images/SnapBG.ai_1743479810295.png){width: 25px} HOMO <br/><br/><br/><br/><br/><br/>morphisms

(Would totally buy a T-shirt with that on it, by the way.)

## Homomorphisms

> Yes, yes, everyone's heard the jokes: "local topologist orders a coffee and a donut, ends up biting the coffee mug" this, "local topologist wakes up, tries fitting their head through a fidget spinner for an hour, gets arrested for public nudity" that. But have you considered the fact that people with a single ear piercing are already homomorphic to a pretzel?

"Homomorphism" means "same shape": if two objects are homomorphic, they have the same underlying shape or structure - donuts and coffee mugs, each being characterized by only having a single hole. In very basic and blasphemously un-rigorous terms, we begin our definition with this notion in mind:

> <span style="background-color: #03cafc; color: black;">Definition</span> (but not quite yet.) A homomorphism is a comparison - or, in slightly fancier math-speak, a map - from one thing to another that establishes how these two things have the same underlying structure.

The "things" in question could be any two objects that has ever existed, as long as they have identical underlying structures; and the map that establishes the homomorphism is simply any action that connects the two objects. A sphere and a coffee mug, by means of deformation; the integers to the rationals, by means of division; the frog to the handsome prince, by means of true love's kiss. 

In our case, though, we are concerned with groups; and more specifically, we are concerned with **preserving the structures** of groups. So what does the structure of a group entail? ~~(Based on the number of discord groups I've been in, I'd bet on unitary dictatorship.)~~

![alt text](./assets/images/image-61.png) 

Consider the cyclic group of integers $\text{mod }3$: the set $\{0, 1, 2\}$, nothing more. The **structure** of this group is given by how the elements of the group interact with each other: $1$ and $2$ combine to form $0$, $2$ and $2$ to form $1$, and so on. 

In other words, the elements themselves aren't important; what matters is the relationship between them. So the question to be asked is: if we replace $0, 1$ and $2$ with $a, b$ and $c$ respectively (and, it must be emphasized, in that order), do we still preserve the same set of relationships - that $1 +2 = 0$ and so $b + c = a$, and everything else besides?

This leads us to our first proper definition of what a group homomorphism entails.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The elements of a group $(G, \cdot_G, e_G)$ combine with each other through the binary operation $\cdot_G$: to see how $a, b \in G$ interact, consider $a \cdot_G b$. These combinations form what are called the **underlying structure** of $G$. <br/><br/>
> Suppose there exists another group $(H, \cdot_H, e_H)$, with its own binary operation and identity element. Call $H$ and $G$ **homomorphic** if there is a map $\phi$ that takes any three elements $g_1, g_2, g_3 \in G$ to three elements $h_1, h_2, h_3 \in H$ and preserves the relationship between them: that is, if $g_1 \cdot_G g_2 = g_3$, then $h_1 \cdot_H h_2 = h_3$.

Slightly more elegantly: there is a function $\phi$ that takes every element in $G$ to some element in $H$ such that $g_1 \cdot_G g_2 = g_3$ implies $\phi(g_1) \cdot_H \phi(g_2) = \phi(g_3)$. Even more elegantly: "show me your true form!"

With the above description in hand, call $\phi$ the **homomorphism** that maps $G$ to $H$.

***

> <span style="background-color: #03cafc; color: black;">Examples</span>.
1. $\phi(x) = x$, $x \in G$ is a homomorphism from $G$ to $G$. (Cool.)
2. $\phi(x) = x$, $x \in H$ is a homomorphism from $H$ to $G$ if $H \leq G$. (Cool.)
3. As seen from the multiplication table above, $\phi(x) = e^{x\frac{2\pi i}{n}}$ is a homomorphism from the cyclic group comprised of numbers $\text{mod }n$ and the cyclic group of rotational symmetries of an $n$-gon.
4. $\phi(x) = \frac{mx}{n}$ is a homomorphism from the cyclic group $\text{mod }n$ to the cyclic group $\text{mod }m$, if $m = kn$ for some positive integer $k$.

***

The above definition of a homomorphism encompasses more than immediately meets the eye.

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. Suppose that $\phi$ is a group homomorphism between groups $(G, \cdot_G, e_G)$ and $(H, \cdot_H, e_H)$, denoted $\phi: G\to H$. Then the following two group axioms are preserved between $G$ and $H$:
1. **Identity:** $\phi(e_G) = e_H$. The homomorphism $\phi$ must map the identity of $G$ to the identity of $H$.
2. **Inverse:** $\phi(g)^{-1} = \phi(g^{-1})$ for $g \in G$, where the first inverse is taken with respect to $\cdot_H$ and the second with respect to $\cdot_G$. The homomorphism $\phi$ must map an inverse to the same inverse.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

1. **Identity.** For all $g\in G$, we have $\phi(g) \cdot_H \phi(e_G) = \phi(g\cdot_G e_G) = \phi(g)$ by definition of a homomorphism. As such, we write
    $$
    \phi(g) \cdot_H \phi(e_G) = \phi(g), \forall g \in G
    $$
    which leads to $\phi(e_G) = e_H$ by definition of the identity.

2. **Inverse.** Consider
    $$
    \begin{aligned}
    \phi(g \cdot_G g^{-1}) &= \phi(g) \cdot_H \phi(g^{-1}) \text{ by definition of $\phi$} \\
    &= \phi(e_G) \text{ by $g\cdot_G g^{-1} = e_G$} \\
    &= e_H \text{ by the above} \\
    \end{aligned}
    $$
    leading to $\phi(g^{-1}) = \phi(g)^{-1}$ by definition of the inverse.

## Isomorphisms

In the simplest terms, homomorphisms are structure-preserving maps from one group to another; but nowhere does it say that for two groups to be homomorphic, they have to be the same size or correspond exactly to one another. A homomorphism $\phi: G \to H$ is a function with domain equal to the set of $G$ by definition, but its *codomain* (range) need not be the entirety of $H$; a subset is enough. In visual terms, the structure of $G$ is *embedded* within $H$.

![alt text](./assets/images/image-62.png)

If instead we required the two groups to have the exact same size, and for $\phi$ to have its codomain equal $H$ - for there to be a *one-to-one* correspondence between $G$ and $H$, we would have

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Isomorphisms** are a one-to-one correspondence between groups: if a homomorphism $\phi$ is an invertible (one-to-one) function which has $G$ as its domain and $H$ as its codomain, call $\phi$ an **isomorphism** and write $G \cong H$.

Isomorphisms map two groups to one another **exactly**: the groups must have the exact same size (due to invertible functions being one-to-one by nature), and if $g$ is mapped to $h$ by an isomorphism $\phi$, then $h$ is mapped to $g$ by its inverse. Isomorphic groups reach the highest level of similarity between two groups without actually reaching equality: they have the same number of elements, and the relationships between these elements follow the same underlying structure. We also call the one-to-one mapping represented by $\phi$ a **bijection.**

## Image and Kernel

> <span style="background-color: #03cafc; color: black;">Definition</span>. Suppose that $G$ is homomorphic to $H$ via the homomorphism $\phi: G \to H$. Call the set represented by the codomain of $\phi$
$$
\text{Im}(\phi) = \{\phi(g)\ |\ g \in G\}
$$
> the **image** of $\phi$; and the set represented by all elements of $G$ that map to the identity of $H$
$$
\text{Ker}(\phi) = \{g \in G\ |\ \phi(g) = e_H\}
$$
> its **kernel**.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The image of $\phi$ is a subgroup of $H$; the kernel of $\phi$ is a subgroup of $G$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

By definition of the homomorphism $\phi$ and the above lemmas, $\phi(e_G) = e_H$, meaning that $\text{Im}(\phi)$ is non-empty. As such, we can apply our second lemma for confirming the existence of a subgroup. Consider $x, y \in G$ and $\phi(x), \phi(y) \in H$. We have
$$
\phi(x) \cdot_H \phi(y)^{-1} = \phi(x) \cdot_H \phi(y^{-1}) = \phi(x \cdot_G y^{-1})\in H
$$
making $\text{Im}(H)$ a subgroup of $H$.

Similarly, for $\text{Ker}(\phi)$ we know that $e_G \in \text{Ker}(\phi)$ from the above lemmas, making the kernel non-empty; supposing that $x, y \in \text{Ker}(\phi)$, we have
$$
\phi(x \cdot_G y^{-1}) = \phi(x) \cdot_H \phi(y^{-1}) = e_H \cdot_H (e_H)^{-1} = e_H
$$
and thus $x \cdot_G y^{-1} \in \text{Ker}(\phi)$, confirming that the kernel is a subgroup.

The notions of an image and kernel give us a useful way of confirming whether a homomorphism is an isomorphism.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. let $\phi: G \to H$ be a homomorphism from groups $G$ to $H$. $\phi$ is an isomorphism if and only if $\text{Im}(\phi) = H$ and $\text{Ker}(\phi) = e_G$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let's tackle the forward statement first. Suppose that $\phi$ is an isomorphism; thus $\phi$ is invertible, yielding 
$$
h = \phi(\phi^{-1}(h))
$$
for all $h \in H$; therefore the image of $\phi$ encompasses all of $H$. If an element $g\in G$ satisfies $\phi(g) = e_H$, then we have
$$
\phi^{-1}(\phi(g)) = \phi^{-1}(e_H) = e_G
$$
as we know that $\phi(e_G) = e_H$ by the isomorphism lemmas above. This provides the forward statement.

Conversely, let $\text{Im}(\phi) = H$ and $\text{Ker}(\phi) = e_G$. If $\text{Im}(\phi) = H$, then every element $h \in H$ can be written $h = \phi(g_h)$ for some $g \in G$. Now define a new function $\psi$, such that
$$
\psi(h) = g_h, \forall h \in H
$$
which satisfies $\phi(\psi(h)) = h$ by definition. To prove that $\psi$ is the inverse to $\phi$, we must prove that it also satisfies $\psi(\phi(g)) = g$ for all $g \in G$. We have
$$
\phi(g^{-1}\cdot_G \psi(\phi(g))) = \phi(g^{-1}) \cdot_H \phi(\psi(\phi(g))) = \phi(g)^{-1} \cdot_H \phi(g) = e_H
$$
and as such $g^{-1} \cdot_G \psi(\phi(g)) = e_G$ by the fact that $\text{Ker}(\phi) = e_G$, meaning that $g = \psi(\phi(g))$. This leads to $\psi = \phi^{-1}$, and thus to the fact that $\phi$ is invertible. $\square$

## A final word on cyclic groups

All this fuss about homomorphisms and isomorphisms allows us to study cyclic groups more closely: more precisely, the fact that its basic structure - a certain action, or *generator*, combining with itself to create the entire group - also underlies many other groups, or subgroups of many other groups.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. All cyclic groups $G$ are isomorphic to either the group $C_n$ (the group of rotational symmetries of an $n$-gon) or the *infinite-order cyclic group* $(\mathbb{Z}, +, 0)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

An isomorphism requires an invertible function $\phi$ that maps each element of $G$ to a unique element in $C_n$ (which has $n$ elements). As outlined by the theorem, there are two possible cases: either $G$ is isomorphic to a finite cyclic group, or to the infinite-order cyclic group $\mathbb{Z}$.

First consider the case that the group $G$ is finite, with $n$ elements including the identity; by definition of a cyclic group, suppose that $G$ has generator $a$: $G = \{a^0, a^1, ..., a^{n-1}\}$ with $a^n = e_G$. $n$ is thus the smallest natural number $k$ satisfying $a^k = e_G$; by definition we also have $a^{2n} = a^{3n} = ... = e_G$. Construct the homomorphism $\phi: C_n \to G$, with $C_n$ containing the elements $\{\omega^0, \omega^1, ..., \omega^{n-1}\}$ with $\omega = e^{\frac{2\pi i}{n}}$, such that
$$
\phi(\omega^k) = a^k
$$
for $k = 0, 1, ..., n-1$. This satisfies the basic condition for a homomorphism:

$$
\phi(\omega^{m} \cdot_C \omega^{n}) = \phi(\omega^{m+n}) = a^{m+n} = a^m \cdot_G a^n = \phi(\omega^m) \cdot_G \phi(\omega^n)
$$

Recall that for a homomorphism to be an isomorphism $C_{n} \to G$, two conditions are necessary and sufficient: first that the homomorphism $\phi$ has image equalling $G$, and second that $\phi$ has kernel $e_{C_n} = \omega^0$. 

The first condition is satisfied by construction; $\phi(\omega^k) = a^k$, and thus $\phi$ has an image encompassing all of $G$. Assume for the sake of contradiction that $\text{Ker}(\phi) \neq \{\omega^0\}$; then for some $0 \leq k \leq n-1$, we have $\phi(\omega^{k}) = a^{k} = e_G$ by construction of $\phi$. As  $n$ is the smallest natural number $k$ satisfying $a^k = e_G$, this reaches a contradiction; thus $\phi$ is an isomorphism.

If $G$ is instead infinite, consider the same homomorphism $\phi$, now from $(\mathbb{Z}, +, 0)$ to $G$ instead:
$$
\phi(k) = a^k
$$
for all $k \in \mathbb{Z}$. As above, this also satisfies the basic requirements for a homomorphism; the same argument involving $\text{Ker}(\phi)$ also reaches a contradiction, leading to $\phi$ being an isomorphism. $\square$

> <span style="background-color: #03cafc; color: black;">Definition</span>. For any group $G$ and a group element $g \in G$, define the **order** of $g$, denoted $\text{ord}(g)$, as the smallest number $n$ satisfying $g^n = e_G$. If no such number exists, we say that $g$ has **infinite order**: $\text{ord}(g) = \infty$.

The subset of $G$ generated entirely by powers of $g$ - $\{g^0, g^1, ..., g^n\}$ - forms a cyclic subgroup of $G$ that is isomorphic to $C_n$.