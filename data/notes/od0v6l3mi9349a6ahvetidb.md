
Up until this point, we've made many advances on the topic of linear differential equations. We now have a systematic method to determine the solutions of a constant-coefficient DE completely. Using various methods like the Wronskian, Abel's theorem, and variation of parameters, we can even determine particular solutions to any second-order linear DE. But what if the homogeneous equation we are considering does not have constant coefficients - for instance, equations like: 

$$
4x^3y'' - (x^2+1)y' + xy = 0
$$

For differential equations which do not have particularly "nice" (elementary) solutions, power series solutions are the best we can hope for - that is, solutions in the form

$$
y=\sum_{n=0}^{\infty} c_n x^n
$$

(or, equivalently, $c_n (x-x_0)^n$), for finite coefficients $c_0, c_1, \dots$, under the assumption that such a power series will converge. 

Before we begin our study of power series solutions to differential equations, we need to lay out a few basic principles regarding power series: namely, the notions of convergence/absolute convergence/divergence, the concept of the radius of convergence, and the application of the ratio test.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Convergence, absolute convergence, and divergence.)** The power series
$$
y=\sum_{n=0}^{\infty} c_n (x-x_0)^n
$$
> is said to ***converge* **at a point $x$ if the limit 
$$
\lim_{k\to\infty}\sum_{n=0}^{k} c_n (x-x_0)^n
$$
> exists; conversely, if the limit diverges to infinity, the power series is said to ***diverge*.**<br/><br/>
> The power series is said to **absolutely converge** at a point $x$ if the sum of the absolute value of all its terms 
$$
\lim_{k\to\infty}\sum_{n=0}^{k} |c_n (x-x_0)^n|
$$
> also converges. If a series is absolutely convergent at $x$, then it is also regularly convergent at $x$, though the converse is not necessarily true. <br/><br/>
There is a non-negative number $\rho$ such that, for all $|x-x_0|<\rho$, the series converges absolutely, and for all $|x-x_0|>\rho$, it diverges. Call $\rho$ the ***radius of convergence.***

To determine the convergence of a power series, we can apply

> <span style="background-color: #bc42f5; color: black;">Method</span> **(Ratio test)**. For a fixed value of $x$ and for $a_n\neq 0$, consider the limit of the ratio between two consecutive terms: 

$$
\lim_{n\to\infty} |\frac{c_{n+1}(x-x_0)^{n+1}}{c_{n}(x-x_0)^n}|=\lim_{n\to\infty} |x-x_0||\frac{c_{n+1}}{c_n}|=\lim_{n\to\infty}|x-x_0|L
$$

> If this ratio is less than 1, the terms of the power series are shrinking and the series converges absolutely; if it is greater than 1, the terms are increasing and thus the series diverges. If the ratio is 1, then no conclusive statement can be made.

For a convergent power series, taking its derivative is equivalent to adding up the derivatives of all of its terms; that is,
$$
    y'=\sum_{n=0}^{\infty} (c_n (x-x_0)^n)'\ \ \ \ \  (=\sum_{n=0}^{\infty} nc_n (x-x_0)^{n-1})
$$
implying that $y$ is infinitely differentiable at $x_0$. If $y$ indeed has a power series representation at $x=x_0$, we refer to $y$ as *analytic*. This gives us everything we need to establish two more important classifications: ordinary and singular points. Let us return to the general form of our second-order linear DE:

$$
    p(x)y''+q(x)y'+r(x)y=0
$$
which can also be written as 

$$
    y''+\frac{q(x)}{p(x)}y'+\frac{r(x)}{p(x)}y=0
$$

