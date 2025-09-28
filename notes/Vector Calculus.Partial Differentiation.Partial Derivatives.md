---
id: 94otf54sqlrwh45msr4awez
title: Partial Derivatives
desc: ''
updated: 1751703632455
created: 1740130227601
nav_order: 3
--- 

> Why do mathematicians want to investigate functions of more than two variables when the paper they use is two-dimensional? Are they stupid?

## Defining partial derivatives

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Partial derivatives** of a multivariate function $f(\mathbf{x}) = f(x_1,x_2, ..., x_n)$ are derivatives **with respect to** a single variable $x_i$ holding **every other variable constant**, but you're a smart cookie, so you knew that already. More precisely, denote this derivative as
$$
(\frac{\partial f}{\partial x_i})_{x_1, x_2, ..., \bar{x_i}, ..., x_n}
$$
> where $\partial x_i$ indicates differentiation with respect to $x_i$, with the little curly $d = \partial$ (joining the ranks of things that are objectively and indisputably better when curly, of which include hair, pigs' tails, and McDonalds' french fries), and the subscript $x_1, x_2, ..., \bar{x_i}, x_n$ represents the variables kept constant (in this case, every variable except $x_i$). 

Partial derivatives thus represent the rate of change of a multivariate function with respect to one variable being changed only. 
The above derivative can be more rigorously defined as the limit
$$
\lim_{h \to 0}\frac{f(x_1, x_2, ..., x_i + h, ..., x_n) - f(x_1, x_2, ..., x_i, ..., x_n)}{h}
$$

> <span style="background-color: #ffb812; color: black;">Remark</span>. There are several alternative ways to denote partial derivatives, including $f_{x_i}$, $D_{x_i}f$, $\partial_{x_i}f$, $\partial_i f$, and the sound of a calculus student quietly shuffling off to the corner of the classroom for a half-hour cry session in the middle of doing their homework. 

> <span style="background-color: #ffb812; color: black;">Remark</span>. Of these alternative notations, one is acceptable, one is slightly less (but still somewhat) acceptable, and the rest are eligible for the death penalty in 126 countries, crimes against humanity charges via Clause 26.8 of the Geneva Convention, and an automatic full score on the Dark Triad quiz (similar to wearing socks before pants, not liking pizza crusts, cutting a brownie from the center out, and being a Linux user).

We will assume you aren't exactly Mr. Norman Newbie or Ms. Amanda Amateur when it comes to calculus, and also that if you want to hear offensively terrible jokes screamed at you with all the force and maturity of a puberty-aged teenager during a raging mood swing you can go follow Elon Musk's twitter account, so let's get down to more serious business:

> <span style="background-color: #03cafc; color: black;">Example</span>. FInd $\frac{\partial}{\partial x} x$.

$$
1.
$$

Feel free to take a deep breath after that arduous intellectual workout. 

As is evident from the above example, partial derivatives are far more difficult than derivatives in one variable, and so in my professional opinion, we have to approach them with a substantially more well-thought-out plan of attack, and with far more finess and expertise:
1. Steal a bunch of paper from your nearest professor's desk, preferably without being caught (even better if toilet paper).
1. Sharpen three Faber-Castell 2B acrylic pencils$^{TM}$ in different colors, or two, or five (one for each variable)
2. Write down your function with each variable being carefully color-coded.
3. Go scream and cry in a corner somewhere for 30 minutes.
4. Repeat step 3.
5. Sharpen the pencils again.
6. Stab yourself with the sharpened pencils because it will be a better experience than spending even another nanosecond on this partial derivative business.

## Directional derivatives

