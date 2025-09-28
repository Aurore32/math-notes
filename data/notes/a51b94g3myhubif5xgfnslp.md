> Course notes for AP Calculus KMS.

## Scalar functions of one variable

Suppose $f(x)$ is a real function of $x \in R$ (as opposed to a fake function, which is three real functions stacked together in a trench coat.)

### Limits

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Limits**. $l$ is the limit of $f(x)$ as $x \to a$ if 
$$
\lim_{x\to a} f(x) = l
$$
Wow. Who's writing these notes, Sherlock Holmes?

> <span style="background-color: #ffb812; color: black;">Remarks</span>.

1. Denote the **left limit** at $x=a$ as $\lim_{x \to a^-}f(x)$; it is the value $f(x)$ approaches at $x=a$ **from the left** of $a$ ($x = a - \epsilon$ for a very small $\epsilon$)
2. Denote the **right limit** at $x=a$ as $\lim_{x \to a^+}f(x)$; it is the value $f(x)$ approaches at $x=a$ **from the right** of $a$ ($x = a + \epsilon$ for a very small $\epsilon$)
3. The left limit may not equal the right limit. For example, $\arctan x$ at $x = 0$. For another example, the speed limit of driving up Mount Everest versus the speed limit of driving down Mount Everest.
4. If the left limit does not equal the right limit, the limit $\lim_{x\to a} f(x) = l$ **does not exist**.

### Continuity

> <span style="background-color: #03cafc; color: black;">Definition</span>. $f(x)$ is **continuous** at a point $a \in \mathbb{R}$ if and only if $\lim_{x\to a}f(x) = f(a)$, i.e. both that the limit exists and that the limit equals the function at that point.

> <span style="background-color: #ffb812; color: black;">Remark</span>. This definition of continuity excludes piecewise functions like

$$
f(x) = \begin{cases}
1, x\neq a \\
0, x = a
\end{cases}
$$
> where the limit exists at $x = a$, but the limit ($\lim_{x\to a} f(x) = 1$) does not equal the function itself ($f(a) = 0$) at that point.

### Differentiability

> <span style="background-color: #03cafc; color: black;">Definition</span>. $f(x)$ is **differentiable** at $x=a$ with derivative $f'(a)$ if
$$
\lim_{x\to a}\frac{f(x) - f(a)}{x-a} = f'(a).
$$

> <span style="background-color: #ffb812; color: black;">Remark</span>. If $f(x)$ is differentiable at $x=a$, it is continuous at $x=a$. This can be seen by multiplying $x-a$ in the limit on both sides.

### Taylor's theorem

Taylor's theorem ranks just barely in the top ten of Taylor's most significant contributions towards humanity, right behind "Firework" and, admittedly, far ahead of "Shake It Off".

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Taylor's theorem**. For a function $f$ differentiable $N+1$ times, 
$$
f(a+h) = f(a) + hf'(a) + \frac{h^2}{2!}f''(a) + ... + \frac{h^n}{n!}f^{(n)}(a) + O(h^{n+1})
$$
> or
$$
f(a+h) = \sum_{k=0}^N \frac{h^k}{k!}f^{(k)}(a) + R_N (h)
$$
> where $R_N(h)$ is the $N+1$th-degree polynomial
$$
R_N(h)=\frac{h^{N+1}}{(N+1)!}f^{(N+1)}(\xi),
$$
> with $a < \xi < a+h$.  In terms of big-O notation, we can also write
$$
f(a+h) = \sum_{k=0}^N \frac{h^k}{k!} f^{(k)}(a) + O(h^{N+1}) 
$$
> for very small $h$.

> <span style="background-color: #ffb812; color: black;">Corollary 1.</span>.
Setting $a = h$ and $h = x-h$ and in the above equation yields
$$
f(x) = \sum_{k=0}^N \frac{(x-h)^k}{k!}f^{(k)}(h) + O((x-h)^{N+1}).
$$
> If $f$ is infinitely differentiable, we instead have
$$
f(x) = \sum_{k=0}^{\infty} \frac{(x-h)^k}{k!}f^{(k)}(h)
$$
> Call this the **Taylor expansion of f(x)** about the point $x=h$.

