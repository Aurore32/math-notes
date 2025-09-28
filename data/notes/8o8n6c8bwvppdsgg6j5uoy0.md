
## Boundary conditions and Poisson's Equation

Suppose we want to solve the Poisson equation
$$
\nabla^2 \Phi = \rho(\mathbf{x})
$$
for some source function $\rho$, and within a region of space $V$ with boundary $\partial V$. In particular, we specify one of two boundary conditions over $\partial V$: either

> <span style="background-color: #03cafc; color: black;">Definition</span>. **The Dirichlet condition**, for which $\Phi(\mathbf{x})$ is directly specified by a function $\psi(\mathbf{x})$ for some $\psi$ on all points on $\partial V$: $\Psi(\mathbf{x}) = \psi(\mathbf{x}), \mathbf{x} \in \partial V$.

or, alternatively,

> <span style="background-color: #03cafc; color: black;">Definition</span>. **The Neumann condition**, for which the directional derivative in the direction of the normal $\mathbf{n}$ to the surface $\partial V$ is specified by a function $\psi(\mathbf{x})$: $\mathbf{\Phi(x)\cdot n} = \psi(\mathbf{x}), \mathbf{x}\in\partial V$. 

For this broad formulation of boundary-value problems concerning Poisson's equation, we claim an equally broad statement of uniqueness:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The solution $\Phi$ to the Poisson equation $\nabla^2\Phi = \rho$ over a bounded region $V$, where either the Dirichlet or the Neumann condition is specified over the boundary $\partial V$, is unique as long as it exists.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Crucial to proving this statement is the following lemma, known as Green's first identity, named (much like Green's theorem and Green's second identity) after the Green Goblin:

> <span style="background-color: #12ffd7; color: black;">Lemma</span>. For scalar fields $\phi$ and $\psi$ in $\mathbb{R^3}$, we have
$$
\int_V \phi \nabla^2 \psi\ dV = \int_{\partial V}\phi\nabla\psi\cdot\mathbf{dS} - \int_V \nabla \phi \cdot \nabla \psi\ dV.
$$
> This can be understood as a multivariate analogue to integration by parts:
$$
\int u\ dv = uv - \int v\ du
$$
> in which we have $u = \phi$ and $v = \nabla \psi$, and the surface integral can be understood as "reducing the degree of integration" by $1$. 

> <span style="background-color: #1eff12; color: black;">Proof</span>.

This lemma follows directly from the application of the Divergence Theorem on the surface integral:

$$
\int_{\partial V}\phi \nabla \psi \cdot \mathbf{dS} = \int_{\partial V} \nabla\cdot(\phi \nabla \psi) dV
$$
resulting in the other two terms. Correspondingly, we also have the result
$$
\int_V \phi\nabla^2 \psi - \psi \nabla^2 \phi\ dV = \int_{\partial V}(\phi \nabla \psi - \psi \nabla \phi) \cdot \mathbf{dS};
$$
this is known as *Green's second identity*, no relation to the first.

***

After the preceding contractually-obligated commercial break, we now return to the Poisson equation. Suppose, for the sake of contradiction, that both $\Phi$ and $\Psi$ are scalar fields that satisfy a given boundary condition and solve the Poisson equation over **any arbitrary** region $V$. Then we have

$$
\nabla^2 \Phi - \nabla^2 \Psi = \nabla^2 (\Phi - \Psi) = \rho - \rho = 0
$$
with $\Phi - \Psi$ satisfying the Laplace equation in the same region; denote $\Phi - \Psi$ as $f$. By Green's first identity, we have
$$
\int_V f\nabla^2 f\ dV = \int_V 0\ dV = 0
$$
on the left-hand side, taking $\phi = \psi = f$, and on the right-hand side
$$
\int_{\partial V} f\nabla f \cdot \mathbf{dS} - \int_V (\nabla f) \cdot (\nabla f)\ dV
$$
resulting in 
$$
\int_{\partial V} f\nabla f \cdot \mathbf{dS} = \int_V (\nabla f) \cdot (\nabla f)\ dV = \int_V |\nabla f|^2\ dV
$$
which we note is always non-negative.

Now we make use of the boundary conditions. If both $\Phi$ and $\Psi$ satisfy either the Dirichlet or Neumann boundary conditions, then either $\Phi - \Psi = f = 0$ (Dirichlet; both equal the same function on the boundary) or $\nabla(\Phi - \Psi) \cdot \mathbf{n} = \nabla f \cdot \mathbf{n} = 0$ (Neumann; the gradient of both fields have the same dot product with the normal to the boundary). 

As such, the left-hand side above is zero in both cases; for the Dirichlet condition $f = 0$ directly, and for the Neumann condition $\nabla f \cdot \mathbf{dS} = \nabla f \cdot \mathbf{n}\ dS = 0$. However, this surface integral - which is always zero - always equals the integral of a non-negative quantity $|\nabla f|^2$ over **any arbitrary** volume; as any volume can be chosen, this clearly reaches a contradiction. $\square$

***

We have two small amendments to make to the above theorem before proceeding:

1. The above proof is just as viable for boundary conditions that are a mix of Neumann and Dirichlet conditions, as well as for regions where there are different boundary conditions on different parts of the boundary.

