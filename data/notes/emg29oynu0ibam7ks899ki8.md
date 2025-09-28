## The big ideas

### Generalizing Green's Theorem

Recall from the previous section that Green's theorem related *microscopic circulation* - the infinitesimal rotation of a vector field at every point in a region - to *macroscopic circulation*, the total rotation of that vector field around the boundary of the region.

![alt text](./assets/images/image-41.png)

> The big horse is the unholy amalgamation of all of the smaller horses.

Stokes' theorem generalizes such a concept to *any* region and *any* boundary surface (with one less dimension than the region) in any-dimensional space, no matter how curved or straight, or in polar or Cartesian coordinates. 

> An infinite number of infinitesimal horses are spinning in place in George Green's pasture, enclosed by a fence. Mr. Green asked the horses politely if they could move out of the pasture, so that he could go harvest some potatoes and carrots; the horses neighed, and POOF! One giant horse was all that was left behind, now tip-toeing its dainty feet around the top of the fence.<br/><br/>
This is where all the first-year undergraduate math students in the room erupted in raucous laughter, for they had just studied Green's theorem and wished to demonstrate their familiarity with the concept. "But wait," one particularly well-studied student chimed in. "What if the pasture wasn't flat at all - what if the horses were grazing on the side of a mountain, and not in the $xy$ Cartesian plane?"<br/><br/>
Of course, that student did not know that Green's theorem was applicable to non-Cartesian coordinate systems; but to explain that would be putting Descartes before the horse.

(Please clap.)

The statement goes:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Stokes' Theorem**. For $S$ a smooth surface in $\mathbb{R^3}$ and $C = \partial S$ its boundary curve, Stokes' theorem states for a smooth vector field $\mathbf{F(x)}$ that
$$
\int_S (\nabla \times \mathbf{F})\cdot \mathbf{dS} = \int_C \mathbf{F}\cdot d\mathbf{x},
$$

> where $d\mathbf{x} = (dx,dy,dz)$, and the orientations of $S$ and $C$ are assumed to be **compatible**, meaning that ~~$S$ doesn't bat for the other team~~ the chosen directions of the tangent to $C$, $\mathbf{t}$, and the normal to $S$, $\mathbf{n}$, have their cross product $\mathbf{t} \times \mathbf{n}$ pointing out of the surface.

![alt text](./assets/images/image-42.png)

In particular, this is satisfied if $\mathbf{n}$ is chosen to point out of the surface and $\mathbf{t}$ is chosen to be in the anticlockwise direction (pictured above).

### A new understanding of curl

Let's elaborate a little bit on Green's theorem again. Previously, we inferred - but by no means rigorously justified - the statement that the left-hand side of Green's theorem, featuring the integrand
$$
\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y},
$$
equalling the divergence of the normal vector to $\mathbf{F}$, was a measure of the rotation of the field - and thus a two-dimensional analogue to curl.

Stokes' theorem allows us to codify this notion a bit more clearly: the integrand of Stokes' theorem features curl, with
$$
\int_S (\nabla \times \mathbf{F})\cdot \mathbf{dS} = \int_C \mathbf{F}\cdot d\mathbf{x};
$$
As with the Divergence Theorem and its recontextualization of divergence, we may now consider an infinitesimal surface $S$ shrunken to contain only the single point in space $\mathbf{x}$. In this infinitesimal surface $S_x$, the curl is constant, and so the left-hand side surface integral is simply the surface area $S$ times the constant:
$$
\int_{S_x} (\nabla \times \mathbf{F})\cdot \mathbf{dS} = S\mathbf{n}\cdot (\nabla \times \mathbf{F})
$$
where $\mathbf{n}$ is the normal to the surface. 

As such, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Coordinate-free definition of curl**. For a vector field $\mathbf{F}$ and a normal vector $\mathbf{n}$ to an infinitesimal surface $S$ with area $|S|$, define the **curl** of $\mathbf{F}$ as the vector-valued function given by the limit
$$
\mathbf{n} \cdot (\nabla \times \mathbf{F}) = \lim_{S \to 0}\frac{1}{|S|}\int_{\partial S} \mathbf{F}\cdot \mathbf{dx}.
$$
We can interpret this as the curl $\nabla \times \mathbf{F}$ representing a **circulation density** (circulation in an infinitesimal point $\int_{\partial S}\mathbf{F\cdot dx}$, divided by the area of that point), and the dot product $\mathbf{n}\cdot (\nabla \times \mathbf{F})$ representing the circulation density in a particular plane normal to $\mathbf{n}$. 

This definition makes the intuition behind Stokes' theorem a little bit easier to understand, notwithstanding the fact that the definition is only true if Stokes' theorem is true in the first place. 

The curl $\nabla \times \mathbf{F}$ represents the local circulation at every point in a region; for two neighboring points, a clockwise circulation for one is an anticlockwise circulation for the other, and so the circulations cancel and cancel when integrated throughout the region until only the circulation on the very edge remains.

## Sketching a proof

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Stokes' Theorem is Green's Theorem across a general surface, rather than a surface lying in the $xy$-plane. Let $S$ be a smooth surface in $\mathbb{R^3}$ parameterizable by $S = \mathbf{x}(u,v)$; as such, our (non-Cartesian) coordinate plane of operations is the $uv$-plane rather than the $xy$-plane. Now all that remains is proving that Stokes' theorem is indeed valid for the $uv$-plane. 

