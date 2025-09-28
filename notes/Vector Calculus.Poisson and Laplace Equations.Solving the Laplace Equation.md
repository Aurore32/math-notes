---
id: 9pqdbygdcfz3lg0q2pas8oy
title: Solving the Laplace Equation
desc: ''
updated: 1742545394835
created: 1742481102824
nav_order: 2
---
## Properties of the Laplace equation


> <span style="background-color: #03cafc; color: black;">Definition</span>. **The Laplace equation** is defined as $\nabla^2\Phi = 0$ for a scalar field $\Phi$, where $\nabla^2$ is the operator known as the **Laplacian**.

Time for a few quick properties of this partial differential equation which should help us out a tiny bit!

> <span style="background-color: #ffb812; color: black;">Property 1</span>. **Linearity**. If $\Phi$ and $\Psi$ are both solutions to the Laplace equation, then any linear combination of the two $\lambda \Phi + \mu \Psi$ for scalars $\lambda, \mu$ also solves the Laplace equation.

This is swiftly verified via the linearity of the Laplacian operator itself. 

Expressed in differential form, the Laplace equation ppears as follows:
$$
\nabla^2 \Phi = \frac{\partial^2 \Phi}{\partial x_1^2} + \frac{\partial^2 \Phi}{\partial x_2^2} + ... + \frac{\partial^2 \Phi}{\partial x_n^2} = 0
$$
for a scalar field $\Phi$ in $\mathbb{R^n}$. 

It's natural to broadly conceptualize solutions to $\Phi$ into one of either two types: types where the solution is **symmetric** - $\frac{\partial^2 \Phi}{\partial x_i^2}$ is the same in every single direction $x_i$, and thus equals zero - and types where the solution is not, and the function has different second partial derivatives along the axes and symmetry is lost.  

This leads us to the following property:

### Radial symmetry and isotropic solutions

> <span style="background-color: #ffb812; color: black;">Property 2</span>. **Radial symmetry**. If $\Phi$ is solely a function of the radius $r$ from the origin, e.g. in polar or spherical coordinates - $\Phi = \Phi(r)$ - then $\Phi$ is symmetrical about all the coordinate axes; thus, if we can guarantee that $\Phi$ has second derivative zero about one of the axes, it satisfies the Laplace equation by default.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call such a solution $\Phi = \Phi(r)$ to $\nabla^2 \Phi = 0$ **isotropic**: it has no preferred direction.

Using the expression for $\nabla^2$ in spherical coordinates (or, for the 2D analogue, polar coordinates) leads to $\Phi$ satisfying

$$
\frac{1}{r^2}\frac{\partial}{\partial r}(r^2\frac{\partial \Phi}{\partial r}) = 0
$$
in which the other two terms involving the other partial derivatives $\partial_\theta$ and $\partial_\phi$ are eliminated because $\Phi$ is conveniently only a function of $r$. This is now an ordinary differential equation - one we can easily solve! 
$$
\begin{aligned}
\frac{1}{r^2}\frac{\partial}{\partial r}(r^2\frac{\partial \Phi}{\partial r}) &= 0 \\
\frac{\partial}{\partial r}(r^2\frac{\partial \Phi}{\partial r}) &= 0 \\
r^2 \frac{\partial \Phi}{\partial r} &= \beta \\
\frac{\partial \Phi}{\partial r} &= \beta r^{-2} \\
\Phi &= \alpha - \beta r^{-1}
\end{aligned}
$$
for arbitrary constants $\alpha$ and $\beta$. Note that, in particular, solutions of the form $\Phi = \frac{\beta}{r}$, e.g. $\Phi = -\frac{GM}{r}$, represent the gravitational and electrostatic fields we all know and love (with $r=0$ representing the point inside the point mass or point charge, where potential is not defined).

> <span style="background-color: #ffb812; color: black;">Caution</span>! This solution is clearly undefined at $r=0$, and does not solve the Laplace equation at that point.

If instead we want $\Phi$ to be radially symmetric in cylindrical coordinates - $\Phi = \Phi(r)$ with $r = \sqrt{x^2+y^2}$ and no $z$-direction - then $\Phi$ is independent of $z$ and thus has zero partial derivative in that direction. As such, we need only consider
$$
\begin{aligned}
\nabla^2 \Phi = \frac{1}{r}\frac{\partial}{\partial r}(r\frac{\partial \Phi}{\partial r})&= 0 \\
r\frac{\partial \Phi}{\partial r} &= \beta \\
\Phi &= \alpha + \beta \log r 
\end{aligned}
$$
for our solution. This solution is invariant along the $z$-axis and changes only in the $xy$-plane; as such, it is also a solution to the Laplace equation in $\mathbb{R^2}$. Importantly, while the spherically symmetric solution $\Phi = \alpha - \beta r^{-1}$ in $\mathbb{R^3}$ decays to $\alpha$ asymptotically, this solution grows to infinity as $r \to \infty$.


