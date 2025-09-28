---
id: 64t8ptaalufwp8zilizp1g0
title: Line Integals
desc: ''
updated: 1751773210979
created: 1740294342212
nav_order: 2
---
> \> Line integral <br/>
\> (Looks inside)<br/>
\> Curve <br/>
**Are they stupid?**

In the previous section, it was hammered into our heads with lethal force that integrals are the limits of a sum, **not** the area under a curve. This section will bring back that hammer and bring further injury upon your wounds in full force.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Line integrals**. 

Whereas previously we defined a standard Riemann integral to be the limiting value of the sum
$$
\sigma(D,\zeta) = \sum_{i=1}^{n} f(\zeta_i)(t_i - i_{i-1})
$$
as $|D| \to 0$, this sum is conducted only over a specific range - to be specific, the flat line represented by $t_a$ to $t_b$. But what if we conduct the sum over a different range - say the line $y = 2t$, or even (shockingly) a curve?

We'll take that suggestion to heart. Suppose that $\mathbf{x} = r(t)$ is **not** a line, and is instead the parametric curve
$$
r(t) = (x(t), y(t)).
$$
The Riemann sum above sub-divided the flat line from $t_a$ to $t_b$ into infinite partitions - can we do the same thing with the curve? The analogue to doing so would be to consider $n+1$ points on the curve
$$
r(s_0), r(s_1), ..., r(s_n), s_0 < s_1 < ... < s_n
$$
and the **change in position of the curve** between them:
$$
\Delta s_i = |r(s_i) - r(t_{s-1})|
$$
denoting the Euclidean distance. We thus define the line integral of a function $f$ along the curve $\mathbf{x = r}(s)$ to be the limit of the Riemann sum
$$
\sigma(D,\zeta) = \sum_{i=1}^{n} f(\zeta_i)\Delta s_i
$$
as $|D| \to 0$ where $\Delta s_i$ is defined as above; in essence, the sum of the values of the function along the curve multiplied by the little bits of the curve. In integral form, this is written
$$
\int_{r(t)} f(\mathbf{x})\ ds = \int_{s_a}^{s_b} f(r(s))\ ds.
$$

> Integrals are the limits of a sum, not the area under a curve. If integrals were the area under a curve (which they are **not**), however, you could think of the line integral over $r(t)$ as this: the area of a very curvy wall whose top is bounded by $r(t)$. 

Using arc length to evaluate integrals is often quite the hassle, so let's convert back to the original parameter $t$:

$$
\int_{s_a}^{s_b} f(r(s))\ ds = \int_{t_a}^{t_b} f(r(t)) \frac{ds}{dt} dt = \int_{t_a}^{t_b}f(r(t))|r'(t)|\ dt
$$
from previous results. Any parameter $t$ can be used, alongside the associated parameterization of the curve $\psi(t)$; as such, the line integral is invariant with respect to the parameterization of the curve considered.

### Scalar fields

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **scalar field** is a map $\phi: \mathbb{R}^n \to \mathbb{R}$, i.e. a function mapping a vector to a scalar. If the corresponding domain of $\phi$ encompasses the vectors $\mathbf{x} \in \mathbb{R^n}$, denote $\phi$ as $\phi(\mathbf{x})$.

Integrating a scalar field over a curve $C$ with arc length parameterization $\mathbf{r}(s)$ results in the same integral as presented above. We define by convention that the line integral
$$
\int_C ds
$$
is equal to the (positive) arc length of the curve; in particular, this means that the line integral is **directionless**, i.e., if $C$ and $C'$ were the same curve in opposite directions, a line integral of the same function over them would have the same result. We further note the following:

> <span style="background-color: #ffb812; color: black;">Proposition</span>. For a **piecewise smooth curve** $C$ which can be subdivided into a finite number of smooth curves $C_1$, $C_2$, ..., $C_n$, the line integral of a scalar field over $C$ is equal to the sum of the line integrals over the smooth curves.


> <span style="background-color: #03cafc; color: black;">Example</span>. Evaluate $\int_C (2 + x^2 y)\ ds$, where $C$ is the curve given by the upper half of the unit circle $x^2 + y^2 = 1$.

> <span style="background-color: #1eff12; color: black;">Solution</span>.

