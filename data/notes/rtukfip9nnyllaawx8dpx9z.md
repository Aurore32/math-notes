> Why don't they just throw it into a bathtub and see how much the water goes \*fooosh\*? Are they stupid?

## Generalizing the area integral

We know the drill. Just as a single integral is formed over a single Riemann sum, and an area (double) integral is formed over a double Riemann sum, a volume integral - just to remind you, we're now at three - is formed over a triple Riemann sum, based off the **volume differential**
$$
dV = dx\ dy\ dz.
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. A **volume integral** over a region $V$ in 3D space of a scalar function $\phi(\mathbf{x}): \mathbb{R^3 \to R}$, denoted $\int_V \phi\ dV$, is the limiting value of the sum
$$
\lim_{\delta V \to 0}\sum_{i=1}^n \phi(\mathbf{x}_i)\ \delta V = \lim_{\delta x,\ \delta y,\ \delta z \to 0}\sum_{i=1}^l \sum_{j=1}^m \sum_{k=1}^n \phi(\mathbf{x}_{ijk})\ \delta x\ \delta y\ \delta z
$$
> if it exists, where each $dV = \delta x\ \delta y\ \delta z$ can be interpreted as an infinitesimal cuboid in space, of which there are $lmn$ in total.

This may also be denoted $\int\int\int dV$, which to my mind looks seven gazillion times cooler, but - to quote the text I'm basing these notes upon -
> "Some texts prefer... a conservation of integral signs and so write area integrals as $\int \int dA$ and volume integrals as $\int \int \int dV$. The authors of these texts aren't string theorists and have never had to perform an integral in ten dimensions."

This is where the "eldritch horror" side of math really shines through. 

Given the above formulation, we can also re-interpret the volume integral as the following iterated integral:
$$
\int_{z_a}^{z_b}\int_{y_a}^{y_b}\int_{x_a}^{x_b}\phi(x,y,z)\ dx\ dy\ dz
$$
where the order of integration is still irrelevant as long as $\phi$ satisfies the usual suspects (smoothness, continuity, springs back when poked, elastic and stretchy, good gluten formation etc. etc.) 

As with non-rectangular regions in 2D, volume integrals may be carried out over non-cuboid regions through allowing $x_a = x_a(y,z), x_b=x_b(y,z)$ to be functions of $y$ and $z$ and $y_a = y_a(z), y_b = y_b(z)$ to be functions of $z$, keeping $z_a$ and $z_b$ constant:
$$
\int_{z_a}^{z_b}\int_{y_a(z)}^{y_b(z)}\int_{x_a(y,z)}^{x_b(y,z)}\phi(x,y,z)\ dx\ dy\ dz
$$
Alternatively, as the order of integration typically does not matter, we may perform integration with respect to $z$ first and thus have
$$
\int_{y_a}^{y_b} \int_{x_a(y)}^{x_b(y)} (\int_{z_a(x,y)}^{z_b(x,y)} \phi\ dz) \ dA
$$
as $dx\ dy = dA$.

## Change of variables for volume integrals

Suppose now that $(x,y,z) \to (u(x,y,z),v(x,y,z),w(x,y,z))$ is a change of variables from $x, y, z$ to $u, v, w$, where all of $u, v, w$ are smooth, invertible functions of $x, y, z$; in particular, denote their inverses as
$$
\begin{cases}
x = x(u,v,w) \\
y = y(u,v,w) \\
z = z(u,v,w)
\end{cases}
$$
Using a similar derivation process to the two-dimensional Jacobian, we define the three-dimensional Jacobian as the matrix determinant
$$
J(u,v,w) = \frac{\partial(x,y,z)}{\partial(u,v,w)} = \begin{vmatrix}
x_u & x_v & x_w \\
y_u & y_v & y_w \\
z_u & z_v & z_w
\end{vmatrix}
$$
representing the area scaling factor for the parallepiped formed by $\delta u, \delta v, \delta w$ instead of the parallelogram formed by $\delta u$ and $\delta v$. Analogous to the two-dimensional case, we thus have
$$
\int_V \phi(x,y,z)\ dV = \int_V \phi(u,v,w)\ |J(u,v,w)|\ du \ dv \ dw
$$

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the Jacobian for: 
1. Spherical polar coordinates, given by $(x,y,z) = (r\sin \theta \cos \phi, r\sin \theta \sin \phi, r\cos \theta)$;
2. Cylindrical polar coordinates, given by $(x,y,z) = (r \cos \phi, r \sin \phi, z)$.