Suppose that the curve $C$ bounding $S$ can be denoted $C = \mathbf{x}(u(t), v(t))$ for a parameter $t$ in the $uv$-plane. Then the circulation of a vector field $\mathbf{F}(x,y,z)$ around this boundary is
$$
\int_C \mathbf{F \cdot dx} = \int_C F_u\ du + F_v\ dv,
$$
where $\mathbf{dx} = \frac{\partial \mathbf{x}}{\partial u} + \frac{\partial \mathbf{x}}{\partial v}$ by definition, and so $F_u = \mathbf{F} \cdot \frac{\partial \mathbf{x}}{\partial u}$ and $F_v = \mathbf{F} \cdot \frac{\partial \mathbf{x}}{\partial v}$.

By Green's Theorem, we have
$$
 \int_C F_u\ du + F_v\ dv = \int_A (\frac{\partial F_v}{\partial u} - \frac{\partial F_u}{\partial v})\ du\ dv
$$
where $A$ is the area corresponding to the surface $S$. Our task is now to convince ourselves that the right-hand side area integral equals the surface integral
$$
\int_\mathbf{S} (\nabla \times \mathbf{F}) \cdot \mathbf{dS}.
$$
Let's look at the two partial derivatives in the integrand one by one. First we have
$$
\frac{\partial F_v}{\partial u} = \frac{\partial}{\partial u}(\mathbf{F} \cdot \frac{\partial \mathbf{x}}{\partial v}) = \frac{\partial}{\partial u}(F_i \frac{\partial x_i}{\partial v}) = (\frac{\partial F_i}{\partial x_j}\frac{\partial x_j}{\partial u})\frac{\partial x_i}{\partial v} + F_i (\frac{\partial^2 x_i}{\partial u\ \partial v}) 
$$
using nothing more than the product rule and the chain rule from the fact that $\mathbf{F}$ was originally a function of $x_i$ instead of $u$ and $v$. Similarly, we also have
$$
\frac{\partial F_u}{\partial v} = (\frac{\partial F_i}{\partial x_j}\frac{\partial x_j}{\partial v})\frac{\partial x_i}{\partial u} + F_i (\frac{\partial^2 x_i}{\partial u\ \partial v}) 
$$
noting the different indices $i$ and $j$. The integral
$$
\int_A (\frac{\partial F_v}{\partial u} - \frac{\partial F_u}{\partial v})\ du\ dv
$$
features the difference between the two partial derivatives, and so the second-order derivative term cancels; all that is left is
$$
\begin{aligned}
&(\frac{\partial F_i}{\partial x_j}\frac{\partial x_j}{\partial u})\frac{\partial x_i}{\partial v} - (\frac{\partial F_j}{\partial x_i}\frac{\partial x_i}{\partial v})\frac{\partial x_j}{\partial u} = (\frac{\partial x_i}{\partial v}\frac{\partial x_j}{\partial u})(\frac{\partial F_i}{\partial x_j} - \frac{\partial F_j}{\partial x_i}) \\
&= (\delta_{ik}\delta_{jl} - \delta_{il}\delta_{jk})(\frac{\partial x_i}{\partial v}\frac{\partial x_j}{\partial u}\frac{\partial F_k}{\partial x_l}) 
\end{aligned}
$$
where, for instance, $\delta_{ik}\delta_{jl}$ simply says "$i$ should equal $k$ and $j$ should equal $l$". Applying the identity
$$
\delta_{ik}\delta_{jl} - \delta_{il}\delta_{jk} = \epsilon_{pij}\epsilon_{pkl}
$$
gives rise to
$$
\epsilon_{pij}\epsilon_{pkl} (\frac{\partial x_i}{\partial v}\frac{\partial x_j}{\partial u}\frac{\partial F_k}{\partial x_l}) = (\epsilon_{pij} \frac{\partial x_i}{\partial v}\frac{\partial x_j}{\partial u})(\epsilon_{pkl}\frac{\partial}{\partial x_l} F_k) = (\frac{\partial \mathbf{x}}{\partial u}\times \frac{\partial \mathbf{x}}{\partial v})\cdot(\nabla \times \mathbf{F})
$$
from the definition of the cross product. As
$$
\mathbf{dS} = \frac{\partial \mathbf{x}}{\partial u}\times \frac{\partial \mathbf{x}}{\partial v}
$$
by definition, we finally have
$$
\int_A (\frac{\partial F_v}{\partial u} - \frac{\partial F_u}{\partial v})\ du\ dv = \int_S (\nabla \times \mathbf{F}) \cdot \mathbf{dS}.
$$


### Corollary: irrotational fields are conservative fields

> <span style="background-color: #1eff12; color: black;">Proof</span>.

An irrotational field $\mathbf{F}$, by definition, satisfies $\nabla \times \mathbf{F} = 0$. By Stokes' theorem, we have
$$
\int_S (\nabla \times \mathbf{F})\cdot \mathbf{dS} = \int_S 0\ dS = 0
$$
equalling
$$
\oint_C \mathbf{F \cdot dx}
$$
for any surface $S$, and thus any closed curve $C$ in $\mathbb{R^3}$.

****