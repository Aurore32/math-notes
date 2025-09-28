---
id: cp1tdvhopvnu9t3jk44jvi5
title: The Chain Rule
desc: ''
updated: 1751704599208
created: 1740192686677
nav_order: 4
---
> So apparently derivatives are fractions now.

### The univariate chain rule, revisited

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **composite function** (of one variable) is a function of the form $f(x)$ where $x$ is itself a function of another variable $t$: $x = g(t)$. 

The chain rule in 1D aims to answer the question: if $f$ depends on $x$ and $x$ depends on $t$, how does $f$ change when $t$ change? - i.e. what is $\frac{df}{dt}$? The two ways of notating the result are either
$$
\frac{df}{dt} = f'(g(t))g'(t)
$$
or
$$
\frac{df}{dt} = \frac{df}{dx}\frac{dx}{dt}
$$
but they speak the same meaning: the rate of change of $f$ with respect to $t$ is the rate of change of $f$ with respect to $x$, multiplied by the rate of change of $x$ with respect to $t$. 

> <span style="background-color: #12ffd7; color: black;">Caution.</span> You will use the second notation, and if you use the first notation, I will personally call 911 and notify the Cringe Police of England that it's cringe-o-clock on your sorry ass.

You may have also heard a variety of analogies to justify this statement, each more sensible and life-changing than the last: e.g. "to turn the second gear you have to turn the first", "to eat a M&M you eat the chocolate shell before you eat the filling", "to microwave a pregnant mother you microwave the mother with the baby inside then microwave the baby", etc., etc.

> Is this a consequence of the divergence theorem?

How can this be generalized to more than one dimension?

### The chain rule in 2D

Now consider a function of two variables
$$
z = f(x,y)
$$
where each of $x, y$ are functions of $t$: 
$$
f(x,y) = f(g(t), h(t)).
$$
How does $f$ change with respect to $t$, i.e. what is $\frac{df}{dt}$? The **multivariate chain rule** states that

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Multivariate chain rule, Case 1 (functions of one variable)**. For a (scalar function of two variables $z=f(x,y)=f(g(t),h(t))$, 
$$
\frac{df}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt}
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Think back to the linear approximation of $f$ near an arbitrary point $x, y$, where the **incremental** $\Delta z = f(x+\Delta x, y + \Delta y) - f(x,y)$ equalled
$$
\Delta z = f_x \Delta x + f_y \Delta y + \epsilon_1 \Delta x + \epsilon_2 \Delta y
$$
with the error terms $\epsilon_1, \epsilon_2$ tending to $0$ as $\Delta x, \Delta y$ tend to 0, as long as $f$ is differentiable at that point. As $x = g(t)$ and $y = h(t)$ respectively, we write:
$$
\begin{cases}
\Delta x = g(t+\Delta t) - g(t) \\
\Delta y = h(t+\Delta t) - h(t)
\end{cases}
$$
To obtain $\frac{df}{dt}$, we divide $\Delta z$ by $\Delta t$
$$
\frac{\Delta z}{\Delta t} = f_x \frac{\Delta x}{\Delta t} + f_y \frac{\Delta y}{\Delta t} + \epsilon_1 \frac{\Delta x}{\Delta t} + \epsilon_2 \frac{\Delta y}{\Delta t}
$$
and suppose that $\Delta t$ tends to $0$, so that $\frac{\Delta z}{\Delta t} \to \frac{dz}{dt}$. Then $\Delta x \to g(t) - g(t) = 0$ and similarly $\Delta y \to h(t) - h(t) = 0$; as such $\epsilon_1$ and $\epsilon_2$ both tend to $0$. Therefore
$$
\frac{\Delta z}{\Delta t} = f_x \frac{\Delta x}{\Delta t} + f_y \frac{\Delta y}{\Delta t}
$$
without the error terms, and as
$$
\Delta t \to 0, \begin{cases}
\frac{\Delta z}{\Delta t} = \frac{dz}{dt} \\
\frac{\Delta y}{\Delta t} = \frac{dy}{dt} \\
\frac{\Delta x}{\Delta t} = \frac{ds}{dt}
\end{cases}
$$
we finally have
$$
\frac{df}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt}
$$
as desired. Note that $\frac{df}{dt}$ instead of $\frac{\partial f}{\partial t}$ is used because $f$ is, in reality, a univariate function of $t$.

