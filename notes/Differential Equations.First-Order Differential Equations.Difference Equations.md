---
id: x1ozstkcytqvkx3eu95ztmo
title: Difference Equations
desc: ''
updated: 1737882520799
created: 1737880744321
nav_order: 7
---
Difference equations are the discrete counterpart to differential equations; in essence, whereas differential equations are concerned with the rate of change of a continuous function, difference equations concern the change of a sequence. For instance, in the logistic population model, instead of a continuous change in population, population may change per season (spring or winter). 

> <span style="background-color: #03cafc; color: black;">Definition</span>. We define a **difference equation** using terms similar to that of differential equations. For difference equation in $y(x)$, if $y_{n-1}$ is analogous to $y(x)$, then $y_{n}$ is analogous to $y'$, $y_{n+1}$ to $y''$, etc. We can also classify difference equations in similar ways to differential equations:
1. Whether the equation is **linear**, i.e. whether it features powers of $y$ beyond the first.
2. Whether the equation is **homogeneous**, i.e. features the variable $x$.
3. The **order** of the equation, i.e. how many of $y_{n}, y_{n-1}, ...$ does it feature?

Difference equations also have fixed points, such as in the following example:

> <span style="background-color: #03cafc; color: black;">Example</span>. Investigate the stability of the fixed points of the difference equation
$$
    u_{n+1} = 4u_n(1-u_n).
$$

> <span style="background-color: #1eff12; color: black;">Solution</span>.

A *fixed point* of a difference equation is a point $u_n$ such that $u_{n+1}=u_n$, thereby making all following terms equal to $u_n$ as well (the sequence is "fixed" at that value). If a certain $u_n = u^*$ satisfies this property, then we have $u_{n+1} = 4u^*(1-u^*) = u^*$, which yields $3u^*=4(u^*)^2$ - a quadratic in $u^*$ with solutions $u^* = 0, \frac{3}{4}$. 

To investigate the stability of these fixed points, we employ a similar method to that of DEs: let $\epsilon$ represent a small perturbation from the fixed point $u^*$ and consider the value of $u_{n+1}$ if $u_n$ instead equaled $u^* + \epsilon_n$. 

Denote $u_{n+1}$ by $f(u_n)$; also let $u_{n+1}$ equal $u_n + \epsilon_{n+1}$, where $\epsilon_{n+1}$ is the perturbation of $u_{n+1}$ away from the fixed point $u_n$ that we are trying to find. At $u_n = u^* + \epsilon$, $u_{n+1} = u_n + \epsilon_{n+1} = f(u^* + \epsilon) \approx f(u^*) + \epsilon_n f'(u^*)$; as $u^*$ is a fixed point, $f(u^*) = u_n$ and so $\epsilon_{n+1} \approx \epsilon_n f'(u^*)$. 

This is analogous to the perturbation theorem for differential equations, and yields that $\epsilon_{n} = \epsilon_0 [f'(u^*)]^n$ due to it following a geometric progression, for some initial perturbation $\epsilon_0$. As such, if $|f'(u^*)| > 1$ the perturbation diverges with an unstable fixed point, and if $|f'(u^*)| < 1$ it converges and the fixed point is stable. 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Fixed point stability for difference equations**. For thee autonomous difference equation
$$
u_{n+1} = f(u_n)
$$
> analogous to the autonomous system
$$
\frac{dy}{dx}=f(y),
$$
> the stability of the point $u^*$ is determined by the value of $|f'(u*)|$: if $|f'(u^*)| > 1$ the perturbation diverges with an unstable fixed point, and if $|f'(u^*)| < 1$ it converges and the fixed point is stable. 

Applying this statement to the fixed points $u^* = 0, \frac{3}{4}$ with $f'(u^*) = 4 - 8u^*$ yields instability for both points. 
