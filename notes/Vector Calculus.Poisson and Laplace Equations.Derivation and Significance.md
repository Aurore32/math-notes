---
id: bg8uqr6kl87d2bt7ydgvxwl
title: Physical Origins and Significance
desc: ''
updated: 1752283104608
created: 1742467566512
nav_order: 1
---
## The Fundamental Forces

We begin, as we always do, with the Four Horsemen of Physics: the four fundamental forces - gravitational, electromagnetic, and the strong and weak nuclear forces. We have, in ascending order of annoyance,

1. The gravitational force, acting between two point particles with masses $m$ and $M$ separated by a distance $r$. When these two masses are static, this force obeys an *inverse-square* law:
$$
\mathbf{F(r)} = -\frac{GMm}{r^2}\mathbf{\hat{r}}
$$
denoting the vector between them as $\mathbf{r}$, its corresponding unit vector as $\mathbf{\hat{r}}$, and its magnitude as $r$.

1. The electromagnetic force, acting between two point particles with charges $Q$ and $q$ separated by a distance $r$. This force satisfies an *inverse-square law* too, but it's a *different* one:
$$
\mathbf{F(r)} = \frac{Qq}{4\pi \epsilon_0 r^2}\hat{\mathbf{r}}
$$
<h6>(and also Maxwell's equations maybe?)</h6><br/>

1. The strong nuclear force. Um, that one involves, like, neutrons and protons and morons and stuff, and it holds them together or something. It's also really strong. (Totally.)
2. The weak nuclear force. This one <h6>(*mumble*) radioactive decay (*mumble*) (*mumble*) (*more incoherent mumbling*) atoms and electrons.</h6> 

And that's all I got, folks! 

## Inverse-square unification

Why do the formulas for the gravitational and electromagnetic forces both roughly follow an inverse-square law, differing only by a constant, a sign (which signifies gravitational attraction and electrostatic repulsion), and the name of the wrinkled old bastard now enshrined upon it - that is, within a static frame of reference where both objects aren't moving? 

Certainly, any surface-level similarities dissolve away completely when the objects begin to move; but the fact that an inverse-square law codifies both forces suggests some shared origin at play. That shared origin has everything to do with the underlying force fields at work: the gravitational and electric fields, respectively. 

Suppose that two objects - one with mass $M$ and charge $Q$, the other with mass $m$ and charge $q$, with $M >> m$ and $Q >> q$ - are stationary with distance vector $\mathbf{r}$ in space. Given such a disparity in mass and charge, the effects enacted by the weakly-charged object on the strongly-charged object are negligible. 

We are thus able to derive the *gravitational field strength* and *electric field strength* of the strongly-charged object at a point $\mathbf{x}$ occupied by the weakly-charged object as
$$
\mathbf{g(x)} = \frac{\mathbf{F_{grav}(x)}}{m} = -\frac{GM}{r^2}\mathbf{\hat{r}}
$$
and
$$
\mathbf{E(x)} = \frac{\mathbf{F_{electric}(x)}}{q} = \frac{Q}{4\pi\epsilon_0 r^2}\mathbf{\hat{r}}
$$
with distance vector $\mathbf{r}$ between the two objects, respectively. This doesn't tell us anything new, necessarily; they're just consequences of the inverse-square laws we had at the beginning. But what *could* tell us something new is whether or not we can derive these field equations from common principles. Specifically, that common principle is:

> <span style="background-color: #03cafc; color: black;">Definition</span>. **The Gaussian principle**. The total field strength emanating from a point in space - be the field gravitational or electric - is proportional to the quantity of mass or charge present at that point.

This statement is fairly intuitive: after all, it makes sense that the more the mass, the more the field strength/attraction (and vice versa).

> Betcha you thought I was gonna make a "your mom" joke there! Well, I'm far too classy to do that. I'm saving that for our later section on poles.

It also helps that the notion of "field strength emanating from a point" lends itself nicely to the concept of divergence, in mathematical language: 

$$
\nabla \cdot \mathbf{g} \propto \rho(\mathbf{x}) 
$$
where $\rho$ denotes (mass) density at point $\mathbf{x}$ in $\mathbb{R^3}$ of the object of mass $M$, and similarly
$$
\nabla \cdot \mathbf{E} \propto \rho_e(\mathbf{x})
$$
for electric field strength $\mathbf{E}$ and *charge density* $\rho_e$ of the object. Experimental results verify that the constant of porportionality is $-4\pi G$ with $G$ the gravitational constant and $\pi$ the circle constant for the gravitational field, with the negative sign signifying attraction, and $1/\epsilon_0$ for that other one. (I don't have a favorite.) Thus, purely out of the fundamental intuition that field strength is proportional to density, we have:
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Gauss' Law**.

$$
\begin{cases}
\nabla \cdot \mathbf{g} = -4\pi G \rho(\mathbf{x}) \\
\nabla \cdot \mathbf{E} = \rho_e(\mathbf{x})/\epsilon_0.
\end{cases}
$$
This is specifically known as Gauss' Law in *differential form*, not to be confused with the other 493 Gauss' Laws, or the 1,928 Gauss' Theorems, or the middle name of my second-born child.

Happily, this statement involves an expression of divergence; and all our Spidey-Senses tingle as we buckle up for a surface integral of epic proportions for both the above fields:

$$
\int_V \nabla \cdot \mathbf{g}\ dV = \oiint_{dV} \mathbf{g} \cdot \mathbf {dS}
$$
where finally the worldrending powers of $\oiint$ are unleashed, and 
$$
\int_V \nabla \cdot \mathbf{E}\ dV = \oiint_{dV} \mathbf{E} \cdot \mathbf {dS}.
$$
The simplest such region in $\mathbb{R^3}$ and its corresponding surface in the context of these fields is a ball and its boundary sphere. For such an object, the direction of both fields at a point $\mathbf{x}$ - $\mathbf{g}$ and $\mathbf{E}$ - are proportional to the vector $\mathbf{r}$ between the origin point of the field and $\mathbf{x}$; as such, on the surface of the sphere, $\mathbf{g}$ and $\mathbf{E}$ are everywhere normals to the sphere. 

As such, the left-hand side volume integrals evaluate to 
$$
\int_V \nabla \cdot \mathbf{g}\ dV = \int_V -4\pi G \rho(\mathbf{x})\ dV = -4\pi G \int_V\rho(\mathbf{x})\ dV = -4\pi G M
$$
as the volume integral of density is mass, with the volume in question being centered around the object with mass $M$, *whether or not it is a point mass* - the object can be any size or shape. This also extends to the electric field, whose volume integral evaluates similarly to
$$
\int_V \nabla \cdot \mathbf{E}\ dV = \frac{Q}{\epsilon_0}
$$
as the volume integral of charge density is charge. 

Simultaneously, by the statement of the Divergence Theorem above we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The **integral form** of Gauss' Law.
$$
\begin{cases}
\oiint_{dV} \mathbf{g} \cdot \mathbf {dS} = -4\pi G M \\
\oiint_{dV} \mathbf{E} \cdot \mathbf {dS}.= \frac{Q}{\epsilon_0}.
\end{cases}
$$
Call this the *integral form* of Gauss' Law. As a consequence of the Divergence Theorem, we know that we could've started with either the integral or the differential forms and ended up with the other; and, even more pleasingly, the integral form also makes just as much sense to us (intuitively speaking) as the differential form does. In plainer terms, it says simply this:

> The amount of gravitational or electric field flowing out of an object is proportional to the amount of mass or charge present in that object. 

Compare this with the differential form of Gauss' Law for a single point. Evaluating the surface integrals directly is also fairly simple: as stated, $\mathbf{g}$ and $\mathbf{E}$ are everywhere parallel to the normal surface-area component $\mathbf{dS}$, leading to
$$
\oiint_{dV} \mathbf{g\cdot dS} = (\text{surface area of sphere})\ g(\mathbf{r}) = 4\pi r^2(\mathbf{g(r)}) = -4\pi GM
$$
yielding
$$
g = -\frac{GM}{r^2}
$$
recovering Newton's Law of Gravitation, and similarly
$$
E = \frac{Q}{4 \epsilon_0 \pi r^2}
$$
recovering Coulomb's Law for a spherical region in space. (Gauss' laws in differential form also form the first of Maxwell's equations.)

All this physicist mumbo-jumbo tells us just two important things:

1. Both the electric and gravitational forces satisfy inverse-square laws because they originate from the same physical principle: that field strength is proportional to density.

2. Through Gauss' Law and applications of the Divergence Theorem, gravitational and electric field strengths aren't only applicable to point masses; in fact, they're applicable to spheres (as above) and indeed objects of any shape or size (and in any dimension), as we'll soon see below - with the Poisson equation.

> Incidentally, another consequence of Gauss' Law is that because the volume integral above doesn't care how the density is distributed inside the sphere, you could have an object that's entirely hollow on the inside and it would still look fine to the equations. This is yet another instance of math being a fantastic metaphor for how my life is going right now.

## The Poisson and Laplace Equations

Suppose that we now want to find, as before, the electric field strength $E$ (or gravitational field strength $g$) some distance $r$ away from an object with mass $M$ - but with the twist that the object may not be spherical; indeed, it could just as well be a square, one of Shrek's ears represented as a Gabriel's Horn, a $\pi^{\pi^{69420}}$-pixel-resolution Mandelbrot set, or a cylinder of length 5.5 inches and girth 3.1 inches encased in a M&Ms-tube filled with peanut butter, jelly, and mashed bananas. 

The left-hand volume integral
$$
\int_V \nabla \cdot \mathbf{g}\ dV
$$
proceeds exactly as expected; the issue lies with the right-hand side flux integral, where the dot product $\mathbf{g\cdot dS}$ is no longer guaranteed to be sympathetic to our ambitions - unlike such a dot product for a spherical object, where field lines were always normal to the surface. 

The new identity entering the fray here originates from one place and one place only: conservatism. (This is a sentence no human being has ever uttered in the history of the universe, and will never utter again.) Physically, we know that both gravitational and electric forces are **conservative**, not because it likes to start conversations at the dinner table with "I'm not racist, but..." and eschew the virtues of supply-side economics, but because of two reasons:

1. *Conservatism* for a force field means that conservation of energy is achieved no matter what path a particle takes between two points. If this weren't true, this would imply that if you climbed a mountain and then climbed back down, there would be a certain pair of paths where you would feel more like you just dunked an entire 12-pack of Red Bull than you started.

2. From Gauss' law, both the gravitational and electric field strengths of a point charge are radially symmetrical; they can thus be written in the form
$$
\mathbf{g} = g(r)\mathbf{\hat{r}}
$$
with magnitude dependent only on radius $r$ and not direction. It can be verified that the curl of all radially symmetrical functions are zero:
$$
\begin{aligned}
\nabla \times \mathbf{g} &= \epsilon_{ijk}\nabla_j(g(r)\hat{\mathbf{r}}_k) \\
&= \epsilon_{ijk}(\frac{x_j x_k}{r}g'(r) + g(r)\delta_{jk}) \\
\end{aligned}
$$
which sums to zero due to the antisymmetry of $\epsilon_{ijk}$, noting that $r = \sqrt{x_1^2 + x_2^2 + x_3^2}$. A field with zero curl is conservative by Stokes' theorem, and thus both of the above roads lead back to Rome. (We can check that the inverse-square formulation of the electric field satisfies these equations.)

We know that conservative fields can be written as the gradient of some potential $\Phi$:
$$
\mathbf{g} = \nabla \Phi,\ \mathbf{E} = \nabla \Psi.
$$
This leads us to the differential form of Gauss' Law, where we wrote
$$
\begin{cases}
\nabla \cdot \mathbf{g} = -4\pi G \rho(\mathbf{x}) \\
\nabla \cdot \mathbf{E} = \frac{\rho_{e}(\mathbf{x})}{\epsilon_0}

\end{cases}
$$
with the substitution of the potentials resulting in
$$
\begin{cases}
\nabla^2 \Phi = -4\pi G \rho(\mathbf{x}) \\
\nabla^2 \Psi = \frac{\rho_{e}(\mathbf{x})}{\epsilon_0}
\end{cases}
$$
and finally and at long last, to the
> <span style="background-color: #03cafc; color: black;">Definition</span>. **Poisson equation**. For a scalar-field **source** $\rho(\mathbf{x})$ and a **potential field** $\Phi$, the **Poisson equation** is the partial differential equation
$$
\nabla^2 \Phi = \rho(\mathbf{x})
$$
> for which the above two stated examples are the Poisson equations satisfied by the gravitational and electric potential fields, respectively. 

The special case where the source field vanishes is called

> <span style="background-color: #03cafc; color: black;">Definition</span>. **The Laplace equation**, which is simply formulated as $\nabla^2\Phi = 0$.

