---
id: 2y9mihsvutycobs1m8hlpmk
title: Orthogonal Curvilinear Coordinates
desc: ''
updated: 1751787157739
created: 1741341700157
nav_order: 3
---

## On the oxymoronic qualities of curvilinearity

*Curvilinear* is a seriously funny word; in fact, it might just be out-competing "thank God I'm an atheist", "fun fact", and "happy mathematician" as my favorite oxymoron of all time. Thankfully, though, orthogonal curvilinear coordinates do not satisfy the two conditions
1. It is curved, and
2. It is linear;

Instead, they satisfy the conditions detailed below.
> <span style="background-color: #03cafc; color: black;">Definition</span>. **Orthogonal curvilinear coordinates** are any coordinate system $\mathbf{x} = (x_1,x_2,x_3)$ in $\mathbb{R^3}$ where the tangent vectors to $\mathbf{x}$ along the $x_1$-, $x_2$-, and $x_3$-axes form a right-handed orthonormal basis:

$$
\frac{\partial \mathbf{x}}{\partial x_i}\cdot \frac{\partial\mathbf{x}}{\partial x_j} = \delta_{ij},\ (\frac{\partial \mathbf{x}}{\partial x_j})\times (\frac{\partial\mathbf{x}}{\partial x_k}) = \epsilon_{ijk}\frac{\partial\mathbf{x}}{\partial x_i}
$$
> e.g. $\partial_{x_2}\mathbf{x}\times\partial_{x_3}\mathbf{x} = \partial_{x_1}\mathbf{x}$.

Let's pick apart this definition one bit at a time.

First, for a coordinate system - say the standard Cartesian coordinate system $\mathbf{x} = (x,y,z)$ - what do the tangent vectors $\partial_x\mathbf{x}, \partial_y\mathbf{x}, \partial_z\mathbf{x}$ indicate? $\partial_x\mathbf{x}$, for example, denotes the change of $\mathbf{x}$ as we move a small step along the $x$-axis; in other words, it indicates the direction the $x$-axis is moving at the point $\mathbf{x}$ - more commonly known as the basis vector for the $x$-axis, $\mathbf{e}_x$. 

This clues us in a little bit: we can say much more generally that for any coordinate system $(x_1, x_2, x_3)$, the tangent vectors $\partial_{x_1} \mathbf{x}, \partial_{x_2}\mathbf{x}, \partial_{x_3}\mathbf{x}$ - upon normalization, as convention dictates - points us in the direction of the basis vectors $\mathbf{e_1, e_2, e_3}$ of the coordinate system at that point. In particular, we call

$$
h_{x_1} = |\partial_{x_1} \mathbf{x}|,\ h_{x_2} = |\partial_{x_2} \mathbf{x}|,\ h_{x_3} = |\partial_{x_3} \mathbf{x}|
$$
*scale factors* that tell us the change in length along each coordinate axis.

An **orthogonal curvilinear coordinate** system is thus one where the basis vectors form a right-handed perpendicular system (**orthogonal**), but not necessarily constant at every point (**curvilinear**). 

## Cylindrical and spherical polar coordinates

### Cylindrical coordinates

Take the cylindrical coordinate system in $\mathbb{R}^3$ as an example of orthogonal curvilinear coordinates:
$$
\mathbf{x} = (x,y,z) = (r\cos \theta, r\sin \theta, z)
$$
resulting in the tangent vectors
$$
\begin{cases}
\partial_r\mathbf{x} = (\cos \theta, \sin \theta, 0) \\
\partial_\theta \mathbf{x} = (-r\sin \theta, r\cos\theta, 0) = (-\sin \theta, \cos \theta, 0) \text{ (normalized)} \\
\partial_z \mathbf{x} = (0,0,1)
\end{cases}
$$
with associated scale factors $1, r, 1$ which are mutually orthogonal, but not at all constant. 

### Spherical coordinates

For the coordinate system $(r, \theta, \phi)$, we have
$$
\mathbf{x} = (x,y,z) = (r\sin\theta\cos\phi, r\sin\theta\sin\phi, r\cos\theta)
$$
and thus the tangent vectors and scale factors
$$
\begin{cases}
\partial_r \mathbf{x} = (\sin \theta \cos \phi, \sin \theta \sin \phi, \cos \theta), h_r = 1 \\
\partial_\theta \mathbf{x} = (r\cos\theta\cos\phi, r\cos\theta\sin\phi, -r\sin\theta), h_\theta = r \\
\partial_\phi \mathbf{x} = (-r\sin\theta\sin\phi, r\sin\theta\cos\phi, 0), h_\phi = r\sin\theta

\end{cases}
$$

