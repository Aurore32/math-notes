---
id: gv3pkv58nre5g52cyc6tq73
title: Differentiation and Integration
desc: ''
updated: 1759048980424
created: 1737873391478
nav_order: 1
---
This section will conduct a simple review of the concepts of integration and differentiation to prepare for later concepts in differential equations.

## Differentiation
> <span style="background-color: #03cafc; color: black;">Definition</span> (**Derivatives/differentiation**).
The derivative of a function $f(x)$ with respect to $x$ is interpreted as the rate of change of $f(x)$, and is denoted $f'(x)$ or $\frac{df}{dx}$.
It is defined as $\frac{df}{dx} = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$.

A function is differentiable at x if this limit exists, i.e. it is the same from the left-hand and right-hand side. For instance, $|x|$ is not differentiable at $x = 0$.

## Big-O and small-o notation

> <span style="background-color: #03cafc; color: black;">Definition</span> (**Big-O**). $f(x) = O(g(x))$ as $x$ approaches $x_0$ means that $f(x)$ approaches a constant multiple of $g(x)$ at $x_0$. This means that $f(x)$ is roughly on the order of $g(x)$; e.g. $4x^2 + 3x = O(x^2)$.


> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Small-o)**. $f(x) = o(g(x))$ as $x$ approaches $x_0$ means that $f(x)$ is part of the class of functions for which $f$ is much smaller than $g$ at $x_0$, or $\lim_{x \to x_0} \frac{f(x)}{g(x)} = 0$.

## Basic propositions and theorems

> <span style="background-color: #ffb812; color: black;">Proposition</span>. $f(x_0 + h) = f(x_0) +  f'(x_0)h + o(h)$. ($h$ is some infinitesimal number close to 0, and $o(h)$ denotes some function which is much smaller than $h$ when $h$ approaches 0.)

> <span style="background-color: #1eff12; color: black;">Proof</span>.

We have
$$
    f'(x_0) =  \frac{f(x_0+h) - f(x_0)}{h}
$$
And thus   
$$
    f'(x_0) = \frac{f(x_0+h) - f(x_0)}{h} + o(h)
$$
for some $o(h)$, as the last term is 0 when $h$ tends to 0. Reorganizing terms gives the above.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Taylor's theorem**. For some $f$ which is $n$-times differentiable, we have
$$
    f(x+h) = f(x) + hf'(x) + \frac{h^2}{2!}f''(x) + ... + \frac{h^n}{n!}f^{(n)}(x) + E_n
$$
> where $E_n$ is some function on the order of $O(h^{n+1})$ as $h$ tends to 0. A similar approximation to the sum above is
$$
f(x) = f(x_0) + (x-x_0)f'(x_0) + \frac{(x-x_0)^2}{2!}f''(x_0) + ... + E_n
$$
where, as $n \to \infty$, the Taylor series of $f(x)$ is obtained.

Taylor's theorem ranks just barely in the top ten of Taylor's most significant contributions towards humanity, right behind "Firework" and, admittedly, far ahead of "Shake It Off".

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **L'Hopital's rule**. Let $f(x)$ and $g(x)$ be differentiable at $x = x_0$, and $\lim_{x \to 0} f(x) = \lim_{x \to 0} g(x) = 0$. Then
$$
    \lim_{x \to x_0} \frac{f(x)}{g(x)} = \lim_{x \to x_0} \frac{f'(x)}{g'(x)}.
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Using Taylor's theorem, we have 
$$
    f(x) =  f(x_0) + (x-x_0)f'(x_0) +  o(x-x_0)
$$
as the later terms all contain higher powers of $(x-x_0)$, which is smaller than $(x-x_0)$ as $x$ approaches $x_0$. A similar result can be derived for $g(x)$.
Furthermore, $f(x_0)$ = $g(x_0)$ = 0 when $x$ tends to $x_0$.

As such, we can rewrite the limit as
$$
    \lim_{x \to x_0} \frac{f(x)}{g(x)} = \lim_{x \to x_0} \frac{f(x_0) + f'(x_0)(x-x_0) + o(x-x_0)}{g(x_0) + g'(x_0)(x-x_0)+o(x-x_0)}  
