> The difference between other mathematicians and me is what we do with smooth surfaces. Other mathematicians merely think **about** smooth surfaces; I think **with** a smooth surface.

## Representations of surfaces

A **curve** is a set of points represented by a single parameter; a **surface** is an extension of the notion of a curve to two parameters, i.e.
> <span style="background-color: #03cafc; color: black;">Definition</span>. A **parametric surface** $\mathbf{x = r}(u,v)$, with two parameters $u, v$, is either (again, depending on whether you're asking the question in a quant firm or a mental institution) a locus of points mapped to by a certain mapping from $u,v$, or that mapping itself.

As with curves, the representation of a surface is far from unique; they come in various shapes, sizes, tastes, and colors, from **parametric form** (as above), to explicit representations, to PG-13 representations, to silver with 8GB of RAM, 512GB of disk space, and a OLED 13.8'' touchscreen which kicked the bucket two seconds after my extended warranty expired. (Screw you, Microsoft!) Examples of these representations are given below:

1. **Explicit representations** (NSFW). Directly representing surfaces in Cartesian coordinates without parameterization ~~(gone wrong) (gone sexual)~~:
$$
z = f(x,y)
$$
For instance, a hemisphere of radius $a$ is
$$
z = \sqrt{a^2 - x^2 - y^2}
$$

2. **Implicit representations** are explicit representations, but in the form $F(x,y,z) = 0$:
$$
x^2 + y^2 + z^2 - a^2 = 0.
$$

3. **Parametric representations** map parameters $u$, $v$ to points $\mathbf{x}$ on the surface:
$$
\mathbf{x} = (a\sin u \cos v, a \sin u \sin v, a \cos u)
$$

Of which the last two forms are not unique.

## Normals to surfaces

We draw upon our definition of a **tangent plane** to a function of two variables to define a normal to a surface. For a curve
$$
\mathbf{x} = r(u,v)
$$
at a point $(u_0, v_0)$, two **curves** $x_1 = r(u_0, v)$ and $x_2 = r(u, v_0)$ can be taken by treating each of $u$, $v$ as constant and the other as a variable; each of these curves has tangent vector 
$$
\frac{\partial r}{\partial u}(u_0, v_0),\ \frac{\partial r}{\partial v}(u_0, v_0)
$$
respectively at $(u_0, v_0)$. By our previous definition for a general two-variable function, the tangent plane at $u_0, v_0$ is the plane uniquely determined by two tangents to the surface; as such the tangent plane to $\mathbf{x} = r(u,v)$ has normal vector
$$
\frac{\partial r}{\partial u}(u_0, v_0) \times \frac{\partial r}{\partial v}(u_0, v_0) = \mathbf{x}_u \times \mathbf{x}_v
$$

and thus

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The **unit normal vector** to a surface $\mathbf{x} = \mathbf{r}(u,v)$ at a point $(u_0, v_0)$ is given by
$$
\hat{\mathbf{n}} = \frac{\mathbf{x}_u \times \mathbf{x}_v}{|\mathbf{x}_u \times \mathbf{x}_v|}.
$$

Alternatively, if $\mathbf{x}$ is instead in parametric form $F(\mathbf{x}) = 0$, the gradient $\nabla F$ represents the normal vector (as it is normal to all level curves of the surface).

## Classification of surfaces

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **smooth surface** is a surface with a unique normal at every point, excepting a sign, and with a direction that depends continuously on the position of the surface. A **piecewise smooth** surface is a surface which can be divided into a finite number of smooth surfaces.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Choose the **positive normal direction** of a smooth surface $S$ at a point $P$ as either the direction of the positive normal vector to $S$ at $P$, or the negative normal vector. If this positive normal direction is consistent for every point $P$ on $S$, then $S$ is an **orientable** surface.

An orientable surface can be understood to "have two sides"; a piece of paper is an orientable surface, but a Mobius strip is not (only has one side).

![alt text](./assets/images/image-11.png)

(Note that the "positive normal direction" suddenly changes when you get to the end of the strip!)

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **closed surface** is one that can contain water and have it not spill from a single place; it bounds a solid object. Examples of closed surfaces: spheres, donuts, JFK's head before Nov. 22, 1963. Examples of open surfaces: a piece of paper, my bedroom ceilings, JFK's head after Nov. 22, 1963.

A straight line (excluding tangents, but we don't talk about that) will intersect a closed surface an even number of times (2 for a round balloon, 4 for a sausage balloon, 10,036 for a caterpillar balloon, etc., etc.)

The Arch of Honors (see "Review") can be formed with your right hand to determine the positive normal direction of the surface at a point. 

## Stationary points in surfaces   

In extending the notion of maximum and minimum points to functions $f: \mathbb{R^m \to R}$, we define

> <span style="background-color: #03cafc; color: black;">Definition</span>. Suppose that the above function $f$ is defined on a domain $D$. A point $\mathbf{a} \in D$ is a **local maximum** or a **local minimum** if for all $\mathbf{x} \in D$ **sufficiently close** to $\mathbf{a}$, we have either
$$
f(\mathbf{x}) < f(\mathbf{a}) \text{ or } f(\mathbf{x}) > f(\mathbf{a}).
$$

Note that "sufficiently close" indicates infinitesimal closeness, i.e. $|\mathbf{x} - \mathbf{a}| \to 0$.

Simultaneously, define

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **weak local minimum or maximum** corresponds with the above, except with

$$
f(\mathbf{x}) \leq f(\mathbf{a}) \text{ or } f(\mathbf{x}) \geq f(\mathbf{a}).
$$

Call a strict local maximum or minimum an **extremum**,, and a weak local maximum or minimum a **weak extremum**.

> <span style="background-color: #ffb812; color: black;">Remark</span>. Local extremums are not necessarily global extremums (i.e. maximum or minimum over the entire domain).

We define

> <span style="background-color: #03cafc; color: black;">Definition</span> A **critical point** or **stationary point** $\mathbf{a}$ of the function $f$ is one where $\nabla f(\mathbf{a}) = \mathbf{0}$.

And indeed, as with the univariate case, we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. All extremums on **the interior** of the domain $D$ of $f$ are critical points (excluding those on the boundary).

> <span style="background-color: #1eff12; color: black;">Proof</span> by contradiction (shocking)!

Suppose that a (strong or weak) extremum $\mathbf{a}$ is **not** a critical point of a function $f$, i.e. $\nabla f(\mathbf{a}) \neq 0$. This implies that for at least one of $x_1, x_2, ..., x_m$, say $x_i$, we have
$$
\frac{\partial f}{\partial x_i} = \lim_{h\to 0}\frac{f(\mathbf{a} + h_i) - f(\mathbf{a})}{h} \neq 0
$$
Suppose, without loss of generality, that the above expression is greater than zero. However, we must now also have
$$
\frac{\partial f}{\partial x_i} = \lim_{h\to 0}\frac{f(\mathbf{a}) - f(\mathbf{a}- h_i)}{h} > 0
$$
which leads to
$$
\begin{cases}
f(a+h_i) - f(a) > 0 \\
f(a-h_i) - f(a) < 0
\end{cases}
$$
As $a+h_i$ and $a-h_i$ are both "sufficiently close" to $a$, and one is larger and one is smaller than $f(a)$, $a$ is not an extremum by definition. Points on the boundary are excluded from this argument beecause there will either not be an $a + h_i$ or an $a - h_i$ (you cannot go any distance beyond the boundary, no matter how small).

In simpler words, the crux of the argument is this: if the gradient is nonzero, then the partial derivative is nonzero in some direction. The partial derivative tells you the rate of change of $f$ in that direction, so if you travel in that direction you can increase or decrease the value of the function to your liking - which is not what happens at an extremum, where you can only either increase or decrease the function.

However, it is important to note that although all extremums are critical points, not all critical points are extremums:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Critical points which are not extremums are called **saddle points**, analogous to points of inflection in 1D; they occur when the function is at a maximum in one direction and at a minimum in another direction.

To reach a local maximum or minimum, the function **has to be** a maximum or minimum no matter what direction you're looking at it; for instance, if you sliced $f(x,y)$ along the $x$ and $y$ axes, both cross-sections have to be minimums. 

As the number of variables increases, it is heuristically more and more unlikely that minimums or maximums can coincide in every axis - for instance, a function of 10 variables would have to be a minimum in the $x_1, x_2, ..., x_{10}$ planes to be an actual local minimum - and thus saddle points are expected to be much greater in quantity than extremums.

## Nature of multivariate stationary points

(Shamelessly copied from notes on [[Linear Algebra]] and [[Differential Equations]].)


> <span style="background-color: #03cafc; color: black;">Definition</span>. **Hessian matrix**.

Recall from **Differential Equations** that the **Hessian matrix** for a multivariate function $f(x_1,x_2,...,x_n),\ \mathbb{R^n \to R},$ of $n$ variables was defined
$$
H_{ij} = \frac{\partial f}{\partial x_i x_j}
$$
with the matrix-valued function $H(\mathbf{a})$ for some $\mathbf{a}\in\mathbb{R}^n$ defined as 
$$
H_{ij}(\mathbf{a}) = \frac{\partial f}{\partial x_i x_j}(\mathbf{a}).
$$
If $f$ has continuous second-order derivatives, recall that the mixed second-order derivatives commute, i.e.
$$
H_{ij} = \frac{\partial f}{\partial x_i x_j} = \frac{\partial f}{\partial x_j x_i} = H_{ji}
$$
meaning that $H$ is symmetric. Suppose that $f(\mathbf{a})$ is a critical point of $f$, $\mathbf{a}\in\mathbb{R}^n$: $\frac{\partial f}{\partial x_i} (\mathbf{a}) = 0$ for all $i= 1, 2, ..., n$. To analyze whether $\mathbf{a}$ is a maximum, a minimum, or a saddle point, we consider a small perturbation $\mathbf{a + x}$ near $\mathbf{a}$ with $|\mathbf{x}|<<1$. By Taylor's theorem, we have
$$
f(\mathbf{a}+ \mathbf{x}) = f(\mathbf{a}) + \sum_{i=1}^n \mathbf{x}_i \frac{\partial f}{\partial x_i} (\mathbf{a}) +\frac{1}{2} \sum_{i=1}^n\sum_{j=1}^n \mathbf{x}_i \frac{\partial^2 f}{\partial x_i x_j} (\mathbf{a})\mathbf{x}_j
$$
plus terms with powers of $\mathbf{x}$ above $2$. The term containing the first derivatives are zero as the first derivatives themselves are zero. The second-derivative term can be rewritten in matrix form as
$$
\frac{1}{2}\sum_{i=1}^n\sum_{j=1}^n \mathbf{x}_i H_{ij}(\mathbf{a})\mathbf{x}_j = \frac{1}{2}\mathbf{x}^{T} H(\mathbf{a})\mathbf{x}
$$
This is a form with a real symmetric associated coefficient matrix, and as real symmetric matrices are diagonalizable, it can be simplified to the form
$$
(\mathbf{x}')^T \Lambda \mathbf{x}
$$
where $\Lambda$ is its diagonal matrix of eigenvalues, which allows us to write
$$
f(\mathbf{a+x})-f(\mathbf{a})\approx \frac{1}{2}(\mathbf{x}')^T \Lambda \mathbf{x} = \sum_{i=1}^n \lambda_i(x_i)^2,
$$
which is positive if all the $\lambda_i$ are positive, negative if all the $\lambda_i$ are negative, and indeterminate if there is at least one positive and one negative eigenvalue. These cases correspond to a minimum point (surrounding point $f(\mathbf{a+x})$ larger than $f(\mathbf{a})$), a maximum point (surrounding point $f(\mathbf{a+x})$ smaller than $f(\mathbf{a})$), and a saddle point respectively. 

Thus we arrive at the 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Hessian determinant test.)** The Hessian determinant test for classifying stationary points of multivariate functions is as follows. Let $H = \nabla \nabla f(x,y)$ be the Hessian matrix as defined above:

$$
H = \begin{bmatrix}
            f_{xx} & f_{xy} \\
            f_{yx} & f_{yy}
        \end{bmatrix}
$$

> If the point $(x_0,y_0)$ with associated Hessian $H(x_0,y_0)$ is a stationary point, then we can classify its nature as follows:

$$
\begin{cases}
            \det H>0,\ f_{xx}(x_0,y_0) > 0: \text{ $(x_0, y_0)$ is a minimum.}\\
            \det H>0,\ f_{xx}(x_0,y_0) < 0: \text{ $(x_0, y_0)$ is a maximum.}\\
            \det H<0: \text{ $(x_0, y_0)$ is a saddle point.}\\
            \det H = 0: \text{ the point is indeterminate in nature.}
        \end{cases}
$$