****

What if each of $x$, $y$ are now themselves multivariate functions, e.g. $x = g(s,t)$, $y = h(s,t)$? Then we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Multivariate chain rule, Case 2 (functions of multiple variables)**. If $z = f(x,y)$ instead equals $f(g(s,t), h(s,t))$ for some functions of two variables $g$ and $h$, then
$$
\begin{cases}
\frac{\partial z}{\partial s} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial s} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial s} \\
\frac{\partial z}{\partial t} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial t} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial t}
\end{cases}
$$
now using $\partial$ instead of $d$ because $z$ depends on more than one variable.

> <span style="background-color: #1eff12; color: black;">Proof</span> is similar to above.

This is a classic example of what is known as "proof by handwaving". of course, the above can also be generalized to functions of any number of variables:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Generalized multivariate chain rule**. Suppose that $\mathbf{f(x) = f}(x_1,x_2,...,x_m)$ is a function of $m$ variables $f: \mathbb{R^m \to R^n}$, with 
$$
\begin{cases}
x_1 = u_1(t_1, t_2, ..., t_l) \\
x_2 = u_2(t_1, t_2, ..., t_l) \\ 
\vdots \\
x_m = u_m(t_1, t_2, ..., t_l),
\end{cases}
$$
> i.e. each of the $x_i$ are a function $u_i$ of $l$ variables $t_1, t_2, ..., t_l$. Then for all $i = 1, 2, ..., l$, we have
$$
\frac{\partial f}{\partial t_i} = \sum_{j=1}^m \frac{\partial f}{\partial x_j}\frac{\partial x_j}{\partial t_i}
$$
(Note that this is a notational simplification because it doesn't display the variables that are being held constant - e.g. if you wanted to be really, really scrupulous you could write $(\frac{\partial f}{\partial x_1})_{x_2,x_3,...,x_m}$ to demonstrate that $x_1$ is the variable differentiated with respect to and the other variables are constant!)

> <span style="background-color: #ffb812; color: black;">Corollary</span>. The above equation can be written in matrix form as
$$
S = TU,
$$
> in which $S$ is the $n \times l$ matrix of partial derivative components of $f$ w.r.t. $t_1, t_2, ..., t_l$:
$$
S = \{(\frac{\partial f}{\partial t_j})_i\} = \begin{bmatrix}
(\frac{\partial f}{\partial t_1})_1 &  (\frac{\partial f}{\partial t_2})_1 & ... & (\frac{\partial f}{\partial t_l})_1 \\
(\frac{\partial f}{\partial t_1})_2 & (\frac{\partial f}{\partial t_2})_2 & ... & (\frac{\partial f}{\partial t_l})_2 \\
\vdots & \vdots & \ddots & \vdots \\
(\frac{\partial f}{\partial t_1})_n & (\frac{\partial f}{\partial t_2})_n & ... & (\frac{\partial f}{\partial t_l})_n
\end{bmatrix}
$$
> $T$ is the $n \times m$ matrix recalled from the previous section as the matrix of the partial derivative components of $f$ w.r.t. $x_1, x_2, ..., x_m$:
$$
T = \{(\frac{\partial f}{\partial x_j})_i\} = \begin{bmatrix}
(\frac{\partial f}{\partial x_1})_1 &  (\frac{\partial f}{\partial x_2})_1 & ... & (\frac{\partial f}{\partial x_m})_1 \\
(\frac{\partial f}{\partial x_1})_2 & (\frac{\partial f}{\partial x_2})_2 & ... & (\frac{\partial f}{\partial x_m})_2 \\
\vdots & \vdots & \ddots & \vdots \\
(\frac{\partial f}{\partial x_1})_n & (\frac{\partial f}{\partial x_2})_n & ... & (\frac{\partial f}{\partial x_m})_n
\end{bmatrix}
$$

> and $U$ is the $m \times l$ matrix of partial derivatives of $x_1, x_2, ..., x_m$ w.r.t. $t_1, t_2, ..., t_l$:

$$
U = \{(\frac{\partial x_i}{\partial t_j})\} = \begin{bmatrix}
\frac{\partial x_1}{\partial t_1} & \frac{\partial x_1}{\partial t_2} & ... & \frac{\partial x_1}{\partial t_l} \\
\frac{\partial x_2}{\partial t_1} & \frac{\partial x_2}{\partial t_2} & ... & \frac{\partial x_2}{\partial t_l} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial x_m}{\partial t_1} & \frac{\partial x_m}{\partial t_2} & ... & \frac{\partial x_m}{\partial t_l}
\end{bmatrix}
$$

