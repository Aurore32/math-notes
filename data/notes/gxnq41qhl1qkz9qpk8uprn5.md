
## Gradient and the Gradient Operator

### Defining the Gradient 2: Electric Boogaloo

The gradient of a scalar field $\phi(\mathbf{x}): \mathbb{R}^n \to \mathbb{R}$ is defined as the vector
$$
\frac{\partial\phi}{\partial x_i}\mathbf{e_i},
$$
itself a vector field, where $\mathbf{e_i}$ is the standard orthonormal basis in Cartesian coordinates; this we are well-aware, yet the necessity of restricting the gradient to Cartesian coordinates limits our understanding. If the gradient is the multivariable analogue of the derivative, is it possible to define the gradient independently of choice of coordinates, based simply on first principles?

Consider the definition of the derivative for uni-variate functions:
$$
f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h}
$$
or, for $|h| << 1$,
$$
f(x+h) = f(x) + hf'(x) + O(h^2)
$$
In the multi-variable case, the above holds for every single variable the function is subjected to:
$$
f(\mathbf{x}+\mathbf{h}) = f(\mathbf{x}) + \mathbf{h}_1f_{x_1}(\mathbf{x}) + \mathbf{h_2}f_{x_2}(\mathbf{x}) + ... + \mathbf{h_n}f_{x_n}(\mathbf{x}) + O(\mathbf{h}^2)
$$
and thus 
$$
f(\mathbf{x+h}) = f(\mathbf{x}) + \nabla f(\mathbf{x}) \cdot \mathbf{h} + O(\mathbf{h}^2).
$$
We arrive at

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **coordinate-independent definition of the gradient** defines the gradient $\nabla f(\mathbf{x})$ at a given vector-valued point $\mathbf{x}$ as the vector that satisfies
$$
f(\mathbf{x+h}) = f(\mathbf{x}) + \nabla f(\mathbf{x}) \cdot \mathbf{h} 
$$
> as $\mathbf{h} \to \mathbf{0}$.

### The Gradient Operator

If there's anything mathematicians are great at, it's getting divorced (math comes a distant second), so it's not surprising that we proceed towards the next stage of our mathematical journey via the forceful separation of two mathematical objects that were once joined together by the decree of God. Behold:
$$
\nabla
$$
There is nothing more terrifying.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **gradient operator**, denoted $\nabla$ without the following function, as the quasi-vector-like object
$$
\begin{bmatrix}
\frac{\partial}{\partial x_1} \\
\frac{\partial}{\partial x_2} \\
\vdots \\
\frac{\partial}{\partial x_n}
\end{bmatrix}
$$
> which doesn't make much sense alone, but awaits a scalar function to form the **gradient** $\nabla f$ defined above.

## Curl and Divergence

The existence of the gradient operator, i.e. a vector-form representation of what $\nabla$ does to scalar functions, allows us to generalize the gradient to vector fields $\mathbf{F}: \mathbb{R^n \to R^n}$. 

For a vector field, $\nabla \mathbf{F}$ - the gradient in its previously-understood meaning, i.e. a vector containing each of the partial derivatives of $\mathbf{F}$ - makes little sense because each partial derivative is also a vector. What **does** make sense, however, is the following:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **divergence** of a vector field $\mathbf{F}: \mathbb{R^n \to R^n}$ as the scalar product $\nabla \cdot \mathbf{F}$ with the gradient operator $\nabla$ as above, outputting a scalar field
$$
\text{div } \mathbf{F} = \nabla \cdot \mathbf{F} = \frac{\partial F_i}{\partial x_i}
$$
> understood as index notation.

Besides the scalar-valued analogue obtained via the dot (scalar) product, we naturally come to the vector-valued analogue obtained via the vector (cross) product, viable only in $\mathbb{R^3}$:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **curl** of a vector field $\mathbf{F}$ **exclusively in $\mathbb{R^3}$** as the vector product $\nabla \times \mathbf{F}$, outputting a vector field
$$
\text{curl }\mathbf{F} = \nabla \times \mathbf{F} = \begin{vmatrix}
\mathbf{e_1} & \mathbf{e_2} & \mathbf{e_3} \\
\frac{\partial}{\partial x_
1} & \frac{\partial}{\partial x_2} & \frac{\partial}{\partial x_3} \\
F_1 & F_2 & F_3
\end{vmatrix}
$$
> which, when fully expanded, equals 
$$
\mathbf{e_1}(\frac{\partial F_3}{\partial x_2} - \frac{\partial F_2}{\partial x_3}) + \mathbf{e_2} (\frac{\partial F_1}{\partial x_3} - \frac{\partial F_3}{\partial x_1}) + \mathbf{e_3} (\frac{\partial F_2}{\partial x_1} - \frac{\partial F_1}{\partial x_2}).
$$

### Interpreting curl and divergence