> <span style="background-color: #ffb812; color: black;">Corollary 2</span>. 
If instead we have $a = 0$ and $h = x$, we obtain the **Maclaurin series** of $f(x)$ (a Taylor expansion about $x=0$):

$$
f(x) = \sum_{k=0}^{\infty} \frac{x^k}{k!}f^{(k)}(0)
$$
> for an infinitely differentiable $f(x)$. These expansions are only valid for a certain **radius of convergence** about the point they are centered upon; this notion will be expanded on later.



## Functions of several variables

Functions of several variables take vectors as either their input or output; i.e. they map from $\mathbb{R}^n$ to $\mathbb{R}^m$, where $n$ and $m$ can be any natural number. For instance,
$$
f(x,y) = k,\ k \in \mathbb{R}
$$
maps a vector $(x,y) \in \mathbb{R^2}$ to $\mathbb{R}$; alternatively,
$$
f(x) = (x, x^2)
$$
maps a real number $x \in \mathbb{R}$ to a vector in $\mathbb{R^2}$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call the subset of $\mathbb{R}^n$ $f$ is well-defined on the **domain** of $f$.

### Limits

With truly astounding mathematical insight and ingenuity, we define the vector or scalar $\mathbf{l}$ in
$$
\lim_{\mathbf{x\to a}}f(\mathbf{x}) = \mathbf{l}
$$
to be the limit of $f$ as $\mathbf{x}$ approaches $\mathbf{a}$, **if and only if** such a limit is independent of the way $\mathbf{x}$ approaches $\mathbf{a}$. This is analogous to a limit existing in 2D if and only if it is the same when approahced from left and right; because higher dimensions have more directions than just left and right, we stipulate that the limit must now be the same when approached from every possible direction. 

> <span style="background-color: #03cafc; color: black;">Example</span>. Consider the function $f(x,y)$ mapping from $\mathbb{R^2 \to R}$
$$
f(x,y) = \begin{cases}
\frac{2xy}{x^2+y^2}, x \neq 0\\
0, x = 0
\end{cases}
$$
> Suppose we are moving on a line parametrized by $(x,y) = (\rho \cos \theta, \rho \sin \theta)$ for a constant $\theta$ (not a constant $\rho$!). Then
$$
f(x,y) = \frac{2\rho^2 \sin \theta \cos \theta}{\rho^2} = \sin 2\theta 
$$
> for all points except $\rho = 0$. As a result we write
$$
\lim_{\rho \to 0}f(x,y) = \lim_{(x,y)\to \mathbf{0}}f(x,y) = \sin 2\theta
$$
> which need not equal zero. As such, $f(x,y)$ has no well-defined limit as $(x,y) \to \mathbf{0}$.

An alternate *epsilon-delta* definition is as follows:

> <span style="background-color: #03cafc; color: black;">Definition</span> (Epsilon-delta definition of limits).  The limit of $f(\mathbf{x})$ as $\mathbf{x\to a}$, denoted
$$
\lim_{\mathbf{x\to a}}f(\mathbf{x})
$$
> is defined to be $L$ if for every $\epsilon > 0$ there is a corresponding $\delta$ such that for every point $\mathbf{x}_0 \neq \mathbf{a}$ within the domain of $f$ and a distance $D$ away from $\mathbf{a}$, where $0 < D < \delta$, 
$$
|f(\mathbf{x_0}) - L| < \epsilon.
$$

This infamous statement needs more than just a bit of clarification, so here goes! 

The limit of $f$ as $\mathbf{x} \to \mathbf{a}$ is the value $f$ approaches as as it gets infinitely close to (but does not fully equal) $\mathbf{a}$. $\mathbf{x_0}$ is a point within the domain of $f$; $D$ is the distance between $\mathbf{x_0}$ and the point $\mathbf{a}$, always larger than zero (meaning that $\mathbf{x_0\neq a}$) but smaller than a certain $\delta$. 