> <span style="background-color: #1eff12; color: black;">Solution</span>.

For spherical polar coordinates:
$$
\begin{aligned}
J(r, \theta, \phi) &= \begin{vmatrix}
(r\sin\theta \cos \phi)_r & (r\sin\theta \cos \phi)_\theta & (r\sin\theta \cos \phi)_\phi \\
(r\sin\theta \sin \phi)_r & (r\sin\theta \sin \phi)_\theta & (r\sin\theta \sin \phi)_\phi \\
(r\cos \theta)_r & (r\cos \theta)_\theta & (r\cos \theta)_\phi
\end{vmatrix} \\
&= \begin{vmatrix}
\sin \theta \cos \phi & r\cos \theta \cos \phi & - r\sin\theta\sin\phi \\
\sin \theta \sin \phi & r \cos \theta \sin \phi & r\sin\theta\cos\phi \\
\cos \theta & -r\sin \theta & 0
\end{vmatrix}
\end{aligned}
$$
Using the last row to expand the determinant gives
$$
\begin{aligned}
J(r,\theta,\phi)&= \cos \theta \begin{vmatrix}
r\cos \theta \cos \phi & - r\sin\theta\sin\phi \\
r \cos \theta \sin \phi & r\sin\theta\cos\phi 
\end{vmatrix} + r \sin \theta \begin{vmatrix}
\sin \theta \cos\phi & -r\sin\theta\sin\phi \\
\sin \theta \sin \phi & r \sin \theta \cos \phi
\end{vmatrix} \\
&= \cos\theta(r^2\sin\theta\cos\theta\cos^2\phi + r^2\sin\theta\cos\theta\sin^2\phi)\\
& + r\sin\theta(r\sin^2\theta\cos^2\phi + r\sin^2\theta\sin^2\phi) \\
&=r^2\sin\theta\cos^2\theta + r^2\sin\theta\sin^2\theta \\
&= r^2 \sin \theta.

\end{aligned}
$$

For cylindrical polar coordinates:

$$
\begin{aligned}
J(r, \phi, z) &= \begin{vmatrix}
(r\cos\phi)_r & (r\cos\phi)_\phi & (r\cos\phi)_z \\
(r\sin\phi)_r & (r\sin\phi)_\phi & (r\sin\phi)_z \\
z_r & z_\phi & z_z
\end{vmatrix} \\
&= \begin{vmatrix}
\cos\phi & -r\sin\phi & 0 \\
\sin\phi & r\cos\phi & 0 \\
0 & 0 & 1
\end{vmatrix}

\end{aligned}
$$
Using the last row to expand the determinant gives
$$
J(r,\phi,z) = r\cos^2\phi + r\sin^2\phi = r
$$
as with polar coordinates in 2D.


## Wrapping up

Three last concerns before we wave *sayonara* and leave the world of multiple integrals behind forever. That is, until next Monday.

1. **Finding volume with volume integrals** (incredible). Our puny three-dimensionaloid minds know not how to interpret $\int_D \phi \ dV$ as volume or area under a curve, but $\int_D \ dV$ represents the sum of the infinitesimal cubes making up the solid $D$ and thus converges to its volume.

