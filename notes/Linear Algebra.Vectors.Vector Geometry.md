---
id: 2r2el4g77gk10wt5mm3q6bm
title: Vector Geometry
desc: ''
updated: 1734857996337
created: 1734854557955
nav_order: 8
---
## Spherical trigonometry
Picking up where we left off:
> <span style="background-color: #ffb812; color: black;">Proposition</span>. $\mathbf{(a\times b)\cdot (a\times c)= (a\cdot a)(b\cdot c)-(a\cdot b)(a\cdot c)}$.

![alt text](image-2.png)

Consider points $A$, $B$, $C$ on the surface of a unit sphere with radius 1 and origin $O$. Let $\mathbf{a,b,c}$ denote the position vectors of $A$, $B$ and $C$ relative to the origin $O$ respectively. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $\delta(A,B)$ denote the angle $\angle AOB$, in radians; $\delta(A,B)$ is also the arc length $\widehat{AB}$. We also have $\mathbf{a\cdot b} = |\mathbf{a||b|}\cos \delta(A,B)=\cos \delta(A,B)$ as $\mathbf{a,b}$ are unit vectors and have $|\mathbf{a|=|b|=1}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span> (Spherical cosine rule). For points $A$, $B$, $C$ on this sphere, we have $\cos \alpha \sin\delta(A,B) \sin\delta(A,C)=\cos\delta(B,C)-\cos\delta(A,B)\cos\delta(A,C)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Notice that the dot product
$$
(a\times b)\cdot (a\times c)
$$
> represents the angle $\alpha$ by means of
$$
\cos \alpha = \frac{(a\times b)\cdot (a\times c)}{|a\times b||a\times c|}
$$
> as $\alpha$ is the angle between the vectors outputted by the two cross products. Using the proposition above, we have
$$
\cos \alpha = \frac{(a\cdot a)(b\cdot c)-(a\cdot b)(a\cdot c)}{|a\times b||a\times c|}
$$
> with $a\cdot a = 1$ due to $a$ being a unit vector. This expression can be rewritten as
$$
\cos \alpha = \frac{\cos\delta(B,C)-\cos\delta(A,B)\cos\delta(A,C)}{\sin\delta(A,B)\sin\delta(A,C)}
$$
> resulting in the desired cosine rule.

This is the fundamental rule governing trigonometry on the surface of a sphere, and it has interesting implications for what triangles would look like in such a circumstance. For instance, say that the triangle is equilateral: $\cos\delta(A,B)=\cos\delta(B,C)=\cos\delta(A,C)=\delta$. We thus have
$$
\cos \alpha =\frac{\delta - \delta^2}{1-\delta^2}=1-\frac{1}{1+\delta}
$$
which is smaller than $\frac{1}{2}$, with $\alpha$ thus being greater than $60^{o}$ - except if $\delta = 1$, where $\delta(A,B)$ and every other angle would be 0 degrees (degenerating the triangle into a point). This also implies that the sum of angles in a spherical triangle exceeds 180 degrees.

## Lines
