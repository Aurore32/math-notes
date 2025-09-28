---
id: pw32zcpaxaw6o2os4my2vw5
title: Constant-Coefficient Equations
desc: ''
updated: 1737883049818
created: 1737882639556
nav_order: 1
---
Second-order ODEs with constant coefficients are the simplest case; they can be expressed in the form
$$
    ay'' + by' + cy = f(x)
$$
where $a$, $b$ and $c$ are constants. Our method for solving such equations are to be expected: we first determine the solution to the equivalent homogeneous equation (call this the *complementary function*), then determine the particular integral that would satisfy the inhomogeneous case.

## Complementary functions
The basic idea of finding the complementary function of a second-order ODE boils down to the concept of eigenfunctions in linear algebra. Differentiation can be viewed as a linear map; that is, it satisfies the property $\frac{d}{dx}(au + bv) = a\frac{d}{dx}u + b\frac{d}{dx}v$ for functions $u, v$ of $x$ and constants $a, b$ - this is known as "linearity".

> <span style="background-color: #bc42f5; color: black;">Method</span>. **Characteristic equations**. The two linearly independent solutions to homogeneous linear second-order ODE $ay''+by'+cy=0$ can be obtained as $e^{\lambda_1 x}$ and $e^{\lambda_2 x}$, where $\lambda_1$ and $\lambda_2$ are solutions to the **characteristic equation** $a\lambda^2+b\lambda+c=0$, as long as $\lambda_1 \neq \lambda_2$ (no repeated roots).

If $\lambda_1 \neq \lambda_2$, then the complementary function in full is all possible linear combinations of the two solutions: $Ae^{\lambda_1 x} + Be^{\lambda_2 x}$, where $A$ and $B$ are arbitrary constants.

If $\lambda_1$, $\lambda_2$ are complex conjugates ($a\pm bi$), we have the complementary function $e^{ax}(A \sin bx + B \cos bx)$ by Euler's formula.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Repeated root case).** If the characteeristic equation above yields a repeated root $\lambda_1 = \lambda_2$, we instead have linearly independent solutions $xe^{\lambda x}$ and $e^{\lambda x}$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

If $\lambda_1 = \lambda_2$ (repeated root), we only have one independent solution when two are expected of a second-order ODE; this is called *degeneracy*. In order to find the other solution $y_2$, we set $y_2 = v(x)y_1$ where $y_1$ is the known solution $e^{\lambda_1 x}$; this is particularly convenient for us because we already know that $y_1$ satisfies the equation. Thus, we have:

$$
\begin{aligned}
    a(vy_1)'' + b(vy_1)' + cvy_1 &= 0 \\
    a(v'y_1 + vy_1')' + b(v'y_1 + vy_1') + cvy_1 &= 0 \\
    a(v''y_1 + 2v'y_1' + vy_1'') + bv'y_1 + bvy_1' + cvy_1 &= 0 \\
    (ay_1)v'' + (2ay_1' + by_1)v' + (ay_1''+by_1'+cy_1)v &= 0 \\
\end{aligned}
$$
where the last term is 0 due to the original DE. Therefore, we have
$$
            (ay_1)v'' + (2ay_1' + by_1)v' = 0
$$
Now substitute $y_1$ for $e^{\lambda_1 x}$. We have $av'' + (2\lambda_1 a + b)v' = 0$ (dividing the exponential function off, as it is nonzero); it is known that $a\lambda^2 + b\lambda + c = 0$, so differentiating both sides with respect to $\lambda$ gives $2a\lambda + b = 0$. Thus, our final equation is $av'' = 0$ or $v'' = 0$, yielding that $v$ is a linear function in $x$. 

We finally conclude that, for the repeated root case, our complementary function is $(Ax+B)e^{\lambda x}$ with repeated root $\lambda$ and arbitrary constants $A, B$. 


