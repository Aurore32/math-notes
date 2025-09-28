---
id: hrvwtwdmpo21tmwzsiyy8un
title: Directional Derivative and Gradient
desc: ''
updated: 1738387288065
created: 1738387043055
nav_order: 1
---
 Before we can be concerned with differential equations, we have to concern ourselves with rates of change.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Gradient for multivariate functions).** Define $\nabla f$, the \it gradient \normalfont of $f(x,y)=z$, as the vector

$$
\nabla f = \begin{bmatrix}
            \frac{\partial f}{\partial x} \\
            \frac{\partial f}{\partial y}
        \end{bmatrix}
$$
> and for the generalized multivariate case, a column vector of partial derivatives of $f$ with respect to all its variables.


Note that this is simply a definition; we haven't attached any geometric significance to the gradient yet, but we will - eventually. 

To get there, consider the following question. We know that $\frac{\partial f}{\partial y}$ gives us the rate of change of $f$ with small changes in $x$, and the partial derivative in $y$ with small changes in $y$; however, what if we choose to move not along one of the axes, but (as is possible in three dimensions) along a certain vector? For instance, take the unit vector
$$
\vec{s} = \begin{bmatrix}
        a \\ b
    \end{bmatrix}
$$
for some $a$, $b$ with $\sqrt{a^2+b^2}=1$. If we're going to be moving along $\vec{s}$, then we'll be moving $a$ units in the $x$-direction and $b$ units in the $y$-direction. The partial derivatives give us how much $f$ changes when we move along each direction, so we can write 
$$
\frac{\partial f}{\partial s} = a\frac{\partial f}{\partial x} + b\frac{\partial f}{\partial y}
$$
as the rate of change of $f$ along $\vec{s}$. Note that we can also rewrite the above as 
$$
\frac{\partial f}{\partial \vec{s}} = \nabla f \cdot \vec{s} \ (\text{notated }\nabla_{\vec{s}} f)
$$
which gives us an insight on what the gradient represents: essentially, it is a vector representing the "base" rate of change at a point that all other directional derivatives are based off of. 

We also note that, since the dot product is maximized when $\cos \theta = 1$ and the angle $\theta$ between the two vectors equalling zero, the directional derivative is at a maximum when $\vec{s}$, the direction travelled in, is in the same direction as the gradient. Thus, the gradient is the direction that maximizes the rate of change of the function. If instead $\vec{s}$ is parallel to the gradient, then the directional derivative is zero. 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The gradient $\nabla f$ of a multivariate function $f$ at a certain point is a vector that geometrically symbolizes the direction of greatest rate of change of $f$ from that point.