**Divergence**. Consider a single term (non-suffix notation) within the dot product that defines divergence:
$$
\nabla \cdot \mathbf{F} = \sum_{i=1}^n \frac{\partial F_i}{\partial x_i}
$$
$F_i$ is the component of $\mathbf{F}$ along the $x_i$-axis, and so this term asks the question "how fast does the $i$th component of $\mathbf{F}$ change, or **diverge**, along the $x_i$ axis?" 

Adding up the rate of change along all axes at a point gives a value that captures the **total** rate of change of $\mathbf{F}$ at that point: whether $\mathbf{F}$ is coming into, or leaving, that point. 

If divergence is positive at a point $\mathbf{x}$, then the amount of $\mathbf{F}$ leaving the point exceeds the amount of $\mathbf{F}$ entering the point, and so we call $\mathbf{x}$ a **source**; conversely, if divergence is negative, then $\mathbf{F}$ enters the point more than it leaves, and so the point is a **sink**. 

**Curl**. Curl is an immortal eldritch abomination delivered to the mortal plane from the ninth circle of Hell that defies earthly interpretation or understanding. (Also, it measures rotation.)

### Basic properties

> <span style="background-color: #ffb812; color: black;">Property 1</span>. **The linear property**. Grad, div and curl fulfill the properties of **a linear transformation**:

$$
\begin{cases}
\nabla (\alpha f + \beta g) = \alpha \nabla f + \beta \nabla g \\
\nabla \cdot (\alpha\mathbf{F} + \beta \mathbf{G}) = \alpha (\nabla \cdot \mathbf{F}) + \beta (\nabla \cdot \mathbf{G}) \\
\nabla \times (\alpha \mathbf{F} + \beta \mathbf{G}) = \alpha (\nabla \times \mathbf{F}) + \beta (\nabla \times \mathbf{G})
\end{cases}
$$
> for scalar fields $f$ and $g$, vector fields $\mathbf{F}$ and $\mathbf{G}$, and constants $\alpha$ and $\beta$.

> <span style="background-color: #ffb812; color: black;">Property 2</span>. **The Leibniz property**. Each of grad, div and curl fulfill some generalization of the product rule:

$$
\begin{cases}
\nabla(fg) = (\nabla f) g + f(\nabla g) \\
\nabla \cdot (\mathbf{F}g) = (\nabla \cdot \mathbf{F})g + \mathbf{F} \cdot (\nabla g) \\
\nabla \times (\mathbf{F}g) = (\nabla \times \mathbf{F})g + (\nabla g)\times \mathbf{F}
\end{cases}
$$
> noting that the last term is $(\nabla g) \times \mathbf{F}$, rather than the other way around.

Further properties follow from dot-product and cross-product properties of vectors, which $\nabla$ counts itself among.

## Irrotational and solenoidal fields

### Irrotational fields

> <span style="background-color: #03cafc; color: black;">Definition</span>. If we accept unambiguously and wholly without justification that the curl of a vector field $\mathbf{F}$, $\nabla \times \mathbf{F}$, quantifies its rotation at a point, then we find ourselves obliged to define an **irrotational field** - a field which has no rotation - as that which satisfies
$$
\nabla \times \mathbf{F} = 0
$$
> at all points.

The following theorem provides a connection between irrotational fields and conservative fields:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If $\mathbf{F}$ is a vector field defined everywhere on $\mathbb{R^3}$, then irrotational implies conservatism:
$$
\nabla \times \mathbf{F} = 0 \iff \mathbf{F} = \nabla \phi
$$
> for some scalar field $\phi$.

Ronald Reagan *would* be spinning in his grave, but he can't, because conservative implies irrotational.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

If $\mathbf{F} = \nabla \phi$, then we have
$$
\begin{aligned}
\nabla \times \mathbf{F} &= \nabla \times (\nabla \phi) \\
&= \nabla \times (\frac{\partial \phi}{\partial x_i}) \\
&= \epsilon_{ijk} \frac{\partial}{\partial x_j}\frac{\partial}{\partial x_k} \phi \\
&= 0
\end{aligned}
$$
arguing that for every permutation $\epsilon_{ijk}$ and its corresponding $\epsilon_{ikj}$, the mixed second derivatives
$$
\frac{\partial^2\phi}{\partial x_j \partial x_k} = \frac{\partial^2 \phi}{\partial x_k \partial x_j}
$$
are equal, but $\epsilon_{ijk} = -\epsilon_{ikj}$, forming a pair that sums to zero.

