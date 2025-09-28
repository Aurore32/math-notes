---
id: bd1lv7h4pgqw8181od9557u
title: Lagrange's Theorem
desc: ''
updated: 1749209448808
created: 1745392330013
nav_order: 2
---

> One of Lagrange's greatest scientific discoveries was the Principle of Least Action, which states that objects tend to take the path requiring the least effort. Lagrange is a brilliant scientist and all, but I could've told you the same thing just by looking at my Sunday afternoon schedule. 

## Properties of cosets

Recall from our previous discussion that cosets represented a way of expressing how the structure of a subgroup could form the entire group: a subgroup's structure is embedded within the structure of the larger group, and through the innate symmetries present within the structures of groups, cosets reveal how the larger group's structure is comprised of many repeated copies of the subgroup's.

In order to formulate this properly, though, we have to prove the following three things.

1. > <span style="background-color: #12ffd7; color: black;">Lemma</span>. The (left) cosets of any subgroup $G$ of a group $H$ span $H$; in other words, for any element $h \in H$, there is at least one such coset $aG$ such that $h \in aG$.

    > <span style="background-color: #1eff12; color: black;">Proof</span>.

    By the definition of a subgroup, $e \in G$; as such, the coset $hG$ includes the element $eh = h$ and $h \in hG$. This means that the cosets of a subgroup are able to represent the entire group $H$.

2. > <span style="background-color: #12ffd7; color: black;">Lemma</span>. Let $H$ and $G$ be as above. As long as two cosets $aG$ and $bG$ for $a, b \in H$ share a single element, $aG$ and $bG$ are identical cosets.

    > <span style="background-color: #1eff12; color: black;">Proof</span>. 

    Let $k \in aG$ and $k \in bG$. By definition of a coset, for some $g_1, g_2 \in G$ we have $a g_1 = b g_2 = k$; as such, we have 
    $$
    b^{-1} a = g_2 g_1^{-1} \in G
    $$
    by group closure, and
    $$
    a^{-1} b \in G
    $$
    by group inverses.
    
    To show that two sets are identical, we must prove a bijection between the sets. For every $g \in G$, we have $a^{-1} bg \in G$ by closure; as such, the coset $aG$ contains all elements of the form $aa^{-1}bg = bg \in bG$ and thus $aG$ maps completely onto $bG$. Conversely, $b^{-1}ag \in G$ for all $g \in G$ and thus $bG$ completely contains all elements of the form $bb^{-1}ag = ag \in aG$. As the two cosets completely contain one another, they are necessarily identical.

    Conversely, if the two cosets are identical, then the condition 
    $$
    b^{-1} a \in G
    $$
    is satisfied via $k \in aG$ and $k \in bG$ yielding $ag_1 = bg_2$.

    > A corollary of this is that, if $a \in G$, then the coset $aG$ is $G$ itself unchangeed as $aG$ has at least one common element with $eG$, the identity coset.

    This implies two things. First, the cosets of a subgroup can be described by different *representatives*: $aG$ and $bG$ with $a \neq b$ could be different names for the exact same coset. Second, even though a coset is not uniquely named, the unique cosets of a subgroup are non-overlapping (or *disjoint*): two cosets are either identical, or do not intersect at all.

    Now all that's left to prove is 

3. > <span style="background-color: #12ffd7; color: black;">Lemma</span>. The cosets of a subgroup $G$ all have the same size: that of $G$ itself.

    > <span style="background-color: #1eff12; color: black;">Proof</span>. 
    
    By definition, a coset $aG$ with $a \in H$ is the set $\{ag\ |\ g \in G\}$. If none of the $ag$s thus defined are equal to one another, then $aG$ will have the same number of elements as $G$. 
    
    Suppose for the sake of contradiction that for some $g_1 \neq g_2 \in G$, we have $ag_1 = ag_2$; as such $a = ag_2g_1^{-1}$, which would necessarily imply $g_2g_1^{-1} = e$ and $g_2 = g_1$ as the identity is unique. This is a contradiction, and no two $ag$s are thus equal.

    (Alternatively, the function $f(g) = ag$ maps $G$ completely to $aG$; however, this function is also invertible, with $f^{-1}(g) = a^{-1}g$ mapping $aG$ to $G$. A bijection between the two sets is thus established, showing they have the same cardinality.)

## Lagrange's Theorem

> This section is the section entitled "Lagrange's Theorem" in the page entitled "Lagrange's Theorem" in the chapter entitled "Lagrange's Theorem". Hopefully you don't hold too much of a Lagrudge against me for this.

The culmination of all of the above properties leads us to the following two results:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The left cosets of a subgroup $G$ of $H$ **partition** $H$; they divide $H$ into sets $H_1, H_2, ..., H_n$ such that $H_1 \cup H_2 \cup ... \cup H_n = H$ and for any $i, j = 1, ..., n$, we have $H_i \cap H_j = \emptyset$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. The partition follows naturally from the three lemmas proven above: the cosets of $G$ are of equal size, have null intersection, and completely span $H$.


and, consequently,

> <span style="background-color: #12ffd7; color: black;">Theorem</span> (the big one!): **Lagrange's Theorem.** If $G$ is a subgroup of $H$, then the size of $G$ divides $H$ (in the sense of $|G|$ being a factor of $|H|$.) 

> <span style="background-color: #1eff12; color: black;">Proof</span>. Each coset of $G$ has size $|G|$, and the cosets of $G$ partition $H$. Thus the size of $H$ is 
$$
|H| = |G| + |G| + ... + |G|
$$
> which is an integer multiple of $|G|$. (Nice job with your two-line big-boy proof, Mr. Lagrange.)

In particular, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **index** of a subgroup $G$ of a group $H$, denoted $|H: G|$, is defined as $\frac{|H|}{|G|}$.

Lagrange's Theorem has several important consequences, one of which is the fact that they dramatically narrow down the potential candidates of subgroups of any group $H$: if the order of $H$ is prime, for instance, we know that the order of any subgroups of $H$ are either $|H|$ - in which case the subgroup is $H$ itself - or $1$, in which case the subgroup is the unimpressive and disappointing $\{e\}$. Other corollaries include

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. The order of an element $g$ of a finite group $G$ divides $|G|$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. We know that finite groups have elements of finite order; if an element $g$ had infinite-order, then there would be an infinite number of elements generatable from $g$ and the group $G$ would thus be infinite, not finite. As such, the group of elements $H = \{g^a\ |\ a = 0, 1, ..., \text{ord}(g) - 1\}$ forms a finite subgroup of $G$; $|H| = \text{ord}(g)$, and thus by Lagrange's Theorem we have $\text{ord}(g)$ dividing $|G|$.

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. For any finite group $G$ and $g \in G$, $g^{|G|} = e$: the exponent of $G$ divides $|G|$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. By the above, $|G| = k\ \text{ord} (g)$ for some positive integer $k$ and any $g \in G$; thus $g^{|G|} = (g^{\text{ord} (g)})^k = e^k = e$ by definition of $\text{ord}(g)$.

(The above arguments have been limited to left cosets; however, every one of the above properties - equal partitions, Lagrange's Theorem, the index - is true for right cosets as well!)
