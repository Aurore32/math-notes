---
id: yc98mxhtouq030oimyyhjdh
title: Group Actions
desc: ''
updated: 1749213915606
created: 1749213894329
nav_order: 1
---
## What are group actions?

At the very beginning of this course, we were instructed to de-abstractify groups by thinking of them as something that rotates a Rubik's Cube. (Rubik's Cubes were only invented in the 1970s, which means people in the 1960s probably learned group theory using disco balls.) Then we were taught the virtues of groups as abstract objects, where we shoved about $7^{10^{e^{69}}}$ different definitions of amusing words like "homomorphisms" down our throats and refused to acknowledge the existence of real-world things like triangles or cubes. 

Unfortunately, now we have to think of groups as something that rotates or flips or changes a real-world object again. This course is flip-flopping more than an American politician during election season, and it's cutting down on my already-limited will to live.

> I HAVE A THEORY. What if Abel, Galois, etc., etc., didn't die of stupid things like getting sick or going to a duel, but instead died out of disgust from studying group theory too much? I have a sample size of 2, so it's a scientifically-proven fact - group theorists all die tragically eaarly deaths.

The permutation group contains all the ways you could change the order of a set. The dihedral group contains all the symmetries of a polygon. When a group element is interpreted as a way to modify some object such that the remains *symmetric*, i.e. the modification preserves some structure of the object - the number of elements in a set, the space a polygon occupies - we call it a

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Group action.** A **group action** of a group $G$ on a set of $n$ elements $X$ (which may represent letters, numbers, the vertices of a polygon, etc., etc.) is a way to interpret every element of $G$ as a permutation of that set. More formally, it is the homomorphism
$$
\phi(g),\ \phi: G \to \text{Sym}(X)
$$
> where $\text{Sym}(X) = S_n$ is the symmetric group of $X$, containing all possible permutations of the $n$ elements of $X$. 

(A quick *nota bene*: "symmetry", i.e. "symmetric group", means in this context "something which maps a set onto itself" - i.e. keeping the stuff inside something exactly the same, though not necessarily the order. Just like what that one back-alley doctor did to my organs after an appendicitis surgery.)

For instance, suppose that $\{1,2,3\}$ represent the three vertices of a triangle placed upright in clockwise order, with $1$ at the top; then the element $e^{\frac{2i\pi}{3}}$, a rotation by 120 degrees counterclocckwise, would permute the set of vertices into $\{2,3,1\}$. Thus, it maps straightforwardly onto the permutation $(123)$; and so do all other elements of either the cyclic group $C_3$ or the dihedral group $D_6$. The simplest example of a group action is the *trivial action*: every element in $G$ maps to the "do-nothing" permutation. This is an action that says it's an action but does nothing in reality, which is what my mom says about me every weekend.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $\theta: G \times X \to X$, defined by $\theta(g,x) = \phi(g)(x)$ where $\phi$ is a function mapping from $G \to \text{Sym}(X)$, is a group action if and only if it satisfies the following three properties:
1. For all $g \in G$ and $x \in X$, $\theta(g,x) \in X$.
2. For all $x \in X$, $\theta(e_G, x) = x$.
3. For all $g,h \in G$ and $x \in X$, $\theta(gh,x) = \theta(g,\theta(h,x))$; the action $gh$ is equivalent to the action $h$ followed by $g$.


(Remember that $X$ is not a group; it is a set!)

> <span style="background-color: #1eff12; color: black;">Proof</span>.

In essence, our proof needs to show two things: 1) that the above three properties are necessary and sufficient to define a homomorphism $\phi$, and 2) $\phi$ maps from $G$ to $\text{Sym}(X)$. From the last property, we have
$$
\phi(gh)(x) = \phi(g)\phi(h)(x)
$$
and thus
$$
\phi(g\cdot_G h) = \phi(g) \phi(h)
$$


Now to prove that $\phi(g)$ maps to $\text{Sym}(X)$. Define $\phi(g)(x)$ as a function that maps $x$ to $\theta(g,x)$; by definition, this is a permutation on $X$ if it maps from the set $X$ to itself and is also invertible (a bijection, i.e. one-to-one - permuting every element in $X$ to another unique element). By rule (1), $\theta(g,x)$ maps to $X$; by rule (2), we have
$$
\theta(e_G, x) = \theta(gg^{-1}, x) = \theta(g,\theta(g^{-1}, x))=\phi(g)\phi(g)^{-1}(x) = x
$$
for any $g \in G$, thus making $\phi(g)^{-1}$ the inverse of $\phi(g)$ with $\phi(g)$ being invertible. Therefore, $\phi(g) \in \text{Sym}(X)$. 

The reverse statement results by a straightforward application of the definition of a homomorphism.

***

Similarly to homomorphisms, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Kernel** of an action. The **kernel** of a group action $G$ on $X$, given by a homomorphism $\phi: G \to \text{Sym}(X)$, is the kernel of the homomorphism $\phi$: it is all group elements $g$ taken to the identity permutation.

Note that an application of the **<sup>FIRST</sup> ISOMORPHISM THEOREM!!!** shows that, as $\phi$ is a homomorphism, the quotient group $G/\text{Ker}(\phi)$ is isomorphic to the image of $\phi$ (or, in other words, a subgroup of $\text{Sym}(X)$.)

Some group actions are perfectly suited to the set they act on: for instance, the dihedral group $D_{2n}$ is *isomorphic* to the symmetric group of the set of vertices of its corresponding $n$-gon. The kernel of these group actions is the identity alone, as they map perfectly to the symmetric group; call these group actions

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Faithful**. A group action is **faithful** if its kernel is exactly $\{e_G\}$.

This is why you should be cuddling in bed with Dummit and Foote's *Abstract Algebra* rather than with a romantic partner: girlfriends and boyfriends cheat, but (a few) group actions are always faithful. (Coincidentally, group actions are also the only action mathematicians are probably ever going to get.)