First parameterize the curve via $x = \cos \theta$, $y = \sin \theta$ for a parameter $0 < \theta < \pi$. As such, we write
$$
\int_C (2 + x^2 y)\ ds = \int_{0}^{\pi} (2 + \cos^2\theta \sin \theta)\frac{ds}{d\theta} d\theta
$$
We proceed either by noting that $ds$ is equal to 
$$
\sqrt{(\frac{dx}{d\theta})^2 + (\frac{dy}{d\theta})^2}\ d\theta = \sqrt{\sin^2 \theta + \cos^2 \theta}\ d\theta = d\theta
$$
by definition, or that the locus of points on the curve can be represented by
$$
\psi(\theta) = \begin{bmatrix}
\cos \theta \\
\sin \theta
\end{bmatrix}
$$
whose derivative, i.e. the tangent vector at point $\theta$, has magnitude $1$ at every point.

Substituting into the original line integral gives
$$
\begin{aligned}
\int_{0}^\pi (2 + \cos^2 \theta \sin \theta) \ d\theta \\
= [2\theta - \frac{\cos^3{\theta}}{3}]^\pi_0 \text{ by substitution}
 \\
= (2\pi + \frac{1}{3}) + \frac{1}{3} \\
= 2\pi + \frac{2}{3}
\end{aligned}
$$

### Vector fields

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **vector field** $\mathbf{F}$ is a map $\mathbb{R}^n\to \mathbb{R}^n$ that maps **each point** in $\mathbb{R}^n$ to a vector in the same space, $\mathbb{R}^n$.

As such, vector-valued functions are not necessarily vector fields; their domain does not necessarily encompass every point in $\mathbb{R}^n$, nor do they map $\mathbb{R}^n$ to vectors in $\mathbb{R}^n$ in general. However, all vector-fields are vector-valued functions. 

This somewhat stringent definition is necessary for the formulation of a line integral over vector fields. Specifically, we define two line integrals of a vector field: one vector-valued, one scalar-valued. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **vector-valued line integral** of a vector field as the vector containing the line integral of all its components. 

For
$$
\mathbf{F(x)} = \begin{bmatrix}
f_1(\mathbf{x}) \\
f_2(\mathbf{x}) \\
\vdots \\
f_n(\mathbf{x})
\end{bmatrix}
$$
we have
$$
\int_C \mathbf{F(x)}\ ds = \begin{bmatrix}
\int_C f_1(\mathbf{x})\ ds \\
\int_C f_2(\mathbf{x})\ ds \\
\vdots \\
\int_C f_n(\mathbf{x})\ ds
\end{bmatrix}
$$
which is directly equivalent to the Riemann sum defining the line integral
$$
\int_C \mathbf{F(x)}\ ds = \sum_{i=1}^n \mathbf{F(x_i)}\Delta s_i = \sum_{i=1}^n \begin{bmatrix}
f_1(\mathbf{x}) \Delta s_i \\
f_2(\mathbf{x}) \Delta s_i \\
\vdots \\
f_n(\mathbf{x}) \Delta s_i
\end{bmatrix}
$$
i.e. this *very literally* interprets the line integral of a vector field as the Riemann sum of the **vector itself**. Such an interpretation, of course, has its uses; most of the time, however, it plays the Benito Mussolini to Herr **Scalar-Valued Line Integral**'s Hitler. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **scalar-valued line integral** of a vector field along a curve $C$ as the Riemann sum of the **magnitude of the vector** in the direction of the curve.

The primary difference between the two interpretations is thus: the vector-valued line integral interprets the integral as a sum of the vector field itself, while the scalar-valued line integral interprets the integral as a sum of the **magnitude** of the vector field. This is particularly useful because many physical quantities are **not** vectors; instead, they are scalars which involve vectors in their expressions. 

The list of such quantities are numerous, and in general include any quantity that represents the magnitude of a vector quantity in a given direction, e.g. electric flux (magnitude of electric field strength in a given direction), magnetic flux (magnitude of magnetic field strength in a giveen direction), and, most significantly, work done by a force:
$$
\text{Work done} = \mathbf{F \cdot s} = |\mathbf{F}||\mathbf{s}|\cos \theta
$$
where $\mathbf{s}$ is the *displacement* of the object the force acts on, and $\theta$ is the angle in-between the force and the direction of travel of the object, i.e. work is equal to the direction traveled multiplied by the magnitude of the force in that direction. 

