---
id: kl15yfn4in91gcpuv10l999
title: First-Order Differential Equations
desc: ''
updated: 1737878907639
created: 1737877275702
nav_order: 2
---
A differential equation is any equation that involves derivatives; solutions to differential equations are functions which satisfy the equation.
*First-order* differential equations are such equations in which only first derivatives are involved.
## The exponential function

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The derivative of an exponential function is always a constant multiple of itself.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Consider $f(x) = a^x$ where $a$ is a constant. By first principles, the derivative of this function is given by
$$
    \begin{aligned}
    \frac{df}{dx} &= \lim_{h \to 0} \frac{a^{x+h}-a^x}{h}\\
    &= \lim_{h \to 0} \frac{a^{x}(a^h-1)}{h}\\
    &= a^x \lim_{h \to 0}\frac{a^h-1}{h} \\
    &= \lambda a^x
    \end{aligned}
$$
where $\lambda = \frac{a^h-1}{h}$ is a constant because it is equal to $f'(0)$. Therefore, the derivative of an exponential function is always a constant multiple of itself.


In particular, we define
> <span style="background-color: #03cafc; color: black;">Definition</span>.
    **(Exponential function)**. $\exp{x}=e^x$ is the unique function $f(x)$ such that $f'(x)=f(x)$, satisfying $f(0)=1$. We write its inverse function as $\ln x$. The importance of this function is that it is an * eigenfunction * of the differential operator; under the operator, the function is unchanged except for a scalar (constant) multiple.

## Defining and classifying differential equations
> <span style="background-color: #03cafc; color: black;">Definition</span>.
    **(Linear differential equation).** A DE is linear if its dependent variables ($y, y', y''$ etc.) appear only linearly (with powers of 1).

> <span style="background-color: #03cafc; color: black;">Definition</span>.
    **(Homogeneous differential equation).** A DE is homogeneous if $y=0$ is a solution.

> <span style="background-color: #03cafc; color: black;">Definition</span>.
   ** (Differential equation with constant coefficients).** A DE has constant coefficients if the variable $x$ does not appear in the coefficients.

> <span style="background-color: #03cafc; color: black;">Definition</span>.
    **($n$th-order differential equations).** An $n$th-order DE is one which has derivatives of $y$ up to the $n$th derivative.
