---
id: bppjh6ro6ivkjzybl0218pg
title: Revisiting Surfaces
desc: ''
updated: 1751784703744
created: 1741253401067
nav_order: 1
---
## Review (See [[Vector Calculus.Curves and Surfaces.Surfaces]])

A few points of importance before we journey forth towards surface integrals.

### Defining surfaces

A surface can be described in all of the following ways:
- **Explicitly**, in the form $z = f(x,y)$, as a two-dimensional surface in three-dimensional space $\mathbb{R}^3$.
- **Implicitly**, in the form $F(x,y,z) = 0$, as a level set $w = 0$ to the function $F(x,y,z)=w$.
- **Parametrically**, as a vector-valued parametric function with two degrees of freedom $\mathbf{x} = \psi(u,v)$ for parameters $u$, $v$ that maps points in $\mathbb{R}^2$ to $\mathbb{R}^3$.

### Normal vectors to surfaces

- For implicit surfaces $F(x,y,z)=0$, $\nabla F$ provides the direction of the normal to the function at every point (as level curves $F = 0$ are curves where $F$ does not change, implying the directional derivative is zero, whereas the gradient is the direction that maximizes the directional derivative)
    - By convention, we normalize the normal vector via $\pm \frac{\nabla F}{|\nabla F|}$ with sign determined by *orientation* (see below).
- For parametric surfaces $\mathbf{x = \psi}(u,v)$, **define** the normal vector to the surface at point $(u,v)$ as the cross product
$$
\frac{\partial \psi}{\partial u}\times \frac{\partial \psi}{\partial v}
$$
where $\psi_u$ provides the tangent vector to the surface in the $u$-direction, while $\psi_v$ provides the tangent vector in the $v$-direction; the normal vector is thus in a direction parallel to two tangent vectors to the surface. 
- Note that in $\mathbb{R}^3$, the cross product is inherently signed (right-handed sets of vectors result in positive cross-products); however, the same is not true in higher-dimensional space.


### Boundaries to surfaces

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **boundary** to a surface is the piecewise-smooth curve that lies on its "edge"; taken entirely unrigorously, that means a point where there's some direction where you'll fall off the surface if you take an infinitesimal step. (In contrast, an **interior point** in the surface is where you can walk infinitesimally in any direction and still stay on the surface.

Examples of boundaries to surfaces: the edge of a swimming pool, the perimeter of a circle, and, if certain illuminaries are to be believed, Antarctica. 

Some surfaces have clear boundaries; the boundary to a disk is the circle that forms the perimeter of that disk. Other surfaces have no such boundaries; a hollow sphere is technically a surface, but its boundary is itself.

For a surface denoted $S$, one common notation for the boundary of the surface is $\partial S$; this arises from the following alternate definition for the boundary. 

Consider two solids $V_r$ and $V_{r+\epsilon}$ in $\mathbb{R}^3$; $V_r$ is the solid bounded by a surface $S$ (e.g. a hollow spheere bounds a sphere), while $V_{r+\epsilon}$ is the solid that is just *infinitesimally bigger* than $V_r$, e.g. through inflation via syringe pump injection of 0.1 $\text{mol}$ of helium gas. Then $V_{r+\epsilon}$ with $V_r$ removed - denoted $V_{r+\epsilon}\backslash V_r$ - yields the **edge** of $V_r$, and thus the boundary of $S$:
$$
\partial S = \lim_{\epsilon \to 0}\frac{1}{\epsilon}(V_{r+\epsilon} \backslash V_{r})
$$
e.g. a disk expanding ever-so-slightly minus the original disk yields a circle. In essence, $\partial S$ is our way of saying that the edge of a surface - the part which moves when the surface is inflated - is its boundary.

> According to the 60$ full-color textbook which I pirated off some shady Onion website and which has thus become my Holy Grail, there is a "deep" and "beautiful" reason, aside from the one given at present, for why this notation carries its meaning as the boundary to a surface. I'm guessing this is mathematician-speak for either one of two things: 

1. There *actually* is something deep and beautiful, but you won't get to know unless you take the optional *Infinite-Order Unorientability of Non-Riemannian Surfaces in Twnety-Dimensional Hyperspace* elective in the five-quadrillionth-femtosecond of Part XIV of your PhD in Differential Geometry, or
2. They're embarassed to admit that the notation is only used today because some French nerd called Pierre Cumsock le Partiale pretard je Logriouxoueuaux in the 1700s invented the symbol and it's obtained too much structural staying-power to be contested ever since.

> Or, on explaining the commutative identity of multiplication to third-graders: "you may rightfully ask why we use the word 'commutative' to describe the binary operation $\cdot$ in $\mathbb{R}^n$, if there are no non-commutative operations in fields identical to $\mathbb{R}^n$ up to isomorphism. There is a deep and beautiful reason behind this which will only be revealed in later courses."

A final note on the power of denoting boundaries as $\partial S$: note that the circumference of a circle of radius $r$, and thus area $\pi r^2$, is 
$$
\frac{d}{dr}\ \pi r^2 = 2\pi r
$$
and the same with a sphere of radius $r$, a hypersphere, etc. Coincidence? I think not.

The boundary of the boundary of a surface is the boundary of a curve, which is nothing. This concept can be succinctly expressed as $\partial^2 S = 0$, and even more succinctly expressed as "a really bad idea."

### Orientability

Basically: orientable surfaces are where you can start at one point on the surface, say "this direction is up", walk the entire way around the surface, and have the same direction be "up" the entire time. Unorientable surfaces, in contrast, are surfaces where you decide one direction is up at the beginning, walk all the way around, then suddenly discover that up has become down and fall off the surface in shock and horror as a result. 

The choice of "up" - i.e. which direction is **outside** the surface, and which direction is **inside** - determines whether we append a positive or negative sign to the normal vector at some point on the surface. If this choice is consistent as we walk smoothly through the surface, call the surface "orientable"; otherwise, call it ~~all sorts of demeaning names and Oriental slurs~~ "unorientable".

A sphere is orientable, while a M$\ddot{o}$bius strip is not.

> M$\ddot{o}$bius