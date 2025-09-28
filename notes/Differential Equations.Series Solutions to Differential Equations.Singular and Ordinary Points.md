---
id: d1ze3vxw7eskbjg40jcqfhh
title: Singular and Ordinary Points
desc: ''
updated: 1738386315573
created: 1738386263875
nav_order: 1
---

We define

> <span style="background-color: #03cafc; color: black;">Definition</span>. (Singular and ordinary points.) If at a certain point $x_0$ the Taylor series (power series) for $\frac{q(x)}{p(x)}$ and $\frac{r(x)}{p(x)}$ do not exist - most commonly because $p(x_0)$ is zero - that point will be a \it singular point\normalfont. Conversely, if the Taylor series of both functions at $x=x_0$ do exist (the functions are analytic), then $x=x_0$ is an ordinary point.

> <span style="background-color: #03cafc; color: black;">Definition</span>.
(Regular and irregular singularities.) Let $x_0$ be a singular point of the aforementioned DE. Then if $\frac{q(x)}{p(x)}$ contains no more than the first power of $(x-x_0)$ in its denominator when simplified, and $\frac{r(x)}{p(x)}$ contains no more than the second power $(x-x_0)^2$ in its denominator, $x=x_0$ is a regular singularity. Otherwise, we deem it to be an irregular singularity.

Why is this so? For some singular points (namely, where $\frac{q(x)}{p(x)}$ and $\frac{r(x)}{p(x)}$ are undefined because $p(x)=0$ at $x=x_0$), the answer is obvious: the coefficients themselves are undefined, meaning that the differential equation would not make sense. However, if - as the definition of a regular singularity goes - the maximum power of $(x-x_0)$ is 2 in $\frac{r(x)}{p(x)}$, and 1 in $\frac{q(x)}{p(x)}$, the power series solution for the DE 
$$
y=\sum_{n=0}^{\infty} c_n (x-x_0)^n
$$
can cancel out these powers of $(x-x_0)$ as long as the first few terms are zero. This leads us to the solution
$$
y=\sum_{n=0}^{\infty} c_n (x-x_0)^{(n+\sigma)},
$$
also known as a Frobenius series, where $\sigma$ can be any complex number with $c_0 \neq 0$. This allows us to "skip" the first few terms of the Taylor series, and cancel out these pesky $x-x_0$ terms in the denominator that result in dividing by zero. If instead the singularity is irregular, then the same method no longer applies; power series solutions may not exist, or may behave strangely, at that particular point.

Finally, at ordinary points where everything is well-defined, analytic, and has power series expansions, we simply have two linearly independent solutions of the form 
$$
y=\sum_{n=0}^{\infty} c_n(x-x_0)^n
$$
about the point $x=x_0$. 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Fuch's theorem).** The second-order differential equation 
$$
y''+p(x)y'+q(x)y=g(x)
$$
> has a power series solution expressible in the form
$$
y=\sum_{n=0}^{\infty} c_n (x-x_0)^{(n+\sigma)}
$$
> near $x=x_0$ if $p(x)$, $q(x)$ and $g(x)$ are analytic at that point, or that point is a regular singular point. If instead $x=x_0$ is an ordinary point, there exists two linearly independent solutions of the form 
$$
y=\sum_{n=0}^{\infty} c_n(x-x_0)^n.
$$