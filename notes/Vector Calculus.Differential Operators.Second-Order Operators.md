---
id: z7hgjig8068ld6bvrym4qgi
title: Second-Order Operators
desc: ''
updated: 1751786738110
created: 1741338307619
nav_order: 2
---
## Curling the grad

Let's consolidate our study of irrotational (curl-free) and solenoidal (divergence-free) fields. Together, their properties inform us on how the three differential operators - curl, grad and div - combine together. Irrotational fields are conservative fields, meaning that
$$
\nabla \times \mathbf{F} = 0 \iff \mathbf{F} = \nabla \phi
$$
combining together to give
$$
\nabla \times (\nabla \phi) = 0
$$
for all scalar fields $\phi$. Similarly, solenoidal fields can be written as the curl of another vector field $\mathbf{A}$:
$$
\nabla \cdot \mathbf{F} = 0 \iff \mathbf{F} = \nabla \times \mathbf{A}
$$
also combining together to give
$$
\nabla \cdot (\nabla \times \mathbf{A}) = 0
$$
for a vector field $\mathbf{A}$ defined everywhere in $\mathbb{R^3}$. Altogether, we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. For a scalar field $\phi$ and a vector field $\mathbf{A}$, $\text{curl grad } \phi = 0$ and $\text{div curl }\mathbf{A} = 0$. 

I am morally and ethically obliged to now repeat the one-liner at the beginning of this section I spent exactly thirty-five seconds thinking up while in the shower, for the world to appreciate its genius with newfound perspective:

> Curl, grad and div walk into a bar, in that order. The bartender can't serve them anything because the bar isn't there anymore.

(Please clap.)

The above results also have another interesting consequence: the *Helmholtz Decomposition*, stated below.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Helmholtz Decomposition**. Any general vector field $\mathbf{F}$ in $\mathbb{R^3}$ can be written as a sum of irrotational and solenoidal vector fields:
$$
\mathbf{F} = \nabla\phi + \nabla \times \mathbf{A}
$$
A proof will be given later when morale improves.

## The Laplacian

So $\text{curl}$ + $\text{grad}$ and $\text{div}$ + $\text{curl}$ turned out to be busts; are there any second-order operators, i.e. a combination of two of curl, grad and div, that (a) are nonzero and (b) have any physical meaning at all beyond being identified by a PhD thesis from a severely underfunded college as the seventh-order time derivative of position of a subatomic muon emitted by a supernova exploding seven quintillion light-years away?

The answer is yes.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define **the Laplacian on scalar fields** as the second-order operator
$$
\nabla^2 = \nabla\cdot \nabla = \frac{\partial^2}{\partial x_i \partial x_i}
$$
> denoting summation, to be understood as 
$$
\nabla^2 \phi = \frac{\partial^2}{\partial x^2} \phi + \frac{\partial^2}{\partial y^2}\phi + \frac{\partial^2}{\partial z^2}\phi
$$
> in the three-dimensional case, and more generally
$$
\nabla^2 \phi = \text{div grad }\phi
$$
> where $\phi$ is a scalar field.

On vector fields $\mathbf{F}$, the Laplacian can also be defined via the vector triple product identity

$$
\nabla \times (\nabla \times \mathbf{F}) = \nabla (\nabla\cdot \mathbf{F}) - (\nabla \cdot \nabla)\mathbf{F}
$$
in which the latter term is the Laplacian $\nabla^2 \mathbf{F}$, resulting in

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Laplacian on vector fields**.

$$
\nabla^2 \mathbf{F} = \nabla(\nabla\cdot \mathbf{F}) - \nabla \times (\nabla \times \mathbf{F}) = \text{grad div }\mathbf{F} - \text{curl curl }\mathbf{F}.
$$

## Applications of differential operators

Unless you despise physics with every fiber of your being, differential operators do not disappoint as far as applications go. Prime among these are Maxwell's equations. It is rumored in the Book of Genesis ([[Vector Calculus]]) that on the first day of creation, God said:


$$
\begin{cases}
\nabla \cdot \mathbf{E} = \frac{\rho}{\epsilon_0} \\
\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}\\
\nabla \cdot \mathbf{B} = 0 \\
\nabla \times \mathbf{B} = \mu_0(\mathbf{J} + \epsilon_0\frac{\partial\mathbf{E}}{\partial t})
\end{cases}
$$

> And there was light --

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Maxwell's equations** for the vector fields $\mathbf{E}$ (electric field), $\mathbf{B}$ (bagnetic field), $\mathbf{J}$ (distribution of electric currents) and scalar field $\rho$ (distribution of charge) encompass all we know about electromagnetism and light, or so it is to be believed.

The Laplacian also makes an entrance, particularly in equations studying diffusion of quantities through space, e.g. the heat flow equation ([[Differential Equations.Partial Differential Equations.Heat Equation]]), which also describes, and I quote, the spread of "the smell of that guy who didn't shower before lectures through the room":

$$
\frac{\partial T}{\partial t} = \kappa \nabla^2 T
$$

and the Schr$\ddot{o}$dinger equation, which features Schr$\ddot{o}$dinger saying "we can't tell what position a particle is in until we observe it", then the particle saying "$H(t)|\psi(t)\rangle = i\hat{h}\frac{\partial}{\partial t}|\psi(t)\rangle$", then Schr$\ddot{o}$dinger saying "shut up".



