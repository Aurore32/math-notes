
### Divergence and curl

For a vector field $\mathbf{F}$ written in terms of curvilinear coordinates $(x_1, x_2, x_3)$
$$
\mathbf{F} = F_1 \mathbf{e}_1 + F_2 \mathbf{e}_2 + F_3 \mathbf{e}_3,
$$
we claim the following two theorems on divergence and curl:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Divergence in curvilinear coordinates** for the above vector field $\mathbf{F}$, coordinates $(x_1,x_2,x_3)$, basis vectors $(\mathbf{e_1,e_2,e_3})$, and corresponding scale factors $h_1, h_2, h_3$, the divergence $\nabla \cdot \mathbf{F}$ is given by
$$
\frac{1}{h_1h_2h_3}(\partial_{x_1}(h_2 h_3 F_1)+\partial_{x_2}(h_1 h_3 F_2) + \partial_{x_3}(h_1 h_2 F_3))
$$
> noting that the scale factors $h_1, h_2, h_3$ **are not constant**!

> <span style="background-color: #1eff12; color: black;">Proof</span>.

This is far easier with the integral definition of divergence. Recall that
$$
\nabla \cdot \mathbf{F} = \lim_{V \to 0}\frac{\oint_S \mathbf{F\cdot dS}}{V}
$$
for an infinitesimally small surface $S$ enclosing a single point $\mathbf{x}$; in the new curvilinear coordinate system, consider a similar infinitesimal cuboid enclosed by sides of length $\delta x_1, \delta x_2, \delta x_3$, with volume
$$
(\delta x_1 \delta x_2 \delta x_3)(h_1 h_2 h_3)
$$
by definition of the scale factors and the orthogonality of the coordinate system. All that's left to do is dealing with the surface integral, which - as a reminder - is evaluated out of the following cuboid, with normal vectors equal to the curvilinear basis vectors $\mathbf{e_1, e_2, e_3}$:

![alt text](./assets/images/image-43.png)

As such, the numerator of the limit which defines the divergence
$$
\oint_S \mathbf{F \cdot dS}
$$
is simply the flux integral out of the faces of the cube: for instance, the faces perpendicular to $\mathbf{e_1}$ (notated $\mathbf{e_w}$ on the diagram) have combined integrals
$$
\begin{aligned}
\oint_{\text{top face}}\mathbf{F\cdot dS} + \oint_{\text{bottom face}}\mathbf{F \cdot dS} \\
= (\mathbf{F(x_1+\delta x_1,x_2,x_3)} \cdot \mathbf{e_1} - \mathbf{F(x_1, x_2, x_3)}\cdot \mathbf{e_1})(\text{area of face}) \\
= (F_1(x_1+\delta x_1,x_2,x_3) - F_1(x_1,x_2,x_3))(h_2 h_3 \delta x_2 \delta x_3) \\
= \delta x_1 \delta x_2 \delta x_3\frac{\partial (h_2 h_3 F_1)}{\partial x_1}

\end{aligned}
$$
by definition of the partial derivative, and due to the fact that the value of $\mathbf{F}$ remains roughly constant over an infinitesimal cuboid. 

(Beware here! The scale factors $h_1, h_2, h_3$ are **not** constant; as such, the area of the top face may not be equal to the bottom face. Thus, in reality we have
$$

(F_1(\text{top face})(h_2h_3)_{\text{top face}} - F_2(\text{bottom face})(h_2h_3)_{\text{bottom face}})\delta x_2 \delta x_3
$$
as our expression for flux above, which is why $h_2 h_3$ is enclosed within the partial derivative rather than multiplied outside it. $\delta x_2 \delta x_3$, however, **are** constant.)

For both of the other pairs of faces, we have equivalent terms $\delta x_1 \delta x_2 \delta x_3 \frac{\partial (F_2 h_1 h_3)}{\partial x_2}$ and $\delta x_1 \delta x_2 \delta x_3 \frac{\partial (F_3 h_1 h_2)}{\partial x_3}$; in total, the limit which defines the divergence in curvilinear coordinates is thus
$$
\lim_{V\to 0}\frac{\oint_S \mathbf{F\cdot dS}}{V} = \lim_{\delta x_1, \delta x_2, \delta x_3 \to 0}\frac{\sum_{i=1}^3(\delta x_1 \delta x_2 \delta x_3)\frac{\partial (F_i h_{\bar{i}})}{\partial x_i}}{(h_1 h_2 h_3)(\delta x_1 \delta x_2 \delta x_3)} 
$$
in which the term $\delta x_1 \delta x_2 \delta x_3$ cancels, leaving us with 
$$
\frac{1}{h_1h_2h_3}[\frac{\partial (F_1 h_2 h_3)}{\partial x_1} + \frac{\partial (F_2 h_1 h_3)}{\partial x_2} + \frac{\partial (F_3 h_1 h_2)}{\partial x_3}]
$$
without the limit.

