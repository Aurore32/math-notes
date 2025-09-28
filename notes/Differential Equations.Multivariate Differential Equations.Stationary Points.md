---
id: ao91sx24ma0i83ro4uo6spq
title: Stationary Points
desc: ''
updated: 1738388720831
created: 1738387278193
nav_order: 2
---
Consider a point $(x,y)=(a,b)$ on the contours of the function $f(x,y)=z$; in particular, consider its gradient 
$$
 \nabla f = \begin{bmatrix}
        \frac{\partial f}{\partial x} (a,b) \\
        \frac{\partial f}{\partial y} (a,b)
    \end{bmatrix}.
$$
If either partial derivative is nonzero, that implies that we can increase (or decrease) the value of $f$ by taking a small step in that direction; that tells us $(a,b)$ is not a stationary (maximum or minimum) point, as we can reach a higher or lower value of $f$ immediately next to $(a,b)$. Thus, our condition for a critical point is 
$$
\nabla f = \vec{0}
$$
or, equivalently, that all partial derivatives of $f$ are zero at that point. Much as univariate calculus gave rise to points of inflection, however, a special case arises where $\nabla f = 0$ but the point is not a stationary point; call these types of points *saddle points*.

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **saddle point**, analogously to points of inflection for single-variable functions, is a point where the gradient is zero but the function is not locally maximized or minimized.

![alt text](/assets/images/DE-ch4-saddlepoint.png)

Why does this happen? The above graph might give us a bit of a clue; it is the graph of $f(x,y)=x^2-y^2$, with saddle point $(x,y)=(0,0)$. At that point, the function $f(x,0)=x^2$ and the function $f(0,y)=-y^2$ are minimized and maximized respectively; this means that at $(0,0)$, the function curves up in one direction and down in another direction, creating a point where the function is transitioning between turning up and down (similar to points of inflection).

## Taylor series for multivariate functions

Consider a point $\vec{s_0}=(x_0,y_0)$ on $f(x,y)=f(\vec{s})=z$, and a small displacement $\delta \vec{s}=(\delta x, \delta y)$ from that point. We want to find an approximation, similar to the one we obtained for single-variable functions through Taylor series, for the value of:

$$
f(x_0+\delta x, y_0+\delta y) = f(\vec{s_0}+\delta \vec{s})
$$

Let $x = x_0 + \delta x$, $y=y_0 + \delta y$. We'll consider the terms of the approximation one by one. The first term, as is known by Taylor's theorem, is simply $f(x_0,y_0)$. The second term should be equal to the change in $(x_0,y_0)$ multiplied by its rate of change - in multidimensional terms, this is the directional derivative of $\begin{bmatrix}x-x_0\\y-y_0
\end{bmatrix}=\delta \vec{s}$:

$$
f(x,y)=f(x_0,y_0)+\nabla_{\delta \vec{s} f} =f(x_0,y_0)+[(x-x_0)\frac{\partial f}{\partial x} + (y-y_0)\frac{\partial f}{\partial y}].
$$

By Taylor's theorem, the quadratic term will be $\frac{1}{2!}$ times the change in $x$ and $y$, $\delta \vec{s}$, times the second directional derivative in that direction. This is given by 

$$
\begin{aligned}
        \frac{1}{2!}(\nabla_{\delta \vec{s}}\nabla_{\delta \vec{s}})f &= \frac{1}{2!}\nabla_{\delta \vec{s}}[(x-x_0)\frac{\partial f}{\partial x} + (y-y_0)\frac{\partial f}{\partial y}] \\
        &= \frac{1}{2!}\delta \vec{s}\cdot \nabla([(x-x_0)\frac{\partial f}{\partial x} + (y-y_0)\frac{\partial f}{\partial y}])\\
        &= \frac{1}{2!}\delta \vec{s}\cdot\begin{bmatrix}
            (x-x_0)\frac{\partial^2 f}{\partial x^2} +(y-y_0)\frac{\partial^2 f}{\partial x \partial y}\\
            (y-y_0)\frac{\partial^2 f}{\partial y^2}+(x-x_0)\frac{\partial^2 f}{\partial x \partial y}
        \end{bmatrix} \\
        &= \frac{1}{2!}[(x-x_0)^2 \frac{\partial^2 f}{\partial x^2} + 2(x-x_0)(y-y_0)\frac{\partial^2 f}{\partial x \partial y}+(y-y_0)\frac{\partial^2 f}{\partial y^2}]
    \end{aligned}
$$

Note that $(x-x_0)$ and $(y-y_0)$ are not treated as variables in the above because they are $\delta x$ and $\delta y$, independent from $x$ and $y$. According to the above, we define 

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Hessian matrix**. The Hessian matrix for $f(x,y)$ is the matrix
$$
\nabla \nabla f = \begin{bmatrix}
    f_{xx} & f_{xy} \\
    f_{yx} & f_{yy}
\end{bmatrix}
$$
> such that the above quadratic term in the Taylor expansion for $f(x,y)$ can also be written 
$$
 \frac{1}{2!}\begin{bmatrix}
            \delta x & \delta y
        \end{bmatrix}\nabla \nabla f \begin{bmatrix}
            \delta x \\ \delta y
        \end{bmatrix}
$$