$$
Which is 
$$
    \lim_{x \to x_0} \frac{f(x)}{g(x)} = \lim_{x \to x_0} \frac{f'(x_0) + \frac{o(x-x_0)}{x-x_0}}{g'(x_0) + \frac{o(x-x_0)}{x-x_0}}  
$$
recognizing that $f(x_0)$ = $g(x_0)$ = 0 and dividing by $x-x_0$ throughout. 

By the definition of $o(x-x_0)$, the term $\frac{o(x-x_0)}{x-x_0}$ approaches 0 at $x_0$, thus yielding the rule.

## Integration

> <span style="background-color: #03cafc; color: black;">Definition</span>. (**Integral**). An **integral** is the limit of the sum 
$$
\int_{b}^{a} f(x) \,dx =  \lim_{\Delta x \to 0} \sum_{n = 0}^{N} f(x_n) \Delta x    
$$
> Where $f(x_i) = b + i\Delta x$. The special kind of integral studied in current-level calculus is the Riemann integral, which is the area under the curve, approached by sub-dividing the area into an infinite amount of infinitesimal rectangles.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Fundamental theorem of calculus**. Let $F(x)$ be $\int_{a}^{x} f(t) \,dt$. Then $F'(x) = f(x)$. Note here that we write $\int f(x) \ dx$ as $\int_{}^{} f(t) \,dt$ where the unspecified lower limit indicates an unknown constant of integration. 

## Partial differentiation

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Partial derivatives.** The partial derivative of a multivariate function $f(x,y)$ with respect to $x$ is the rate of change of $f$ as $y$ is kept constant, but $x$ changes. More precisely, it is given by 
$$
    \frac{\partial f}{\partial x} = \lim_{\delta x \to 0} \frac{f(x+\delta x, y) - f(x,y)}{\delta x}
$$

> We write $f_x = \frac{\partial f}{\partial x}$, $f_{xy} = \frac{\partial^2 f}{\partial y \partial x}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If $f$ has continuous second derivatives, then $f_{xy}$ = $f_{yx}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Chain rule for partial derivatives**. For $z=f(x,y)$ and some variable $t$, where $x$ and $y$ can be written as functions of $t$,
$$
\frac{dz}{dt}=\frac{\partial f}{\partial x} \frac{dx}{dt} + \frac{\partial f}{\partial y} \frac{dy}{dt}
$$
> As such we can also write
$$
\int df =  \int \frac{\partial f}{\partial x} dx + \int \frac{\partial f}{\partial y} dy
$$

> <span style="background-color: #bc42f5; color: black;">Method</span>. **Differentiation under the integral sign**. Consider a group of functions $f(x,c)$.
Define $I(b,c) = \int_{0}^{b } f(x,c) \,dx$, and by the fundamental theorem of calculus we have $\frac{\partial I}{\partial b} = f(b,c)$.
However, we also have 
$$
\begin{aligned}
\frac{\partial I}{\partial c} &= \lim_{\delta c \to 0} \frac{I(b, c+\delta c) - I(b,c)}{\delta c} \\
&= \lim_{\delta c \to 0} \int_{0}^{b} \frac{f(x, c+\delta c)  - f(x,c)}{\delta c}\,dx \\
&= \int_{0}^{b} \lim_{\delta c \to 0} \frac{f(x, c+\delta c)  - f(x,c)}{\delta c}\,dx \\
&= \int_{0}^{b} \frac{\partial f}{\partial c} dx
\end{aligned}
$$
> If $b$ and $c$ are both functions of $x$, then we obtain the general result
$$
\begin{aligned}
\frac{dI}{dx} &= \frac{\partial I}{\partial b} \frac{\partial b}{\partial x} + \frac{\partial I}{\partial c} \frac{\partial c}{\partial x} \\
&= f(b(x), c(x))b'(x) + c'(x)\int_{0}^{b(x)} \frac{\partial f}{\partial c} dy
\end{aligned}
$$
> which makes use of the previous fact that $\frac{\partial I}{\partial b} = f(b,c)$ and $y$ is simply a dummy variable.