## Differential operators in curvilinear coordinates

### The gradient and the gradient operator

Recall our previous *coordinate-independent* definition of the gradient $\nabla f$ of a scalar field $f(\mathbf{x})$ as being the vector satisfying
$$
df = \nabla f \cdot d\mathbf{x}
$$
for $d\mathbf{x} \to 0$, where $d\mathbf{x}$ is the vector given by
$$
d\mathbf{x} = (\partial_{x_1}\mathbf{x})\ dx_1 + (\partial_{x_2}\mathbf{x})\ dx_2 + (\partial_{x_3}\mathbf{x})\ dx_3
$$
i.e. the total change in position resulting from a small change along each of the coordinate axes.

This definition is valid for any coordinate system $(x_1,x_2,x_3)$, with orthogonal curvilinear basis $(\mathbf{e_1, e_2, e_3})$. For such a coordinate system, we also have
$$
df = (\partial_{x_1} f)\ dx_1 + (\partial_{x_2} f)\ dx_2 + (\partial_{x_3} f)\ dx_3
$$
with a comparison of coefficients yielding
$$
\begin{aligned}
(\partial_{x_1} f)\ dx_1 + (\partial_{x_2} f)\ dx_2 + (\partial_{x_3} f)\ dx_3 &= \nabla f \cdot ((\partial_{x_1}\mathbf{x})\ dx_1 + (\partial_{x_2}\mathbf{x})\ dx_2 + (\partial_{x_3}\mathbf{x})\ dx_3) \\
&= \nabla f \cdot (h_1 \mathbf{e_1}dx_1 + h_2\mathbf{e_2}dx_2 + h_3\mathbf{e_3}dx_3)

\end{aligned}
$$
combining all the above. Suppose now that the gradient vector $\nabla f$ can be written in the orthogonal curvilinear basis $(\mathbf{e_1, e_2, e_3})$ as 
$$
\nabla f = \alpha_1 \mathbf{e_1} + \alpha_2 \mathbf{e_2} + \alpha_3 \mathbf{e_3}
$$
By the orthonormality of this basis, we obtain the expression
$$
\begin{aligned}
&(\partial_{x_1} f)\ dx_1 + (\partial_{x_2} f)\ dx_2 + (\partial_{x_3} f)\ dx_3 = \nabla f \cdot (h_1 \mathbf{e_1}dx_1 + h_2\mathbf{e_2}dx_2 + h_3\mathbf{e_3}dx_3) \\
&= (\alpha_1 \mathbf{e_1} + \alpha_2 \mathbf{e_2} + \alpha_3 \mathbf{e_3})\cdot (h_1 \mathbf{e_1}dx_1 + h_2\mathbf{e_2}dx_2 + h_3\mathbf{e_3}dx_3) \\
&= \alpha_1 h_1 dx_1 + \alpha_2 h_2 dx_2 + \alpha_3 h_3 dx_3 \text{           \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ as $\mathbf{e_i\cdot e_i} = 1$} \\
\end{aligned}
$$
Comparing coefficients of $dx_1, dx_2$ and $dx_3$ now yield
$$
\begin{cases}
\alpha_1 = \frac{1}{h_1}(\partial_{x_1} f) \\
\alpha_2 = \frac{1}{h_2}(\partial_{x_2} f) \\
\alpha_3 = \frac{1}{h_3}(\partial_{x_3} f) \\
\end{cases}
$$
and thus 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **The gradient in general orthogonal curvilinear coordinates $(x_1,x_2,x_3)$.**
$$
\nabla f = \frac{1}{h_1}(\partial_{x_1} f)\mathbf{e_1} + \frac{1}{h_2}(\partial_{x_2} f)\mathbf{e_2} + \frac{1}{h_3}(\partial_{x_3} f)\mathbf{e_3}
$$
with the newfound scale-factor terms in the denominator intuitively understood as "scaling down" the rates of change in the $x_1$, $x_2$ and $x_3$ axes (for instance, a single step in the $x_1$ axis is worth $h_1$ length-units instead of $1$ length-unit, so $\partial_{x_1}f$ is $h_1$ times longer than it should be).

Associated with this is

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **The gradient operator in curvilinear coordinates**, derived from above as
$$
\nabla = \frac{\mathbf{e_1}}{h_1} \partial_{x_1} + \frac{\mathbf{e_2}}{h_2} \partial_{x_2} + \frac{\mathbf{e_3}}{h_3} \partial_{x_3}.
$$
The abstracted gradient operator can then be used to derive expressions for divergence and curl in different coordinate systems; unfortunately, this stone shall be left unturned until we introduce the Big Integral Theorems.
