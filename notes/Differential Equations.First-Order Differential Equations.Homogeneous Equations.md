---
id: d6z8wi85dat6p12e6akcvfs
title: Homogeneous Equations
desc: ''
updated: 1759058666336
created: 1737878723645
nav_order: 1
---
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Any homogeneous linear ODE with constant coefficients has solutions of the form $e^{mx}$ (and all multiples of it). 

> <span style="background-color: #1eff12; color: black;">Proof</span>. The following section will present two derivations of the above statement:

> <span style="background-color: #bc42f5; color: black;">**Method 1 (discrete approximation)**. </span>  

Suppose we are given the differential equation $ay' - by = 0$ for some constants $a$, $b$. One method of approaching this equation 
is to divide it into discrete timesteps of length $h$, for some $h$; that is, to define a sequence $y_0, y_1, y_2, ...$ such that $y_0 = y(0), y_1=y(h), y_2=y(2h)$, and so on. As $y'$ is geometrically the slope of $y$, 
we can write the differential equation above as $a\frac{y_{n+1}-y_n}{h} - by_n = 0$, which yields
$$
    \begin{aligned}
        a\frac{y_{n+1}-y_n}{h}&=by_n \\
        y_{n+1}-y_n &= \frac{bh}{a}y_n \\
        y_{n+1} &= \frac{bh + a}{a}y_n 
    \end{aligned}
$$
applying this formula recursively yields
$$
    y_n = (1 + \frac{bh}{a})^n y_0
$$
Now let $h$ equal $\frac{x}{n}$, such that $y_n = f(\frac{nx}{x}) = f(x)$. As $n$ approaches infinity, the discrete approximation becomes infinitely close to the actual solution of the DE, so
$$
    y = \lim_{n\to \infty} (1+\frac{bx}{a}\frac{1}{n})^n y_0 = y_0 e^{\frac{bx}{a}}
$$
due to the exponential limit.

> <span style="background-color: #bc42f5; color: black;">**Method 2 (Series solution).**</span>

Let $y$ be the Taylor series $y = \sum_{n=0}^{\infty} a_n x^n$, with $y' = \sum_{n=1}^{\infty} n a_n x^{n-1}$. Again consider the DE $ay'-by=0$; substituting $y$ into this equation yields
$$
    \begin{aligned}
        ay' - by &= \sum_{n=0}^{\infty} a(n+1) a_{n+1} x^{n} - \sum_{n=0}^{\infty} ba_n x^n \\
        &= \sum_{n=1}^{\infty} (a(n+1)a_{n+1} - ba_n)x^n \\
        &= 0
    \end{aligned}
$$
(note that the $n+1$ term instead of $n$ originates from the fact that the bounds on the series have been adjusted to $0$ to $\infty$, instead of $1$ to $\infty$).


This implies that every term in the infinite sum is 0, or $a(n+1)a_{n+1} - ba_n = 0$; therefore, we write recursively that $a_{n+1} = \frac{b}{a(n+1)}a_n$. Using this formula yields the general term $a_n = (\frac{b}{a})^n\frac{1}{n!} a_0$. Thus $y = a_0 \sum_{n=0}^{\infty}(\frac{bx}{a})^n \frac{1}{n!}$ which is once again the exponential function $e^{\frac{bx}{a}}$.
