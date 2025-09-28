---
id: rifvn0500fkjo4kkrs9spok
title: Non-Linear Equations
desc: ''
updated: 1737879767808
created: 1737879192101
nav_order: 4
---
This section studies any general equation of the form
$$
Q(x, y)\frac{dy}{dx} + P(x,y) = 0
$$
where, if the power of $y$ or $y'$ is higher than 1, the equation is said to be *non-linear*. Two cases arise for these equations:

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Separable equations).** This case applies for equations that can be separated into the form $f(x) dx = g(y) dy$, making the equation relatively simple as both sides can simply be integrated. For instance, the equation $(3x+2)\frac{dy}{dx} = y$ can be separated into $\frac{dy}{y} = \frac{dx}{3x+2}$, with each side containing one variable only.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Exact equations)**. (Exact equations). We define a DE in the form $Q(x,y)\frac{dy}{dx} + P(x,y) = 0$ to be **exact** if and only if there is a function $f(x,y)$ such that $\frac{\partial f}{\partial x} = P(x,y)$ and $\frac{\partial f}{\partial y} = Q(x,y)$; that is, if $Q(x,y)$ is one partial derivative of $f$ and $P$ is the other partial derivative.

Alternatively, if the equation is rewritten $Q(x,y) dy + P(x,y) dx = 0$, it is exact if and only if there is a function $f(x,y)$ such that $df = P\ dx + Q\ dy$.

To check whether a DE is exact, notice that mixed second derivatives are equal ($f_{xy} = f_{yx}$); thus, if $P$ and $Q$ are both partial derivatives of the same function $f$, then $P_y$ = $Q_x$. This method only holds if the domain of $f$ is *simply-connected*.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Simply-connected domain.** A domain $\mathbf{D}$ is simply-connected if:
1. The domain is connected (closed) and not open.
2. Any closed loop in $\mathbf{D}$ can be shrunk to a point that is still on $\mathbf{D}$.

For instance, a sphere is simply-connected while a donut is not. Yum!

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$ through a simply-connected domain $\mathbf{D}$, then the differential equation $Qy' + P = 0$ is exact.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Solving exact differential equations)**. 

If it is known that $df = P\ dx + Q\ dy$, then $f(x,y) = \lambda$ for some constant $\lambda$ is a solution to the DE. In order to find $f$, we integrate $\frac{\partial f}{\partial x} = P$ with respect to $x$, giving a function plus a function depending only on $y$ (due to $y$ being held constant in the partial derivative).

This result can then be differentiated with respect to $y$ to obtain $\frac{\partial f}{\partial y} + h'(y) = Q + h'(y)$, which can be compared to $Q$ to obtain $h'(y)$. This can be best illustrated with the following example.

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the general solution to $6y(y-x)\frac{dy}{dx} + (2x-3y^2) = 0$.
 
> <span style="background-color: #1eff12; color: black;">Solution</span>.

Set $Q = 6y(y-x), P= 2x-3y^2$. Then $P_y = -6y = Q_x$, meaning that the differential form is exact. First integrate $P$ with respect to $x$:
$$
        f = \int P \ dx = \int \frac{\partial f}{\partial x} \ dx  = \int 2x-3y^2 \ dx =x^2 - 3xy^2 + h(y)
$$
for some function $h(y)$ depending only on $y$. Differentiating this with respect to $y$ gives
$$
        Q + h'(y) =6y^2 - 6xy + h'(y) =  -6xy
$$
and thus $h'(y) = -6y^2, h(y) = -2y^3 + C$ for a constant $C$. The final solution is $f = x^2 - 3xy^2 + h(y) = x^2 - 3xy^2 - 2y^3 = C$.