***

Correspondingly, we have the following result for curl:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Curl in curvilinear coordinates** for vector field in $\mathbb{R^3}$ denoted $\mathbf{F}$, curvilinear basis vectors $\mathbf{e_1, e_2, e_3}$, and scale factors $h_1, h_2, h_3$ is given by the determinant
$$
\nabla \times \mathbf{F} = \frac{1}{h_1 h_2 h_3}\begin{vmatrix}
h_1 \mathbf{e_1} & h_2 \mathbf{e_2} & h_3 \mathbf{e_3} \\
\partial_1 & \partial_2 & \partial_3 \\
h_1F_1 & h_2F_2 & h_3 F_3
\end{vmatrix}
$$
(This differs from the standard expression for curl, given in Cartesian orthonormal basis vectors as
$$
\begin{vmatrix}
\mathbf{e_x} & \mathbf{e_y} & \mathbf{e_k} \\
\partial_x & \partial_y & \partial_z \\
F_x & F_y & F_z
\end{vmatrix}
$$
by only the presence of scale factors.)

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Begin as above with the integral definition of curl, given by
$$
\mathbf{n} \cdot (\nabla \times \mathbf{F}) = \lim_{A \to 0}\frac{\oint_C \mathbf{F \cdot dx}}{A}
$$
for an infinitesimally small curve $C$ enclosing an area $A$, and $\mathbf{n}$ as the normal vector to that area. Suppose we choose the normal vector $\mathbf{e_1}$; this would give us the first component of the vector representing curl in the basis $\mathbf{e_1, e_2, e_3}$.

Consider an infinitesimally small (rectangular) area on a surface normal to $\mathbf{e_1}$; in other words, the area has tangent vectors $\mathbf{e_2}$ and $\mathbf{e_3}$, as they are themselves orthonormal to $\mathbf{e_1}$. As such, the area can be approximated by
$$
\delta x_2 \delta x_3 (h_2h_3)
$$
by definition of the scale factors; the total circulation of $\mathbf{F}$ over the curve which bounds that area is thus the vector-valued line integral over a rectangle whose sides are parallel to $\mathbf{e_2}$ and $\mathbf{e_3}$. For instance, for the pair of sides parallel to $\mathbf{e_2}$ and running in opposite directions, we have
$$
\mathbf{e_2} \cdot (\mathbf{F}(x_1,x_2, x_3+\delta x_3) - \mathbf{F}(x_1,x_2,x_3)) (\text{length of line})
$$
equalling
$$
(\mathbf{F_2}(x_1,x_2, x_3 x_3) - \mathbf{F_2}(x_1,x_2,x_3+\delta)) (\delta x_2 h_2) = -\frac{\partial (F_2 h_2)}{\partial x_3}\delta x_2 \delta x_3
$$
as $\mathbf{e_3}$ is "going downwards" in a right-handed basis, and correspondingly, for the pair of sides parallel to $\mathbf{e_3}$, we have
$$
\frac{\partial(F_3 h_3)}{\partial x_2}\delta x_2 \delta x_3
$$
positive because $\mathbf{e_2}$ is "going upwards" in a right-handed basis. This gives us
$$
\mathbf{e_1}\cdot (\nabla \times \mathbf{F}) = \lim_{\delta x_2, \delta x_3 \to 0}\frac{(\partial_2(F_3 h_3) - \partial_3(F_2 h_2))(\delta x_2\delta x_3)}{(h_2h_3)(\delta x_2 \delta x_3)} = \frac{1}{h_2 h_3}\begin{vmatrix}
\partial_2 & \partial_3 \\
F_2 h_2 & F_3 h_3
\end{vmatrix}
$$
as the first term for our expression for curl. The other two terms follow suit in a similar manner, with choices of $\mathbf{e_2}$ and $\mathbf{e_3}$ as their normal vectors. In total, we have

