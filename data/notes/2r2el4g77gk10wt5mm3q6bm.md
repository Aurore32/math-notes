## Spherical trigonometry
Picking up where we left off:
> <span style="background-color: #ffb812; color: black;">Proposition</span>. $\mathbf{(a\times b)\cdot (a\times c)= (a\cdot a)(b\cdot c)-(a\cdot b)(a\cdot c)}$.

![alt text](./assets/images/image-2.png)

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

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The line through a point with position vector $\mathbf{a}$ and parallel to vector $\mathbf{t}$ has equation $\mathbf{x} = \mathbf{a} + \lambda \mathbf{t}$, where $\lambda$ is a constant. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. If $P$ denotes the point on the line, then the position vector of $P$ $\vec{OP}$ equals $\vec{OA} + \vec{AP}$ where $\vec{OA} = \mathbf{a}$ and $\vec{AP}$ is some vector in the direction of the line; hence, $\lambda \mathbf{t}$.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The equation of the same line can also be rewritten $\mathbf{(x-a)\times t = 0}$ where $\times$ denotes the cross product. This can be intuitively seen because the only case when two vectors have a cross product of zero is if one is zero, or if they are parallel; thus either $\mathbf{x=a}$ or $\mathbf{x-a}$ is in the direction of $\mathbf{t}$.

## Planes
> <span style="background-color: #ffb812; color: black;">Proposition</span>. The equation of a plane perpendicular to some unit vector $\mathbf{n}$ and passing through a point $\mathbf{a}$ is $\mathbf{(x-a)\cdot n} = 0$. This simply expresses the notion that a vector lying in the plane, $(\mathbf{x-a})$, is perpendicular to the normal vector $\mathbf{n}$.

This can also be rewritten $\mathbf{x\cdot n = a\cdot n}$.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The distance from the origin to the plane is equal to $\mathbf{x \cdot n = a \cdot n}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $Q$ be the point on the plane such that $\vec{OQ}$ is parallel to  $\mathbf{n}$. This is the perpendicular line extending from the origin to the plane, and thus it represents the minimum distance from the origin to the plane. Let $\vec{OQ} = d\mathbf{n}$ for some $d$. As $Q$ is on the plane, it satisfies
$$
(\vec{OQ}-\mathbf{a}) \cdot \mathbf{n} = (d\mathbf{n-a}) \cdot \mathbf{n} = d|\mathbf{n}| - a\cdot \mathbf{n} = 0
$$
> with $|\mathbf{n}|=1$ by $\mathbf{n}$ being a normal vector. Thus, $\mathbf{a\cdot n} = d$.

Note also that if $\mathbf{l}$ and $\mathbf{m}$ are two linearly independent vectors that lie in the plane, then any point on the plane can be expressed as
$$
\mathbf{x}=\mathbf{a}+\mu \mathbf{l}+\lambda \mathbf{m}
$$
where $\lambda$ and $\mu$ are real.

## Spheres and circles

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The equation of a generalized hypersphere in $n$ dimensions, with radius $r$ and center $\mathbf{a}$, (in 2D: a circle, in 3D: a sphere, in 4D and beyond: a hypersphere) is $\mathbf{|x-a|}=r,\ \mathbf{x} \in \mathbb{R^n}$. This encompasses the set of all points in $n$-space a distance $r$ away from $\mathbf{a}$.

## Vector equations

Equations involving vectors, the dot product and the cross product, such as $\mathbf{x - (x\times a)\times b = c}$, are often best solved through vector manipulation:
1. To make a vector $\mathbf{a}$ disappear on one side of the equation, take the cross product with $\mathbf{a}$ on both sides, as $\mathbf{a\times a} = 0$.
2. If two vectors are normal to one another, take their dot product.
3. Use vector identities such as the vector triple product to expand more complicated expressions.

