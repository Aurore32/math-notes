---
id: 9ct9sy0ph4ewyzsppgv363h
title: Integral Solutions
desc: ''
updated: 1742563178919
created: 1742543630798
nav_order: 4
---
## Point sources and the Delta function

As mentioned before, an important caveat to the isotropic solution for the Laplace equation in $\mathbb{R^3}$ - which takes the form $\psi(r) = \alpha - \beta r^{-1}$ - is the fact that it diverges at the origin, where $r = 0$; at that point, it can no longer be construed as a valid solution to the Laplace equation. In that case, then, 1) what does $r=0$ mean in a physical sense, and 2) what equation does the fundamental solution solve at that point?

The answer to the first question is slightly easier. A gravitational field around an infinitely small point mass, for instance, would satisfy the Laplace equation everywhere except for the point where the mass is located; at every other point, the mass density of the point mass is zero. As such, $r = 0$ in the context of a solution to the Laplace equation can be interpreted as gravitational potential near a point mass - all the density concentrated in a single point, zero density everywhere else, and infinite potential/energy required to bring another mass to that point as a result.

To see what equation our fundamental solution solves at $r = 0$, consider the volume integral in a spherical region $V$ of radius $R$ around the origin

$$
\int_V \nabla^2 \psi\ dV = \oiint_S \nabla \psi \cdot \mathbf{dS} = (\nabla\psi(R))4\pi R^2 
$$
by the Divergence Theorem; yet we know that, by definition of the fundamental solution, $\nabla^2 \psi = 0$ at every point aside from the origin. This would imply that the Poisson equation satisfied by $\psi$, $\nabla^2 \psi = \rho$, has the properties:
$$
\begin{cases}
0 \text{ everywhere where $\mathbf{x \neq 0}$,} \\
\int_V \rho\ dV = 4\pi R^2 (\nabla\psi(R))
\end{cases}
$$
and when $\psi(r)$ is our fundamental solution $1/4\pi r$, we have $\nabla \psi = -1/4\pi r^2$ and $\int_V \rho\ dV = -1$.
These are properties only the Delta function would have. In three dimensions, the Delta function $\delta^3(\mathbf{x})$ is easily generalized by definition to be
$$
\begin{cases}
\delta^3(\mathbf{x}) = 0, \mathbf{\ x\neq 0}\\
\int_V \delta^3(\mathbf{x})\ dV = 1\text{ for any region $V$ enclosing the origin}.
\end{cases}
$$
As such, the *fundamental solution* $\psi(r) = 1/4\pi r$ obtained previously as a solution to the Laplace equation everywhere except the origin is, in reality, a solution of the more general Poisson equation
$$
\nabla^2 \psi = -\delta^3(\mathbf{x})
$$
throughout a domain that now encompasses the entirety of $\mathbb{R^3}$; in general, we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Poisson equation for a point source**. The isotropic solution to the Laplace equaiton
$\psi(r) = \lambda/4\pi r$ solves the Poisson equation
$$
\nabla^2 \psi = -\lambda\delta^3(\mathbf{x}).
$$
In particular, the Delta function's presence represents a **point source** for the potential: one that exists only at a single point and nowhere else.

## An integral solution for the Poisson equation

We understand from the above that the isotropic solution
$$
\psi(r) = \lambda/4\pi r
$$
to the Laplace equation models a point source of strength $\lambda$ placed at the origin; if instead the point source is placed at a point $\mathbf{x'}$, then by extension we have
$$
\psi(\mathbf{x}) = \frac{\lambda}{4\pi |\mathbf{x - x'}|}.
$$
Now suppose that instead of a single point source, we have many, many different point sources scattered about a closed region $V$; each has a different strength $\lambda$ - enough to justify our use of a function $\rho$ to represent the strength of the point source placed at point $\mathbf{x'}$: 
$$
\lambda = \rho(\mathbf{x'}).
$$
Eventually, when we have an infinite number of point sources that cover $V$ in its entirety and $\rho$ becomes a smooth, continuous function, the point sources collect together to become an object bounded by $V$ with density $\rho(\mathbf{x'})$ at each point:

$$
\psi(\mathbf{x}) = \int_V \frac{\rho(\mathbf{x'})}{4\pi |\mathbf{x - x'}|}\ dV.
$$

where, importantly, the variable being integrated through in the volume integral is $\mathbf{x'}$, **not** $\mathbf{x}$. This ultimately leads to one final claim:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The amalgamated object $\psi(\mathbf{x})$, represented by the above volume integral of point sources, is a solution to the Poisson equation $\nabla^2 \psi = -\rho.$

The surface-level dark-magic trickery of what we're doing here belies a simple explanation for how this might have occurred: the Poisson equation $\nabla^2 \psi = -\rho(\mathbf{x})$ describes a potential function $\psi$ which arises from a source of density $\rho$ at points $\mathbf{x} \in \mathbb{R^3}$. Therefore, if at each **infinitesimal point** some function $\psi$ has a point source placed there with strength $\rho$, and if it smells like the potential function of $\rho$ and talks like the potential function of $\rho$, then it **is** the potential function of $\rho$.

Not rigorous enough yet? Then

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Direct substitution gives
$$
\begin{aligned}
\nabla^2 \psi(\mathbf{x}) &= \int_V \nabla^2\frac{\rho(\mathbf{x'})}{4\pi |\mathbf{x - x'}|}\ dV \\
&= \int_V \rho(\mathbf{x'})\frac{1}{4\pi}\nabla^2 \frac{1}{|\mathbf{x-x'}|}\ dV
\end{aligned}
$$
Where we know that $\frac{1}{\mathbf{x-x'}} = \frac{1}{r}$, as an isotropic solution to the Laplace equation, also satisfies the Poisson equation involving a delta function
$$
\nabla^2 \frac{1}{\mathbf{|x-x'|}} = -4\pi \delta^3(\mathbf{x-x'})
$$
translated from the origin to $\mathbf{x'}$. What we are left with is simply
$$
\begin{aligned}
\nabla^2 \psi(\mathbf{x}) &=\int_V -\rho(\mathbf{x'})\frac{1}{4\pi}4\pi \delta^3(\mathbf{x-x'})\ dV \\
&= \int_V -\rho(\mathbf{x'})\delta^3(\mathbf{x-x'})\ dV \\
&= p(\mathbf{x})
\end{aligned}
$$
integrating over $\mathbf{x'}$, by the properties of the Delta function.