Conversely, we find the nearest corner, curl up into fetal position, and cry for the next half-hour. (Or at least, until le Grande Théorème Intégral swoops in and saves us - but that'll be much later!)

> <span style="background-color: #12ffd7; color: black;">Corollary</span>. The above theorem implies that the curl of conservative fields is zero:
$$
\nabla\times (\nabla \phi) = 0
$$
> for some scalar field $\phi$.


### Solenoidal fields

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define a **solenoidal** or a **divergence-free** field as a vector field $\mathbf{F}$ which satisfies $\nabla \cdot \mathbf{F} = 0$ at every point where it is defined.

Solenoidal fields derive their names from **solenoids**: coils of wires that produce magnetic fields $\mathbf{B}$ which are divergence-free, seen below.

![alt text](./assets/images/image-23.png)

No point in the field can be understood as a source or sink; the field leaves and enters each point in equal amounts. Solenoidal fields connect themselves to the concept of curl through the following theorem:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Given a solenoidal field $\mathbf{F}$ satisfying $\nabla \cdot \mathbf{F} = 0$, we have
$$
\mathbf{F = \nabla \times A}
$$
> for some vector field $\mathbf{A}$, provided that $\mathbf{F}$ is defined everywhere on $\mathbb{R^3}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Again, the forward direction is fairly straightforward: if $\mathbf{F = \nabla \times A}$, then we have
$$
\begin{aligned}
\nabla \cdot \mathbf{F} &= \nabla \cdot (\nabla \times \mathbf{A}) \\
&= \nabla \cdot (\epsilon_{ijk}\frac{\partial}{\partial x_j}A_k) \\
&= \frac{\partial}{\partial x_i}(\epsilon_{ijk}\frac{\partial}{\partial x_j}A_k)
\end{aligned}
$$
which vanishes due to symmetry.

Conversely, we now are no longer reduced to crying and vomiting; instead, for an arbitrary point in the plane $(\mathbf{x_0,y_0,z_0})$, we claim an actual solution for $\mathbf{F} = \nabla \times \mathbf{A}$ in the form
$$
\mathbf{A(x)} = (\int_{z_0}^z F_y(x,y,z')\ dz', \int_{x_0}^x F_z(x',y,z_0)\ dx' - \int_{z_0}^z F_x(x,y,z')\ dz',\ 0)
$$
where $x'$ and $z'$ are meant to be dummy variables with no other purpose than to satisfy the cosmic whims of the Fundamental Theorem of Calculus. This construction is neither unique nor aesthetically pleasing nor comprehensible to the human mind, but its saving grace is that its $z$-component $A_z = 0$, simplifying the formula for curl:
$$
\nabla \times \mathbf{A} = \begin{vmatrix}
\mathbf{e_1} & \mathbf{e_2} & \mathbf{e_3} \\
\partial_x & \partial_y & \partial_z \\
A_x & A_y & A_z
\end{vmatrix} = \begin{vmatrix}
\mathbf{e_1} & \mathbf{e_2} & \mathbf{e_3} \\
\partial_x & \partial_y & \partial_z \\
A_x & A_y & 0
\end{vmatrix}
$$
resulting in
$$
\nabla \times \mathbf{A} = \mathbf{e_1}(-\partial_z A_y) + \mathbf{e_2}(\partial_z A_x) + \mathbf{e_3} (\partial_x A_y - \partial_y A_x).
$$
Let's check the terms one by one. FIrst, $-\partial_z A_y$ is
$$
\begin{aligned}
-\frac{\partial}{\partial z}(\int_{x_0}^x F_z(x',y,z_0)\ dx' - \int_{z_0}^z F_x(x,y,z')\ dz') \\ 
= F_x(x,y,z) - 0 = F_x(x,y,z)
\end{aligned}
$$
by the Fundamental Theorem, and because the first integral in the expression is not a function of $z$. Similarly, $\partial_z A_x$ yields $F_y(x,y,z)$ with even less kicking and screaming. Finally, 
$$
\begin{aligned}
\partial_x A_y - \partial_y A_x \\ = \partial_x (\int_{x_0}^x F_z(x',y,z_0)\ dx' - \int_{z_0}^z F_x(x,y,z')\ dz') - \partial_y (\int_{z_0}^z F_y(x,y,z')\ dz') \\
= F_z(x,y,z_0) - \int_{z_0}^z \frac{\partial F_x}{\partial x}(x,y,z')\ dz' - \int_{z_0}^{z}\frac{\partial F_y}{\partial y} F_y(x,y,z')\ dz' 
\end{aligned}
$$
differentiating under the integral sign. As previously we had $\nabla \cdot \mathbf{F} = 0$ by definition, we have
$$
\partial_x F_x + \partial_y F_y + \partial_z F_z = 0 \iff \partial_z F_z = -(\partial_x F_x + \partial_y F_y)
$$
leading to 
$$
\begin{aligned}
F_z(x,y,z_0) - \int_{z_0}^z \frac{\partial F_x}{\partial x}(x,y,z')\ dz' - \int_{z_0}^{z}\frac{\partial F_y}{\partial y} F_y(x,y,z')\ dz' \\
= F_z(x,y,z_0) - \int_{z_0}^z (\partial_x F_x + \partial_y F_y) (x,y,z')\ dz' \\
= F_z(x,y,z_0) + \int_{z_0}^z (\partial_z F_z)(x,y,z')\ dz' \\
= F_z(x,y,z_0) + F_z(x,y,z) - F_z(x,y,z_0) \\
= F_z(x,y,z)
\end{aligned}
$$
as desired.