2. **Generalizing volume integrals to higher dimensions**. Three points of concern here:

    - By Fubibinini's Theorem, the order of integration is still irrelevant given the usual terms and conditions.
    - If expressing an integral over some $n$-dimensional region as $n$ iterated integrals, the innermost integral can have bounds $a, b$ that are functions of the other $n-1$ variables, the second-innermost integral can have bounds that are functions of the other $n-2$ variables, etc., etc., until the outermost integral can only have constant bounds. 
    - The Jacobian $J(y_1,y_2,..y_n)$ for a change of variables $x_1, ..., x_n \to y_1, ..., y_n$ is given by the matrix determinant $|\frac{\partial x_i}{{\partial y_j}}|$.

3. **Other applications of volume integrals.**

    1. **Finding the total of a quantity (e.g. electric charge) over a solid object.**

        > <span style="background-color: #03cafc; color: black;">Example</span>. **Electric charge on a hemisphere**. Let $H$ be a hemisphere of radius $R$, centered about the origin. Suppose that there is a charge at every point on the sphere, with magnitude $f(z)$ at each point dependent on the $z$-coordinate only: $f(z)=f_0\frac{z}{R}$ for some constant $f_0$. What is the total charge on the hemisphere?

        > <span style="background-color: #1eff12; color: black;">Solution</span>.

        Let's use spherical coordinates for this one! A hemisphere with radius $R$ about the origin in spherical coordinates can be very concisely described by
        $$
        r = R,\ 0\leq\theta\leq \frac{\pi}{2}
        $$
        as the hemisphere only encompasses the top half of the $xyz$-space. The total charge over the entire volume of the sphere can be formulated as the volume integral
        $$
        \int_H f(z)\ dV
        $$
        which, given a change of coordinates to spherical coordinates, equals
        $$
        \begin{aligned}
        \int_{0}^{2\pi}\int_{0}^{\frac{\pi}{2}}\int_{0}^{R}f_0\frac{r\cos\theta}{R}\ r^2\sin\theta\ dr\ d\theta\ d\phi \\
        = \frac{f_0}{R}\int_{0}^{2\pi}\int_{0}^{\frac{\pi}{2}}\sin\theta\cos\theta\ [\frac{r^4}{4}]^R_0\ d\theta\ d\phi \\
        = \frac{f_0R^3}{4}\int_{0}^{2\pi}\int_{0}^{\frac{\pi}{2}}\sin\theta\cos\theta\  d\theta\ d\phi \\
        = \frac{f_0R^3}{4}\int_{0}^{2\pi}[\frac{\sin^2\theta}{2}]^{\frac{\pi}{2}}_0 \ d\phi \\
        = \frac{f_0 R^3 \pi}{4}.
        \end{aligned}
        $$

    2. **Finding the center of mass of a solid object.**

        > <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Center of mass**. Suppose that $D$ describes a solid object in space, and $\rho(\mathbf{x})$ describes the density of the object at point $\mathbf{x}=(x,y,z)$. The center of mass of the object is thus given by
        $$
        \mathbf{X} = \frac{1}{M}\int_V \mathbf{x}\rho(\mathbf{x})\ dV
        $$        
        > where $M$ is the total mass of the object, given by the integral of its density over volume:
        $$
        M = \int_V \rho(\mathbf{x})\ dV.
        $$
        > Note that the center of mass is a **vector-valued integral**, which is simply an integral evaluated component-by-component but otherwise normally.

        > <span style="background-color: #1eff12; color: black;">Proof</span>. 

        The integral expression of the center of mass is motivated by the **priciple of moments**, which states that if an object is thought of as being comprised of $n$ point-masses with position $\mathbf{x_1, x_2, ..., x_n}$ and masses $m_1, m_2, ..., m_n$, then the object is in equilibrium about a pivot point $\mathbf{X}$ (imagine balancing the object on the tip of your finger at this point) if the **moments** of the point masses sum to zero:

        $$
        \sum_{i=1}^n m_i(\mathbf{X-x_i}) = 0 \iff \mathbf{X} = \frac{\sum_{i=1}^n\mathbf{m_i x_i}}{\sum_{i=1}^n m_i}
        $$

        which, as $n \to \infty$, converges to the above integral for $\mathbf{X}$.