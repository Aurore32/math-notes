---
id: 9iwoo2vtyjjut6weur45ae3
title: Nonhomogeneous Equations
desc: ''
updated: 1737884133406
created: 1737883958432
nav_order: 3
---
We begin with an important result that will be used throughout our discussion in this section:
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. "Nonhomogeneous" shall be used instead of "inhomogeneous" (with certain exceptions, e.g. when I forget to).

> <span style="background-color: #1eff12; color: black;">Proof</span>.     I think "nonhomogeneous" sounds cooler. $\square$

Now that that's out of the way, we move on to less important things. 

> <span style="background-color: #03cafc; color: black;">Definition</span>.  Nonhomogeneous second-order DEs are ones of the form 
$$
    L[y](t) = g(t)
$$
> where $L[y](t)$ is as defined above, and $g(t)$ is any function of $t$ that is nonzero. The equation
$$
    L[y](t) = 0
$$
> is thus referred to as the homogeneous equation corresponding to $L[y](t) = g(t)$, and was discussed at length in the previous section. 

To proceed, we formulate several statements that may seem trivial, but are important to our upcoming discussion:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Solutions to inhomogeneous equations. **    (Solutions to inhomogeneous equations). If $Y_1$ and $Y_2$ are both solutions to a certain inhomogeneous DE $L[y](t) = g(t)$, then $Y_1-Y_2$ is a solution to the corresponding homogeneous equation. 

This can be easily proven by substituting $Y_1$ and $Y_2$ into the DE; thus, we have $Y_1 - Y_2 = c_1 y_1 + c_2 y_2$ for fundamental solutions $y_1$ and $y_2$ and constants $c_1, c_2$. As such, it quickly follows that 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Solutions to inhomogeneous equations. ** The general solution to $L[y](t) = g(t)$ can be fully described by

$$
        y(t) = c_1y_1 + c_2 y_2 + Y(t)
$$

>  where $c_1 y_1 + c_2 y_2$ is the general solution to the homogeneous equation and $Y(t)$ is a specific solution to the inhomogeneous equation.

> <span style="background-color: #1eff12; color: black;">Proof</span>.     As proven by the above theorem, for any two solutions $Y_1$ and $Y_2$ to $L[y](t) = g(t)$, we have $Y_1 - Y_2 = c_1y_1 + c_2y_2$. Thus set $Y_1 = y(t)$ and $Y_2 = Y(t)$ to obtain the desired result.

The implications of the above results inform us on how to approach such inhomogeneous equations:

1. First, we should approach the corresponding homogeneous equation and obtain its solutions.
2. We should then find some specific solution $Y(t)$ to the inhomogeneous equation.
3. The general solution will be the combination of the results of the above two steps.

The second step of finding a specific solution, in particular, is of interest to us in this section. To this end, we present two different approaches:



