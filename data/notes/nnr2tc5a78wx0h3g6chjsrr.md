Let us present an example of the method of power series near an ordinary point. 

> <span style="background-color: #03cafc; color: black;">Example</span>.  Find solutions as power series in $x$ of the differential equation
$$
y''+xy=0.
$$

> <span style="background-color: #1eff12; color: black;">Solution</span>.

First, we note that $x=0$ is an ordinary point - $x$ is clearly analytic here. As such, the usual power series solution 

$$
y=\sum_{n=0}^{\infty} c_n(x)^n
$$

will work in this case. Substituting into the equation yields 

$$
y'=\sum_{n=1}^{\infty} nc_n(x)^{n-1}
$$

(note that the range of the sum has gone from $n=0$ to $n=1$, as the derivative of the first term in $y$, a constant, is zero). And thus:

$$
y'' = \sum_{n=2}^{\infty} n(n-1)c_n(x)^{n-2}
$$
Substituting into the equation yields
$$
\sum_{n=2}^{\infty} n(n-1)c_n(x)^{n-2}+ \sum_{n=0}^{\infty} c_n(x)^{n+1} = 0.
$$
 We want to shift the ranges of the two sums so that they have the same range and can be merged into a single sum. Inspection gives the first sum as 
$$
\sum_{n=0}^{\infty} (n+2)(n+1)c_{n+2}x^n
$$
and thus the left-hand side of the DE as 
$$
2c_2 + \sum_{n=1}^{\infty}((n+2)(n+1)c_{n+2}+c_{n-1})x^n = 0
$$
It is important to note here that if a power series is zero, then all of its terms must be zero. Thus we can write: 
$$
\begin{cases}
            2c_2=0 \iff c_2 = 0 \\
            (n+2)(n+1)c_{n+2}+c_{n-1} = 0 \iff c_{n+2}=-\frac{c_{n-1}}{(n+1)(n+2)},\ n\geq 1
        \end{cases}
$$
where two independent solutions arise from the values of $c_1$ and $c_2$.

****

Let's now consider an example of solutions near a regular singular point.

> <span style="background-color: #03cafc; color: black;">Example</span>. Consider the differential equation 
$$
 4xy''+2(1-x)y'-y=0.
$$
> Find solutions as power series in $x$.

> <span style="background-color: #1eff12; color: black;">Solution</span>.

First, we convert the above equation to a form with coefficient of $y''$ equal to 1:
$$
y''+\frac{(1-x)}{2x}y'-\frac{1}{4x}y = 0
$$

$x=0$ is a regular singular point (as the power of $x$ in the denominators of $\frac{1-x}{2x}$ does not exceed 1, and in $\frac{1}{4x}$, it does not exceed 2). We know from Fuch's Theorem that there exists a solution of the form 

$$
        y=\sum_{n=0}^{\infty}c_n x^{n+\sigma}
$$
with corresponding derivatives
$$
 y'=\sum_{n=0}^{\infty}c_n(n+\sigma) x^{n+\sigma-1}, \ y'' =\sum_{n=0}^{\infty}c_n(n+\sigma)(n+\sigma -1)x^{n+\sigma-2}
$$
 Substituting into the equation gives:
$$
\sum_{n=0}^{\infty}[4c_n(n+\sigma)(n+\sigma-1)+2c_n(n+\sigma)]x^{n+\sigma-1} - \sum_{n=0}^{\infty}[2c_n(n+\sigma)+1]x^{n+\sigma} = 0
$$
and thus
$$
\begin{cases}
            [4c_0(\sigma)(\sigma-1)+2c_0(\sigma)]x^{\sigma}-1=0 \\
            \sum_{n=0}^{\infty}[2c_{n+1}(n+\sigma)(2(n+\sigma+1)+1)-2c_n(n+\sigma)-c_n]x^{n+\sigma} = 0
        \end{cases}
$$
The first term, involving only $\sigma$, is known as the *indicial equation* (determines the value of the index):
$$
4c_0(\sigma)(\sigma-1)+2c_0(\sigma) = 0 \iff \sigma(\sigma-1)+\frac{\sigma}{2}=0,\ \sigma=0,\ \frac{1}{2}
$$
From the second term we obtain the recurrence relation
$$
2c_{n+1}(n+\sigma)(2(n+\sigma+1)+1)-2c_n(n+\sigma)-c_n=0
$$
or equivalently
$$
c_{n+1}=\frac{1+2(n+\sigma)}{2(n+\sigma)(2(n+\sigma+1)+1)}c_n
$$
where $\sigma = 0,\ \frac{1}{2}$ can be plugged in to obtain two independent solutions.