Directional derivatives, as it turns out, **have** been given a thorough treatment in previous courses: they measure the rate of change of a multivariate function when going in the direction of a certain unit vector $\hat{u}$ (*if you're going up a mountain at a 10-degree-angle, or at a 45-degree-angle, or going from this rock to that rock, how fast are you climbing the mountain?*). 

More formally, we can define

> <span style="background-color: #03cafc; color: black;">Definition</span>. With respect to a unit vector $\hat{u} \in \mathbb{R}^n$, define the **directional derivative** of a multivariate function $\mathbf{f(x)}: \mathbb{R^n \to R^m}$ to be
$$
\lim_{h \to 0}\frac{f(\mathbf{x+}h\hat{u}) - f(\mathbf{x})}{h}
$$
> if the limit exists, i.e. the rate of change of $f$ when going up a tiny little step in the direction $\hat{u}$. It can also be measured by
$$
\nabla f \cdot \hat{u}
$$
> where $\nabla$ denotes the gradient (more on this later)!

## Differentiability

Can a function be locally approximated by a linear function? In the univariate case, we call a function *differentiable* if the answer to that question is yes - its tangent line at a point best approximates it linearly at that point. In the multivariate case, this idea is expanded to a *tangent plane* (or a tangent cube, which is quite simply one of the most fantastic combinations of words I've ever encountered); however, we will restrict our three-dimensional minds to the simple case of a two-variable function $f(x,y) = z$.

> <span style="background-color: #03cafc; color: black;">Definition</span> Suppose that at a point $(x_0, y_0, z_0)$, $T_x, T_y$ are the tangent lines to $f$ at that point with respect to the $x$ and $y$-directions respectively (keeping the other direction constant). Then the **tangent plane** to $f$ at $(x_0,y_0)$ is the plane that is formed from the intersection of $T_x$ and $T_y$.

Essentially: the tangent plane as defined above contains the tangent line in all possible directions (and not just the $x$-axis and the $y$-axis!) As the gradients to the tangent lines in the direction of each variable $T_x$ and $T_y$ are given by $f_x(x_0,y_0)$ and $f_y(x_0,y_0)$, we have
$$
z - z_0 = f_x(x_0, y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0)
$$
as the tangent plane passes through $(x_0,y_0,z_0)$. The tangent line is the **best possible** linear approximation to the function $f(x,y)$ at the point $(x_0,y_0,z_0)$; both it and its first derivative equal $f$'s at that point, and the more we zoom in, the more $f$ resembles its tangent plane.

Some functions, however, are naughty and do not behave like their tangent planes imply. Take, from the last section, the example

> <span style="background-color: #03cafc; color: black;">Example</span>.

$$
f(x,y) = \begin{cases}
\frac{2xy}{x^2+y^2}, x \neq 0\\
0, x = 0
\end{cases}
$$
where the partial derivatives $f_x$ and $f_y$ both exist at $(x,y) = (0,0)$, and are both zero. Previously, we verified that the limit of this function does not exist at the point $(0,0)$ because approaching it from different directions give different results; this would imply that the tangent plane does not well-approximate its behavior at $(0,0)$ because it has different behaviors in every direction. Indeed,
$$
z = 0
$$
is the tangent plane at $(0,0)$; yet if we approach $(0,0)$ along the line $y = x$ we instead have $f(x,y) \to \frac{1}{2}$. Call such poorly-behaved functions in multiple variables the same thing we call poorly-behaved functions in one variable: ~~children in need of capital punishment~~ **nondifferentiable functions**.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Differentiable functions** in multiple variables (in this case, two) at a certain point $(x_0,y_0)$ are functions whose tangent plane well-approximates them at that point.

It is lucky indeed that this definition gives rise to another even more elaborate and contrived definition, so let us offer it. Suppose that the **increment** $\Delta z$ of $z = f(x,y)$ near $(x_0, y_0)$ is given by
$$
\Delta z = f(x_0 + \Delta x, y_0 + \Delta y) - f(x_0, y_0)
$$
for very small $\Delta x$ and $\Delta y$. Then if $f(x_0,y_0)$ is **well-approximated** by its tangent plane at that point, we say that
$$
\Delta z = f_x(x_0, y_0) \Delta x + f_y(x_0, y_0)\Delta y + \epsilon_x \Delta x + \epsilon_y \Delta y
$$
where $\epsilon_x, \epsilon_y \to 0$ as $\Delta x, \Delta y \to 0$. Essentially, for very small changes to $x$ and $y$, $f(x,y)=z$ beehaves exactly like the tangent plane.

This definition can be generalized to functions of any domain and range:

> <span style="background-color: #03cafc; color: black;">Definition</span>. Suppose that $\mathbf{f(x)} = \mathbf{f}(x_1, x_2, ..., x_m)$ is a function $\mathbb{R^m \to R^n}$, and let $\Delta \mathbf{f}$ be defined as 
$$
\mathbf{f(x+\Delta x) - f(x)}
$$
> as above. Then if $\Delta\mathbf{f}$ can be approximated linearly by
$$
\Delta \mathbf{f} = T \Delta \mathbf{x} 
$$
> when $\Delta \mathbf{x}$ is small (i.e. the error term $\epsilon(\Delta \mathbf{x})$ tends to zero), where $\Delta \mathbf{x}$ is
$$
\begin{bmatrix}
\Delta x_1 \\
\Delta x_2 \\
\vdots \\
\Delta x_m
\end{bmatrix}
$$
> and $T$ is the $n \times m$ matrix
$$
\begin{bmatrix}
(\frac{\partial f}{\partial x_1})_1 &  (\frac{\partial f}{\partial x_2})_1 & ... & (\frac{\partial f}{\partial x_m})_1 \\
(\frac{\partial f}{\partial x_1})_2 & (\frac{\partial f}{\partial x_2})_2 & ... & (\frac{\partial f}{\partial x_m})_2 \\
\vdots & \vdots & \ddots & \vdots \\
(\frac{\partial f}{\partial x_1})_n & (\frac{\partial f}{\partial x_2})_n & ... & (\frac{\partial f}{\partial x_m})_n
\end{bmatrix}
$$
> which is independent of $\Delta \mathbf{x}$, then $\mathbf{f(x)}$ is **differentiable** at $\mathbf{x} = (x_1, x_2, ..., x_m)$.

The above matrix looks extremely messy, but closer inspection reveals that 
$$
\Delta \mathbf{f} = T \Delta \mathbf{x} 
$$
results in
$$
\Delta \mathbf{f} = 
\begin{bmatrix}
(\frac{\partial f}{\partial x_i})_1\Delta x_i \\
(\frac{\partial f}{\partial x_i})_2 \Delta x_i \\
\vdots \\
(\frac{\partial f}{\partial x_i})_n \Delta x_i \\
\end{bmatrix} = \vec{(\frac{\partial f}{\partial x_i})}\Delta x_i
$$
using summation notation, i.e. $\Delta \mathbf{f}$ is still the sum of the products of $\frac{\partial f}{\partial x_i}$ and $\Delta x_i$ except for the fact that each partial derivative is now a vector instead of a scalar.

An extremely effective **sufficient condition** for differentiability, eliminating the need to dance with limits and frolick in the blood-crazed fields of $\epsilon-\delta$, is

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If the partial derivatives of $\mathbf{f(x)}: \mathbb{R^m \to R^n}$ exist near a point $\mathbf{x} = (x_1, x_2, ..., x_m)$ and are continuous at that point, then $\mathbf{f(x)}$ is differentiable at that point.