Call these matrix the *Jacobian* matrices of $\mathbf{f(x)}$.

> <span style="background-color: #03cafc; color: black;">Example</span> of the chain rule applied to a change of coordinates (Cartesian to polar).

Suppose that $z = f(x,y)$ describes the height of a point $(x,y)$ on your bedsheets this morning after I "befriended" your mom last night. Because your mom emits both the gravitational and magnetic fields characteristic of an Earth-sized planet, we have decided to convert $(x,y)$ to polar coordinates $(x(\rho, \theta), y(\rho,\theta))$ (they are more applicable to problems which revolve around a globe). What is the rate of change of $z$ w.r.t. $\rho$ and $\theta$?

A notational clarification is required here:

> <span style="background-color: #03cafc; color: black;">Notation</span>. If $f(x,y) = f(x(\rho, \theta), y(\rho, \theta))$ (or any such combination of variables), $f$ can be written as a function of $\rho$ and $\theta$. Thus write $f(x,y) = F(\rho, \theta)$.

In this case, we have $(x,y) = (\rho \cos \theta, \rho \sin \theta)$ by polar coordinates. By the chain rule we have
$$
\begin{aligned}
(\frac{\partial f}{\partial \rho})_{\theta} &= (\frac{\partial f}{\partial x})_y(\frac{\partial x}{\partial \rho})_\theta + (\frac{\partial f}{\partial y})_x(\frac{\partial y}{\partial \rho})_\theta \\
&= (\frac{\partial f}{\partial x})_y\cos \theta + (\frac{\partial f}{\partial y})_x\sin \theta \\
\end{aligned}
$$
being careful to note which variables are kept constant, and
$$
\begin{aligned}
(\frac{\partial f}{\partial \theta})_{\rho} &= (\frac{\partial f}{\partial x})_y\frac{\partial x}{\partial \theta} + (\frac{\partial f}{\partial y})_x\frac{\partial y}{\partial \theta} \\
&= -(\frac{\partial f}{\partial x})_y\rho \sin \theta + (\frac{\partial f}{\partial y})_x\rho \cos \theta \\
&= - y (\frac{\partial f}{\partial x})_y + x (\frac{\partial f}{\partial y})_x
\end{aligned}
$$
As $\rho = \sqrt{x^2 + y^2}$ and $\theta = \tan^{-1}(\frac{y}{x})$ are both functions of $x$ and $y$, we can also obtain expressions for $\frac{\partial f}{\partial x}_y$ and $\frac{\partial f}{\partial y}_x$ from the chain rule based on $\rho$ and $\theta$, e.g.
$$
(\frac{\partial f}{\partial x})_y = (\frac{\partial f}{\partial \rho})_{\theta} (\frac{\partial \rho}{\partial x})_y  + (\frac{\partial f}{\partial \theta})_{\rho} (\frac{\partial \theta}{\partial x})_y
$$
noting crucially that $(\frac{\partial \rho}{\partial x})_y$ **keeps $y$ constant, not $\theta$**.