2. Uniqueness does not guarantee existence even though existence guarantees uniqueness. For instance, if $\Phi$ satisfies $\nabla^2 \Phi = \rho$ in a region $V$ with Neumann condition $\nabla \Phi \cdot \mathbf{n} = g(\mathbf{x})$ for some $g$, then 
$$
\oiint_{\partial V} \nabla \Phi \cdot \mathbf{n}\ dS = \oiint_{\partial V} \nabla \Phi \cdot \mathbf{dS} = \int_V \nabla^2\Phi\ dV
$$
by the Divergence Theorem, which mandates that $\oiint_{\partial V} g\ dS = \int_V \rho\ dV$.

## Harmonic functions and their properties

> <span style="background-color: #03cafc; color: black;">Definition</span>. Solutions to the Laplace equation $\nabla^2 \psi = 0$ are called **harmonic functions**. Not to be confused with the type of harmonic function that pops up in a musicology PhD's doctoral thesis analyzing the first bars of Rick Astley's hit single, "Never Gonna Give You Up".

Harmonic functions pop up everywhere in the real world. As stated, they describe the potential function of something when that particular "something" has no source - when it is equally diffused throughout the region, like heat or fluid flow or "the smell of that guy who hasn't showered in a week showing up to the lecture hall".

This section will introduce just two of the countless fascinating properties of harmonic functions. (In reality the *only* two fascinating properties, but we don't need to know that.)

> <span style="background-color: #ffb812; color: black;">Property 1</span>. The **mean-value property**. The value of a harmonic function $\psi(\mathbf{x})$ at a point $\mathbf{x = a}$ within a region that encompasses a sphere of radius $R$ centered at $\mathbf{a}$ is equal to the mean value of $\psi$ on that sphere $S$:

$$
\psi(\mathbf{a}) = \bar{\psi}(R) = \frac{1}{4\pi R^2} \int_S \psi(\mathbf{x})\ dS
$$

> for any value of $R$ within the region.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Using spherical coordinates $(r, \theta, \phi)$ centered at $\mathbf{a}$, the sphere $S$ can be represented in parametric form as
$$
(r\sin \theta \cos \phi, r \sin \theta \sin \phi, r\cos \phi)
$$
 and the surface-area component $dS$ as $r^2 \sin \theta\ d\theta\ d\phi$ by the cross product. As such, we have
$$
\begin{aligned}
\bar{\psi}(r) = \frac{1}{4\pi r^2}\int_{S}\psi(\mathbf{x})\ dS = \frac{1}{4\pi}\int_0^{\pi}\int_0^{2\pi}\psi(r,\theta,\phi)\sin \theta\ d\theta\ d\phi   

\end{aligned}
$$
Note here that $\psi(r, \theta, \phi)$ is solely a function of $r$, and thus satisfies $\nabla\psi(r) = \frac{\partial \psi}{\partial r} \hat{\mathbf{r}}$ and $\mathbf{dS} \cdot \nabla\psi(r) = \nabla\psi(r)\ dS$ as the normal to the surface is parallel with the gradient, which has $r$-component only.

Our task is now to prove that this is a constant with respect to $r$, and that its value is $\psi(\mathbf{a})$. Begin with 
$$
\begin{aligned}
\frac{\partial}{\partial r}\bar{\psi}(r) &= \frac{1}{4\pi}\int_0^{\pi}\int_0^{2\pi}\frac{\partial}{\partial r}\psi(r)\ dS \\
&= \frac{1}{4\pi}\int_S \nabla\psi \cdot \mathbf{dS} \\
&= \frac{1}{4\pi}\int_V \nabla^2 \psi\ dV =0
\end{aligned}
$$
by the Divergence Theorem and the definition of a harmonic $\nabla^2 \psi = 0$. Thus $\bar \psi(r)$ is constant; in addition, when $r \to 0$ the sphere being considered encompasses the point $\mathbf{a}$ and $\mathbf{a}$ only, and so $\bar\psi(r)$ takes the value $\psi(\mathbf{a})$ at that point. $\square$



> <span style="background-color: #ffb812; color: black;">Property 2</span>. The **extreme-value property**. Harmonic functions satisfying the Laplace equation within a region $V$ have no local maxima or minima within $V$; any maxima or minima must be on the boundary of the region.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

If $\nabla^2 \psi = 0$, then $\nabla \cdot (\nabla \psi) = 0$ for every point in $\psi$. Assume for the sake of contradiction that a maximum or minimum point $\mathbf{x}$ exists in $V$; by definition, such a point satisfies either
$$
\psi(\mathbf{x + \epsilon}) > \psi (\mathbf{x})
$$
or
$$
\psi(\mathbf{x + \epsilon}) < \psi (\mathbf{x})
$$
for all such infinitesimal vectors $\epsilon$ with $|\epsilon| \to 0$. Suppose that $\mathbf{x}$ is a maximum point, with $\psi(\mathbf{x + \epsilon}) < \psi (\mathbf{x})$. Then by the **mean-value property** above, we have

$$
\psi(\mathbf{x}) = \text{mean value of points surrounding $\mathbf{x}$}
$$
which is smaller than $\psi(\mathbf{x})$ by definition. This leads to a contradiction.