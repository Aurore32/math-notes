---
id: 509cman1903g1ylhux4x647
title: Nonlinear Dynamical Systems
desc: ''
updated: 1739435797293
created: 1739435702787
nav_order: 3
---

This section provides an analogue to the technique of stability analysis for a single autonomous ODE, and extends it to a system of ODEs. Consider the second-order system of DEs 

$$
\begin{cases}
        \dot{x}=f(x,y)\\
        \dot{y}=g(x,y)
    \end{cases}
$$

where $x$ and $y$ are functions in $t$. This is an \it autonomous \normalfont system, in the sense that the independent variable $t$ does not appear anywhere in the system. Solving the equations can be nigh-impossible, but through analyzing their fixed points and their stabilities, we can learn many things about them. 

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Equilibrium points.)** As with a single equation, we define an equilibrium point or fixed point of a system of ODEs (such as the one shown above) as a point $(x_0,y_0)$ for which $\dot{x}=\dot{y}=0$.

We observe that this occurs when $f(x_0,y_0)=g(x_0,y_0) = 0$.

To determine the stability of the equilibrium point $(x_0,y_0)$, we consider - as before - a small perturbation $(x_0+\alpha, y_0+\beta)$ from $(x_0,y_0)$. As such we have

$$
\begin{aligned}
        \frac{d}{dt}(x_0+\alpha)&=\frac{d\alpha}{dt}\text{ (left-hand side)} \\
        &=f(x_0+\alpha, y_0+\beta)\text{ (right-hand side)} \\ \\
        \frac{d}{dt}(y_0+\beta)&=\frac{d\beta}{dt}\text{ (left-hand side)} \\
        &=g(x_0+\alpha, y_0+\beta)\text{ (right-hand side)}
    \end{aligned}
$$

and thus by the multivariate Taylor expansion, we have 

$$
\begin{cases}
        \frac{d\alpha}{dt} =f(x_0+\alpha, y_0+\beta) \approx f(x_0,y_0)+\alpha \frac{\partial f}{\partial x}(x_0,y_0) + \beta\frac{\partial f}{\partial y}(x_0,y_0)\\
        \frac{d\beta}{dt} =g(x_0+\alpha, y_0+\beta) \approx g(x_0,y_0)+\alpha \frac{\partial g}{\partial x}(x_0,y_0) + \beta\frac{\partial g}{\partial y}(x_0,y_0)
    \end{cases}
$$

ignoring all second-order and above terms. As $f(x_0,y_0)=0$ by definition of an equilibrium point, we have 

$$
\begin{bmatrix}
        \dot{a} \\\dot{b}
    \end{bmatrix}=\begin{bmatrix}
        f_{x} & f_{y} \\
        g_{x} & g_{y}
    \end{bmatrix}\begin{bmatrix}
        \alpha \\ \beta
    \end{bmatrix}
$$

which is a system of differential equations that we can analyze using the methods demonstrated above. 
