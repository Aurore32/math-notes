---
id: lzhy8bvxt01f3gcdtmvvvua
title: Equidimensional Equations
desc: ''
updated: 1737960579722
created: 1737960336774
nav_order: 4
---
We take a brief, contractually-obligated segue from our studies in inhomogeneous equations to arrive at equidimensional DEs.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Equidimensional equations).** Also known as the Euler equation, because of course it is, we define an equidimensional equation to be of the form
$$
        L[y] = x^2y'' + \alpha xy' + \beta y = g(x)
$$

> It is named so because every term ($x^2y'', xy', y$) is of the same dimension; if $y$ was in meters and $x$ in seconds, then $y'$ would be the rate of change of $y$ (m/s), $y''$ would be in m/s$^2$, and so every term in the DE have the same dimensions.

The method behind solving such equations is largely similar to constant-coefficient equations: solving by eigenfunctions.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Solving equidimensional equations by eigenfunctions).**

Notice that $y=x^k$ for any $k$ is an eigenfunction of the equation: e.g. $x^2y'' = x^2(k)(k-1)x^{k-2} = k(k-1)y$, a constant multiple of $y$. Simply set $y = x^k$ to obtain a characteristic equation in $k$:

$$
 k(k-1) + \alpha k + \beta = 0
$$

If there are two real solutions for $k$ - $k_1$ and $k_2$ - then (as the Wronskian would attest) $x^{k_1}$ and $x^{k_2}$ are the two fundamental solutions. The same goes for two distinct complex roots $a+bi$ and $a-bi$:

$$
\begin{aligned}
y &= Ax^{a+bi} + Bx^{a-bi} \\
&= Ae^{\ln x^{a+bi}} + Be^{\ln x^{a-bi}}  \\
&= Ae^{(a+bi)\ln x} + Be^{(a-bi)\ln x} \\
&= Ae^{a\ln x}e^{b(\ln x)i} + Be^{a\ln x}e^{-b(\ln x)i} \\
&= Ax^a(\cos (b\ln x) + i\sin (b\ln x)) + Bx^a(\cos (b\ln x) - i\sin (b\ln x))
\end{aligned}
$$
by Euler's formula. This has real part
$$
Ax^a\cos (b\ln x) + Bx^a\sin (b \ln x)
$$

In order to deal with the repeated root (degeneracy) case, we need a different method as we can no longer multiply the first solution by $x$. Thus, we attempt a substitution:

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Substitution for repeated-root equidimensional equations).**

We don't quite know how to deal with equidimensional equations (with $x^k$ as the solutions) yet, but we do know how to deal with constant-coefficient equations (with $e^{kx}$ as solutions). Let's try the substitution $z=\ln x, \frac{dz}{dx} = \frac{1}{x}$. Then:

$$
\begin{aligned}
    z = \ln x &\iff x = e^z \\
    y(x) &= y(e^z) \\
    \frac{dy}{dz} &= y'(e^z) e^z = xy' \\
    \frac{d^2y}{dz^2} &= e^z y'(e^z) + e^{2z}y''(e^z) = xy' + x^2y''
\end{aligned}
$$
and thus 
$$
\begin{aligned}
    x^2 y'' + \alpha x y' + \beta y = g(x) &\iff (\frac{d^2 y}{dz^2} - \frac{dy}{dz}) + \alpha \frac{dy}{dz} + \beta y = g(e^z) \\
    &= \frac{d^2 y}{dz^2} + (\alpha - 1)\frac{dy}{dz} + \beta y 
\end{aligned}
$$
which is a standard constant-coefficient DE, with characteristic equation $\lambda^2 + (\alpha-1)\lambda + \beta=0$. If there is a repeated root $\lambda$, then:
$$
y = (Az+B)e^{\lambda z} = (A\ln x + B)e^{\lambda \ln x} = (A\ln x + B)x^{\lambda}
$$
which is the desired result for the repeated root case. It is worth noting that, analogously to how we multiply by $x$ when a guess for a particular integral fails, we multiply by $\ln x$ in the case of an equidimensional equation.
