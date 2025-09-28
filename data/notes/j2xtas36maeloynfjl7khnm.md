## Generalizing the line integral

Since we're studying all these different types of integrals, and each one is a generalization or specification or manifestation or personification of the last, it's occasionally useful to understand exactly *how* they're all connected - and what parts they're generalizing off of one another.

A surface integral is a generalization of two types of integrals: an area integral, whose idea of integrating along infinitesimal areas $dA$ is generalized to two-dimensional surfaces in three dimensions, rather than in the two-dimensional plane, and a line integral, whose idea of taking directional slices along a curve is generalized to taking directional slices along a surface.

Let's take a look at how each of these generalizations operate. 

## Areas along a parametric surface

![alt text](./assets/images/image-21.png)

For an area integral, the area differential $dA = dx\ dy$ represented the process of splitting a region into infinitesimally small rectangular areas, each with length $dx$ and with $dy$. For a surface integral over a parametric surface $S = \mathbf{x}(u,v)$, we deal not with rectangular areas, but with *surface areas* along the $u$- and $v$-directions - much like how, over a curve $C$, we deal with arc length $ds$ instead of the differential $dx$ along a straight line.

There is zero guarantee that $u$ and $v$ are orthogonal; given a small increment along the $u$-axis $\delta u$ and along the $v$-axis $\delta v$, we can only guarantee that, at infinitesimal scales, the infinite sum of the parallelograms formed by the vector
$$
\mathbf{x}(u+\delta u, v) - \mathbf{x}(u, v)
$$
and the vector
$$
\mathbf{x}(u, v+\delta v) - \mathbf{x}(u,v)
$$
can approximate the surface area of $S$. The above two expressions look exactly like partial derivatives:
$$
\mathbf{x}(u+\delta u, v) - \mathbf{x}(u, v) = \frac{\partial \mathbf{x}}{\partial u} \ \delta u
$$
and, correspondingly,
$$
\mathbf{x}(u, v+\delta v) - \mathbf{x}(u, v) = \frac{\partial \mathbf{x}}{\partial v} \ \delta v.
$$
The area of the parallelogram formed by two vectors is the magnitude of the cross-product of the two vectors, and thus our expression for the surface area differential $dS$ is
$$
| \frac{\partial \mathbf{x}}{\partial u} \ \delta u \times \frac{\partial \mathbf{x}}{\partial v} \ \delta v|
$$
where $\delta u$ and $\delta v$ are scalars, and thus the above expression equals
$$
dS = |\frac{\partial \mathbf{x}}{\partial u} \times \frac{\partial \mathbf{x}}{\partial v}|\ du\ dv
$$
where the cross product equals our expression for the normal vector to the surface!

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **scalar area differential** for a surface $S$ parameterized as $\mathbf{x}(u,v)$ as
$$
dS = |\frac{\partial \mathbf{x}}{\partial u} \times \frac{\partial \mathbf{x}}{\partial v}|\ du\ dv
$$
> as opposed to the vector area differential (encountered later).

### Reparameterization invariance

Like the uniqueness of the arc length parameterization for line integrals, the above definition for the surface area differential is independent of the parameterization $(u,v)$ chosen for a surface.

Suppose we wish to re-parameterize the surface via alternative parameters $\bar{u}, \bar{v}$, assuming that each can be expressed as (scalar) functions of $u$ and $v$ (and vice versa). By the chain rule, we have
$$
\frac{\partial \mathbf{x}}{\partial \bar{u}} = \frac{\partial \mathbf{x}}{\partial u} \frac{\partial u}{\partial \bar{u}} + \frac{\partial \mathbf{x}}{\partial v} \frac{\partial v}{\partial \bar{u}}
$$
and
$$
\frac{\partial \mathbf{x}}{\partial \bar{v}} = \frac{\partial \mathbf{x}}{\partial u} \frac{\partial u}{\partial \bar{v}} + \frac{\partial \mathbf{x}}{\partial v} \frac{\partial v}{\partial \bar{v}}
$$
leading to 
$$
\begin{aligned}
|\frac{\partial \mathbf{x}}{\partial \bar{u}} \times \frac{\partial \mathbf{x}}{\partial \bar{v}}| &= (\frac{\partial \mathbf{x}}{\partial u} \frac{\partial u}{\partial \bar{u}} + \frac{\partial \mathbf{x}}{\partial v} \frac{\partial v}{\partial \bar{u}}) \times (\frac{\partial \mathbf{x}}{\partial u} \frac{\partial u}{\partial \bar{v}} + \frac{\partial \mathbf{x}}{\partial v} \frac{\partial v}{\partial \bar{v}}) \\
&= 0 + (\frac{\partial u}{\partial \bar{u}} \frac{\partial v}{\partial \bar{v}})|\frac{\partial\mathbf{x}}{\partial u}\times \frac{\partial\mathbf{x}}{\partial v}| - (\frac{\partial u}{\partial \bar{v}} \frac{\partial v}{\partial \bar{u}})\ |\frac{\partial\mathbf{x}}{\partial u}\times \frac{\partial\mathbf{x}}{\partial v}| + 0 \\
&= \frac{\partial(u,v)}{\partial(\bar{u},\bar{v})}|\frac{\partial\mathbf{x}}{\partial u}\times \frac{\partial\mathbf{x}}{\partial v}| \\
&= \frac{du\ dv}{d\bar{u}\ d\bar{v}}\ |\frac{\partial\mathbf{x}}{\partial u}\times \frac{\partial\mathbf{x}}{\partial v}|
\end{aligned}
$$
where the last two lines are due to the Jacobian, leading to
$$
|\frac{\partial \mathbf{x}}{\partial \bar{u}} \times \frac{\partial \mathbf{x}}{\partial \bar{v}}|\ d\bar{u}\ d\bar{v} = |\frac{\partial\mathbf{x}}{\partial u}\times \frac{\partial\mathbf{x}}{\partial v}|\ du\ dv.
$$