### Monopoles and dipoles

> Always two, there are. No more, no less.<br/>
-- Master Yoda

We move on to one final property of solutions to the Laplace equation which allow us to generate more isotropic solutions from a single isotropic solution:

> <span style="background-color: #ffb812; color: black;">Property 3</span>. If $\Phi$ is an isotropic solution to $\nabla^2 \Phi = 0$, then the directional derivative of $\Phi$ in the direction of any vector $\mathbf{d}$, $\nabla_\mathbf{d}\Phi = \mathbf{d} \cdot \nabla \Phi$, is also a solution to the Laplace equation.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Using summation convention, we have
$$
\nabla_\mathbf{d} \Phi = d_i \partial_i \Phi
$$
and as such
$$
\nabla^2 (\nabla_\mathbf{d} \Phi) = \nabla^2(d_i \partial_i \Phi) =  \sum_{j=1}^n \partial^2_j (d_i \partial_i \Phi)
$$
and if indeed $\Phi$ is an isotropic solution to the Laplace equation, then in every direction $\partial^2_i \Phi = 0$; as $\Phi$ can be assumed to be smooth and continuous, swapping the order of the partial derivatives results in
$$
\sum_{j=1}^n \partial^2_j (d_i \partial_i \Phi) = \sum_{j=1}^n d_i \partial_i (\partial^2_j \Phi) = 0.
$$

If we were to construct such directional-derivative-bound solutions, our basic building block would be:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Denote the isotropic solution to Laplace's equation in $\mathbb{R^3}$ as the **fundamental solution**, or the **unit monopole**, if it has the property that the flux of its gradient out of a sphere of any radius is equal to one.

The flux of the gradient $\nabla \Phi$ has the convenient physical interpretation of being either gravitational flux (for $\Phi$ equalling gravitational potential, where $\nabla \Phi$ is gravitational force) or electric flux.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The fundamental solution in $\mathbb{R^3}$ takes the form $\Phi_m = -1/4\pi r$, and the fundamental solution in $\mathbb{R^2}$ takes the form $f = \log r/2\pi$.

> <span style="background-color: #1eff12; color: black;">Proof</span>

For the general isotropic solution $\Phi = \alpha - \beta r^{-1}$, consider the flux integral
$$
\oiint_{S} \nabla \Phi \cdot \mathbf{d S}
$$
over an arbitrary sphere $S$ centered at the origin. Using the expression of gradient in spherical coordinates, we have
$$
\nabla \Phi = \frac{\partial }{\partial r}(\alpha - \beta r^{-1})\hat{\mathbf{r}} = (\beta r^{-2})\hat{\mathbf{r}}
$$
which is always parallel with the normal vector to the sphere at every point. Thus, the flux integral simplifies to the sum of $\beta r^{-2}$ throughout the surface of the sphere, where it is constant; supposing that the sphere has radius $\rho$ and thus surface area $4\pi \rho^2$, we have
$$
\oiint_S = 4\pi \rho^2 \cdot \beta \rho^{-2} = 4\pi\beta
$$
independent of radius $\rho$, yielding $\beta = 1/4\pi$ and thus the fundamental solution $\Phi_m = -1/4\pi r$. The $\mathbb{R^2}$ case follows similarly.

***

The fundamental solution is also known as the unit monopole because it's a hypothetical representation of a single magnetic pole (north or south), existing independent of its counterpart and freely suspended in space; despite every mathematical indication towards their existence and despite scientists' best attempts at smashing three billion dollars' worth of funding to bits and pieces in the Large Hadron Collider, monopoles have never been found outside of physicists' wet dreams and in-between the arms of your mom at the epileptic strip club down the street.


Given this fundamental solution, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **dipole** of strength $\mathbf{d}$ - a pair of magnetic poles with opposite polarity, i.e. north and south, separated by a close distance and with large but opposite strengths - can be modelled by the Laplace equation solution $\nabla_\mathbf{d} \Phi_m$, where $\Phi_m$ is the fundamental solution as above.