$$
\nabla \times \mathbf{F} = \frac{1}{h_1 h_2 h_3}\begin{vmatrix}
h_1 \mathbf{e_1} & h_2\mathbf{e_2} & h_3\mathbf{e_3} \\
\partial_1 & \partial_2 & \partial_3 \\
h_1 F_1 & h_2 F_2 & h_3 F_3
\end{vmatrix}
$$
***


### Differential operators in cylindrical coordinates
Recall from above the basis vectors and associated scale factors for cylindrical coordinates
$$
\begin{cases}
\partial_r\mathbf{x} = (\cos \theta, \sin \theta, 0), h_r = 1 \\
\partial_\theta \mathbf{x} = (-r\sin \theta, r\cos\theta, 0), h_\theta = r \\
\partial_z \mathbf{x} = (0,0,1), h_z = 1
\end{cases}
$$


**The gradient**. We have 
$$
\begin{aligned}
\nabla f &= \frac{\mathbf{e_r}}{h_r}\partial_r f + \frac{\mathbf{e_\theta}}{h_\theta}\partial_\theta f + \frac{\mathbf{e_z}}{h_z}\partial_z f \\
&= ((\cos\theta\ \partial_r  - \sin \theta\ \partial_\theta)f, (\sin\theta \partial_r + \cos\theta \partial_\theta) f, \partial_z f)

\end{aligned}
$$
which can also be written (quite interestingly) as
$$
\begin{bmatrix}
\cos \theta & -\sin \theta & 0 \\
\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{bmatrix}\begin{bmatrix}
\partial_r f \\
\partial_\theta f \\
\partial_z f
\end{bmatrix}
$$
indicating the relationship between the gradient in cylindrical coordinates and Cartesian coordinates: a rotation counterclockwise in the $xy$-plane by an angle $\theta$!

**The divergence**. Using the above, for a vector field $\mathbf{F}$ we have
$$
\begin{aligned}
\nabla \cdot \mathbf{F} &= \frac{1}{h_r h_\theta h_z}[\frac{\partial (F_r h_\theta h_z)}{\partial r} + \frac{\partial (F_\theta h_r h_z)}{\partial \theta} + \frac{\partial (F_z h_r h_\theta)}{\partial z}] \\
&= \frac{1}{r}(\frac{\partial (r F_r)}{\partial r} + \frac{\partial F_\theta}{\partial \theta} + \frac{\partial (r F_z)}{\partial z}).
\end{aligned}
$$

**The curl**. We have

$$
\begin{aligned}
\nabla \times \mathbf{F} &= \begin{vmatrix}
h_r \mathbf{e_r} & h_\theta \mathbf{e_\theta} & h_z \mathbf{e_z} \\
\partial_r & \partial_\theta & \partial_z \\
h_r F_r & h_\theta F_\theta & h_zF_z 
\end{vmatrix} \\
&= \begin{vmatrix}
\mathbf{e_r} & r\mathbf{e_\theta} & \mathbf{e_z} \\
\partial_r & \partial_\theta & \partial_z \\
F_r & r F_\theta & F_z 
\end{vmatrix}

\end{aligned}
$$

**The Laplacian**. Defined as the divergence of the gradient of a scalar field $f$, we have
$$
\begin{aligned}
\nabla \cdot (\nabla f) = \nabla^2 f &= \nabla \cdot \begin{bmatrix}
f_r / h_r \\ f_\theta / f_\theta \\ f_z / h_z
\end{bmatrix} \\
&= \nabla \cdot \begin{bmatrix}
f_r \\ f_\theta/r \\ f_z
\end{bmatrix} \\
&= \frac{1}{h_r h_\theta h_z}[\frac{\partial(f_r h_\theta h_z)}{\partial r} + \frac{\partial (f_\theta h_r h_z)}{\partial \theta} + \frac{\partial(f_z h_r h_\theta)}{\partial z}] \\
&= \frac{1}{r}[\frac{\partial (rf_r)}{\partial r} + \frac{\partial f_\theta}{\partial \theta} + \frac{\partial(r f_z)}{\partial z}]
\end{aligned}
$$
where $r$ is treated as a constant in the final partial derivative, but not in the first.