Thus, the above definition states that for **any** $\epsilon > 0$ (meaning infinitesimally small), we are able to find a $\delta > 0$ such that every point $x_0$ a distance $0 < D < \delta$ from $\mathbf{a}$ satisfies
$$
|f(\mathbf{x_0}) - L| < \epsilon,
$$
i.e. $f(\mathbf{x_0})$ can get infinitely close (as $\epsilon$ can be any value) to $f(\mathbf{a})$, from any direction, and not actually equal it.


### Continuity

As before, consider $f(\mathbf{x})$ continuous at $\mathbf{a}$ if
$$
\lim_{\mathbf{x} \to \mathbf{a}} f(\mathbf{x}) = f(\mathbf{a})
$$
Noting that
> <span style="background-color: #ffb812; color: black;">Remark</span>. Suppose that $\mathbf{a} \in \mathbb{R^n} = (a_1, a_2, ..., a_n)$. Then it is **not sufficient** for 
$$
\lim_{x_i \to a_i} f(a_1, a_2, ..., x_i, ..., a_n) = f(a_1, ..., a_n); 
$$
> for all $i = 1,...,n$; i.e. it is not sufficient for the limit to exist when every variable except $x_i$ is held constant and $x_i$ approaches $a_i$. This is because, as mentioned above, the limit must be the same **from every direction** (and not just the direction of the variables $x_1, ..., x_n$!)

## Derivatives of vector-valued functions

Let $\mathbf{f}(x)$ be a **vector-valued** function, i.e. it takes a scalar $x\in \mathbb{R}$ and maps it to a vector in $\mathbb{R^n}$. Define the **derivative** of $\mathbf{f}(x)$ at $x=a$ as
$$
\mathbf{f}'(a) = \lim_{x \to a}\frac{\mathbf{f}(x) - \mathbf{f}(a)}{x - a}
$$
where we can likewise say that $\mathbf{f}$ is differentiable at $x=a$ if this limit exists. If we write
$$
\mathbf{f}(a) = 
\begin{bmatrix}
\mathbf{f}_1(a) \\ \mathbf{f}_2 (a) \\ \vdots \\ \mathbf{f}_n (a)
\end{bmatrix}
$$
notwithstanding my eternal and inextinguishable vitriol towards \begin{bmatrix}, i.e. representing $\mathbf{f}$ as its vector components, then it follows that
$$
\mathbf{f}'(a) = \begin{bmatrix}
\mathbf{f}'_1(a) \\ \mathbf{f}'_2 (a) \\ \vdots \\ \mathbf{f}'_n (a)
\end{bmatrix}
$$
where each of the $\mathbf{f}_k(a)$ are univariate functions ($\mathbb{R\to R}$).

> <span style="background-color: #ffb812; color: black;">Remark</span>. The velocity of a particle with time-varying **position** given by $\mathbf{x}(t)$ at time $t$ is defined to be 
$$
\mathbf{u}(t) = \frac{d\mathbf{x}}{dt}.
$$

> <span style="background-color: #03cafc; color: black;">Example</span>. Let $\mathbf{u}(t)$ be a vector-valued function, and $g(t) = \mathbf{u}(t) \cdot \mathbf{u}(t)$, i.e. the magnitude of $\mathbf{u}$. We thus have
$$
\frac{dg}{dt} = \frac{d}{dt}u_i^2
$$
> by the summation convetion, and
$$
\frac{d}{dt}u_i^2 = 2u_i \frac{d u_i}{dt} = 2\mathbf{u}\cdot \frac{d\mathbf{u}}{dt}
$$
> rewriting in vector form. If we further specify that $\mathbf{u}(t)\cdot \mathbf{u}(t) = |\mathbf{u}(t)| = 1$, then $\frac{dg}{dt} = 0$, implying
$$
\frac{dg}{dt} = 2 \mathbf{u}\cdot \frac{d\mathbf{u}}{dt} = 0
$$
> and that $\mathbf{u}$ is perpendicular to its time derivative.