## Scalar fields

> <span style="background-color: #03cafc; color: black;">Definition</span>.
For a scalar field $\phi(\mathbf{x})$ and a parameterized surface $S = \mathbf{x}(u,v)$ defined over a region $D = \{(u,v): u_a < u < u_b,\ v_a < v < v_b\}$, define the **scalar surface integral** as the area integral
$$
\int_{v_a}^{v_b} \int_{u_a}^{u_b} \phi(\mathbf{x}(u,v))\ |\frac{\partial\mathbf{x}}{\partial u} \times \frac{\partial \mathbf{x}}{\partial v}|\ du\ dv
$$
> regardless of the parameterization $(u,v)$ considered. 

Note that taking $\phi = 1$ simply gives the surface area of the surface.

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the surface area of a sphere of radius $a$. 

I sure love it when calculus textbooks demonstrate the unadulterated power of calculus by overcomplicating statements in my fifth-grade textbook and irrevocably lifting the veil of innocence from my untarnished childhood forever.

Apply a parameterization in, big surprise, spherical coordinates: 
$$
\mathbf{x(\theta, \phi)} = (x,y,z) = \begin{bmatrix}
a\sin \phi \cos \theta \\
a \sin \phi \sin \theta\\
a \cos \phi
\end{bmatrix},\ 0 \leq \phi \leq \pi,\ 0 \leq \theta \leq 2\pi,
$$
leading to 
$$
dS = |\frac{\partial\mathbf{x}}{\partial \theta} \times \frac{\partial \mathbf{x}}{\partial \phi}| = |\begin{bmatrix}
-a\sin\phi\sin\theta \\
a\sin\phi\cos\theta \\
0
\end{bmatrix}\times \begin{bmatrix}
a\cos\phi\cos\theta \\
a\cos\phi\sin\theta \\
-a\sin\phi
\end{bmatrix}| = a^2\sin \phi\ d\theta\ d\phi
$$
(Source: trust me bro/sis/gender-neutral-term-of-vitriolic-affection.) 

The surface integral that leads to the surface area can be formulated as
$$
\begin{aligned}
\int_{0}^{\pi} \int_{0}^{2\pi}a^2\sin\phi\ d\theta\ d\phi \\
= 2\pi a^2 \int_{0}^{\pi}\sin\phi\ d\phi \\
= 4\pi a^2
\end{aligned}
$$
I can't believe it took these calculus nerds two semesters in Cambridge to figure out what I knew ever since fourth grade.

## Vector fields

As promised, we now define the vector-valued analogue to the scalar area differential $dS$:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **vector area differential**, denoted $d\mathbf{S}$, for a surface $S$ parameterized by $\mathbf{x}(u,v)$ as
$$
d\mathbf{S} = (\frac{\partial \mathbf{x}}{\partial u}\times \frac{\partial \mathbf{x}}{\partial v})\ du\ dv
$$
with the cross-product term no longer behind bars, having served its sentence for first-degree murder of $k\mathbf{x}$ in the presence of $\mathbf{x}$. In contrast to $dS$, $d\mathbf{S}$ is a vector with direction pointing in the normal to the surface and magnitude $dS$; it thus encodes both surface area and surface direction within it, and that fact allows us to calculate

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Flux**. Suppose that the vector field $\mathbf{F(x)}$ denotes the **velocity field** of a fluid, i.e. its direction and magnitude of flow at every point; we define the **flux** of the fluid about a surface $S$ as the amount of fluid crossing the surface $S$ per unit time.

This definition of flux is made calculable through the surface integral by two relevant facts:

1. The direction pointing out of the surface at a point is given by $d\mathbf{S}$ (pointing in the direction of the normal vector to the surface);
2. The flow of a fluid $\mathbf{F}$ in the direction $\mathbf{n}$ is given by the dot product $\mathbf{F\cdot n}$.

All of this leads to the following formulation for flux, given a surface $S$, a velocity field $\mathbf{F(x)}$, and a region $D$ in the $u-v$ plane over which the surface lies:
$$
\int_D \mathbf{F\cdot dS}
$$
We can, of course, speak of flux even if the underlying vector field $\mathbf{F}$ does not describe fluid flow; *electric flux* and *magnetic flux* - the electric and magnetic fields passing through a surface, respectively - are good examples in this vein.

