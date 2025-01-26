---
id: hduqs5fphra3kiley5psg9p
title: Solution Curves
desc: ''
updated: 1737880172234
created: 1737879773032
nav_order: 5
---
How can we understand the nature of the family of solutions to a differential equation (when the constant term in the solution varies) without actually solving it? The following methods will introduce several key points to plotting such solution curves:
1. Spotting constant solutions (e.g. $y = \pm 1$)
2. Analyzing the sign of $\frac{dy}{dx}$ for $x=0, x>0$ and $x<0$
3. **Determining stability**. (See below)
4. Finding ***isoclines*: **curves along which $\frac{dy}{dx}$ is constant.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Isoclines)**. For a differential equation $\frac{dy}{dx} = ...$, an *isocline* is a curve on which $\frac{dy}{dx}$ is constant, e.g. $\frac{dy}{dx} = 1$; they can be found simply by setting $\frac{dy}{dx}$ to that value. (For instance, if $\frac{dy}{dx}=x^2+3, x^2+3=1 \iff x^2 = -2$ is the curve on which $\frac{dy}{dx}=1$.)

Isoclines are useful in plotting solution curves because they can be plotted with a slope field, i.e. at every point on the isocline, its slope can be drawn as an arrow. The solution curves to the DE must have a shape that follow these arrows.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Equilibrium points and stability).**

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Equilibrium point).** An **equilibrium point** or **fixed point** of a DE is a constant solution $y=c$, which corresponds to $\frac{dy}{dt} = 0$.

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Stability of an equilibrium point)**. An equilibrium is **stable** if, whenever a solution to the DE $y = c+\epsilon(t)$ for an arbitrarily small $\epsilon(t)$, $y$ eventually converges to $c$ as $x \to \infty$. Similarly, an equilibrium is **unstable** if it diverges as $x \to \infty$. 

In graphical terms, if the solutions to the DE converge to a constant which is also a solution, it is a stable equilibrium/fixed point.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Perturbation theorem)**. For a fixed point of a DE $y=a$ and an arbitrarily small $\epsilon(t) << 1$, the change of the perturbation of the solution function $y=a+\epsilon(t)$ about $y=a$ can be approximated by 
$$
        \frac{d\epsilon}{dt} \approxeq \epsilon \frac{\partial f}{\partial y}(a, t)
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Suppose $y=a$ is a fixed point of $\frac{dy}{dt} = f(y,t)$, with $\frac{dy}{dt} = 0$ and thus $f(a,t) = 0$. Consider $y = a + \epsilon (t)$ for an arbitrarily small function of $t$, $\epsilon(t)$. Plugging this into the DE obtains
$$
\begin{aligned}
        \frac{d}{dt} y &= \frac{d}{dt} (a + \epsilon(t)) \\
        &= \frac{d\epsilon}{dt} \\
        &= f(a+\epsilon(t), t) \\
        &= f(a,t) + \epsilon(t)\frac{\partial f}{\partial y}(a,t) + O(\epsilon^2)
    \end{aligned}
$$
due to Taylor's theorem generalized to multivariate functions. If $\epsilon$ is arbitrarily small, terms on the order of $O(\epsilon^2)$ can be ignored, and so $\frac{d\epsilon}{dt} \approxeq \epsilon \frac{\partial f}{\partial y}$.

Consider the following example to demonstrate the method of perturbation analysis:


> <span style="background-color: #03cafc; color: black;">Example</span>. Find the equilibrium points of $\frac{dy}{dt} =y(y-1)(y-2)$ and analyze their stability.

> <span style="background-color: #1eff12; color: black;">Solution</span>.

We begin by setting $\frac{dy}{dt} = 0$ to find all the equilibrium points; then $y(y-1)(y-2)=0$, so $y = 0, 1, 2$ are the equilibrium points of this DE. 

Now consider the perturbation function $\epsilon(t)$. First note that $f(t,y) = y(y-1)(y-2)$ in this case, so $\frac{\partial f}{\partial y} = (y-1)(y-2) + y(y-2) + y(y-1) = 3y^2 - 6y + 2.$ For $y = 0$ we have
$$
\begin{aligned}
        \frac{d\epsilon}{dt} &\approx \epsilon \frac{\partial f}{\partial y}(0) = 2\epsilon \\
        \int \frac{d\epsilon}{\epsilon} &= \int 2\ dt \\
        \ln \epsilon &= 2t + C \\
        \epsilon &= \epsilon_0 e^{2t}
\end{aligned}
$$
which is unstable as it tends to infinity as $t$ grows; for $y = 1$ we have
$$
    \begin{aligned}
        \frac{d\epsilon}{dt} &\approx \epsilon \frac{\partial f}{\partial y}(1) = -\epsilon \\
        \epsilon &= \epsilon_0 e^{-t} \\ \\
    \end{aligned}
$$
which is stable as $e^{-t}$ tends to 0 as $t$ grows. Finally, for $y=2$ we have
$$
    \begin{aligned}
        \frac{d\epsilon}{dt} &\approx \epsilon \frac{\partial f}{\partial y} = 2\epsilon \\
        \epsilon &= \epsilon_0 e^{2t}
    \end{aligned}
$$
which is the same case as $y=0$ (unstable equilibrium).