If instead the object travels along a curve $C$ - i.e. if the object changes its direction of travel at each infinitesimal time-step, with the direction being represented by the change in arc length $d\mathbf{s}$ - the above expression can instead be written as the following line integral:

$$
\int_{C} \mathbf{F \cdot d\mathbf{s}} = \lim_{n \to \infty} \sum_{i=1}^n \mathbf{F(x_i) \cdot \Delta s}
$$
making necessary the fact that the curve $C$, the domain of $\mathbf{F}$, and the range of $\mathbf{F}$ are in the same-dimensional space, as the line integral of $\mathbf{F}$ along $C$ is the sum of the value of $\mathbf{F}$ on points on $C$. Note in particular that $d\mathbf{s}$ is no longer the **magnitude** of the change in arc length; instead, it is the **vector** representing the infinitesimal change in arc length.


If we have
$$
\mathbf{F(x)} = \begin{bmatrix}
F_1(\mathbf{x}) \\
F_2(\mathbf{x}) \\
\vdots \\
F_n(\mathbf{x})
\end{bmatrix}
$$
and the curve $C$ parameterized by $\psi(t)$, with
$$
\mathbf{x} = \psi(t) =  \begin{bmatrix}
\psi_1(t) \\
\psi_2(t) \\
\vdots \\
\psi_n(t)
\end{bmatrix}
$$
and consequently
$$
\psi'(t) = \begin{bmatrix}
\psi_1'(t) \\
\psi_2'(t) \\
\vdots \\
\psi_n(t)
\end{bmatrix} = d\mathbf{s}
$$
then, as a result, the line integral can be re-formulated as
$$
\int_{C} \mathbf{F \cdot d\mathbf{s}} = \int_C \sum_{i=1}^n F_i(\psi(t))\psi_i'(t) \ dt.
$$

Let's have a quick example.

> <span style="background-color: #03cafc; color: black;">Example</span>. Your dad went to the grocery store to get milk. He tells you he will be back in 5 minutes, but it's been three days and he still isn't back. Suppose that the path between your home and the grocery store, then back again, is a full circle with radius 1 centered at the origin in $\mathbb{R}^2$, and that your dad's will to return home can be modeled as an attractive force $\mathbf{F}$, with
$$
\mathbf{F} = \begin{bmatrix}
e^{-x} \\
e^{-y} \\
\end{bmatrix}
$$
> which is exponentially decaying over time. What is your dad's total will to return home over the full journey from home to the grocery store, then back again?

> <span style="background-color: #1eff12; color: black;">Solution</span>.

We interpret the statement "total will to return home" as the total magnitude of the force $\mathbf{F}$ in the direction of the path from the grocery store back home, i.e. the work done by $\mathbf{F}$ in that direction. As such, the desired quantity is given by the line integral
$$
\int_C \mathbf{F \cdot ds}
$$
with the curve $C$ being a full circle with radius $1$ centered at the origin, parameterized by
$$
\mathbf{x} = \psi(t) = \begin{bmatrix}
\cos t \\
\sin t
\end{bmatrix}
$$
with $x= \cos t$ and $y = \sin t$ over the time parameter $0 < t < 2\pi$, yielding
$$
\psi'(t) = d\mathbf{s} = \begin{bmatrix}
-\sin t \\
\cos t
\end{bmatrix}
$$
Substituting back into $\mathbf{F}$ gives the value of the force $\mathbf{F}$ on the curve $C$:

$$
\mathbf{F} = \begin{bmatrix}
e^{-x} \\
e^{-y}
\end{bmatrix} = \begin{bmatrix}
e^{-\cos t} \\
e^{-\sin t}
\end{bmatrix}
$$
and thus
$$
\int_C \mathbf{F \cdot ds} = \int_0^{2\pi} -e^{-\cos t}\sin t + e^{-\sin t}\cos t\ dt
$$
equalling by substitution
$$
[-e^{-\cos t}+ e^{\sin t}]^{2\pi}_0 = (-e^{-1}+1) - (-e^{-1} + 1) = 0.
$$
In conclusion, your dad's total will to return home over the course of a two-way trip from home to the grocery store to get milk is zero.

****

But why? Why will your dad never get home? Does it have to do with the intrinsic qualities of the vector field $\mathbf{F}$, or with the path from home to the grocery store $C$? We're on the cusp of uncovering something essential - but what? Find out on the next episode of Vector Calculus Z!