The Hessian matrix encodes information about the second-order partial derivatives for $f$. It can be generalized for $f(x_1,x_2,\dots,x_n)$, a multivariate function in $n$ variables, as 

$$
\nabla \nabla f = \begin{bmatrix}
            f_{x_1x_1} & f_{x_1x_2} & \dots & f_{x_1x_n} \\
            f_{x_2x_1} & f_{x_2x_2} & \dots & f_{x_2x_n} \\
            \vdots & \vdots & \vdots & \vdots \\
            f_{x_nx_1} & f_{x_n x_2} & \dots & f_{x_nx_n}
        \end{bmatrix}
$$

and the Taylor expansion term as 

$$
 \frac{1}{2!}(\delta s)^{\mathbf{T}}\nabla \nabla f (\delta s)
$$
where 
$$
\delta s = \begin{bmatrix}
            \delta x_1 \\ \delta x_2 \\ \vdots \\ \delta x_n
        \end{bmatrix}
$$

and the $\mathbf{T}$ indicates matrix transposition.

## Classification of multivariate stationary points

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

We can also refer to this test through the *signature* of the Hessian, which will be useful in higher-dimensional cases. For an $n$-variable Hessian matrix in $(x_1,x_2,\dots,x_n)$, let its signatures be

$$
 f_{x_1 x_1},\ \begin{vmatrix}
            f_{x_1x_1} & f_{x_1x_2}\\
            f_{x_2x_1} & f_{x_2x_2}
        \end{vmatrix},\ \dots,\ \begin{vmatrix}
            f_{x_1x_1} & f_{x_1x_2} & \dots & f_{x_1x_n} \\
            f_{x_2x_1} & f_{x_2x_2} & \dots & f_{x_2x_n} \\
            \vdots & \vdots & \vdots & \vdots \\
            f_{x_nx_1} & f_{x_n x_2} & \dots & f_{x_nx_n}
        \end{vmatrix}
$$

Name these terms $H_1, H_2, \dots, H_n$ respectively. If $H_1, H_2, \dots, H_n$ have signs $+, +, \dots, +$ (all positive) at a certain stationary point, then the point is a local minimum; if the signatures are $-, +, -, \dots, +, \dots$ (alternating signs starting with negative), then the point is a local maximum. Otherwise, if the determinant is not zero, the point is a saddle point.

****  

Why does this hold true? It is beyond our abilities to provide a full proof at the moment, but using the tools of eigenvalues in linear algebra, we can provide an intuitive explanation for all of this. 

We first note that $H$ is "symmetric" no matter how many dimensions or variables there are; when we flip it around the diagonal, it remains the same because for a continuous function, $f_{xy}=f_{yx}$. (This symmetry is most evident in the two-dimensional case). 

A result from linear algebra tells us that because of this symmetry, $H$ can be diagonalized, i.e. it can be written in terms of its eigenvalues:
$$
(\delta \vec{s})^{\mathbf{T}}\cdot H\cdot \delta\vec{s} = \begin{bmatrix}
        \delta x_1 & \delta x_2 & \dots & \delta x_n 
    \end{bmatrix}\begin{bmatrix}
        \lambda_1 & & & \\
        & \lambda_2 & & \\
        & & \ddots & \\
        & & & \lambda_n
    \end{bmatrix}\begin{bmatrix}
        \delta x_1 \\ \delta x_2 \\ \dots \\ \delta x_n 
    \end{bmatrix}
$$

which then equals the sum

$$
 \lambda_1(\delta x_1)^2+\lambda_2(\delta x_2)^2 + \dots + \lambda_n(\delta x_n)^2
$$

where $\lambda_1, \lambda_2, \dots$ denote the eigenvalues of $H$. This is relevant because the above term, $(\delta \vec{s})^{\mathbf{T}}\cdot H\cdot \delta\vec{s}$, is a part of the Taylor expansion of $f$:

$$
f(x_1+\delta x_1, x_2+\delta x_1, \dots, x_n+\delta x_n) =f(x_1, x_2, \dots, x_n) + \delta\vec{s} \cdot \nabla f +  \frac{1}{2} (\delta \vec{s})^{\mathbf{T}}\cdot H\cdot \delta\vec{s}
$$

with $\nabla f$ being 0 at any stationary point, so 

$$
f(x_1+\delta x_1, x_2+\delta x_1, \dots, x_n+\delta x_n) =f(x_1, x_2, \dots, x_n) + \frac{1}{2} (\delta \vec{s})^{\mathbf{T}}\cdot H\cdot \delta\vec{s}
$$

If the point $(x_1, x_2, ..., x_n)$ is a minimum, then we can expect any point close to it to be greater than it; thus, the last term in the above equation must be positive. Conversely, if the point is instead a minimum, any point next to it must be smaller than it, and the last term is a negative. We know that the last term is the sum

$$
 \lambda_1(\delta x_1)^2+\lambda_2(\delta x_2)^2 + \dots + \lambda_n(\delta x_n)^2
$$

which is positive if every eigenvalue is positive (minimum point), negative if every eigenvalue is negative (maximum point), and indeterminate if the signs are mixed (saddle point). This information about eigenvalues, as will become evident in the Linear Algebra course, is encoded within the determinant of the Hessian.


