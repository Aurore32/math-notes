---
id: lunebnp6hfbd51z9lnzvnfc
title: Inital-Condition Problems
desc: ''
updated: 1737883937830
created: 1737883042002
nav_order: 2
---
In this section, we will define a new operator $L[\phi]$ for some function $\phi(t)$ twice differentiable on a given interval (becaus math just doesn't have enough Greek letters in it, apparently):

> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Differential operator).** We define $L[\phi] = \phi'' + p\phi' + q\phi$, which is a function of $t$; $p$ and $q$ can either be constants or functions of $t$ also, and $L[\phi](t) = \phi''(t) + p(t)\phi'(t) + q(t)\phi(t)$. This will simplify our notations for second-order differential equations greatly (and prevent me from having to amputate my fingers from excess typing before I turn 21).

The motivation for this section comes from initial-condition problems arising from real-world scenarios; problems where, through a set of initial conditions (e.g. $t=0, y=...$), we are able to uniquely determine one solution to a DE. Consider, for instance, the general second-order homogeneous ODE $L[y](t) = 0$:

$$
L[y] = y'' + p(t)y' + q(t)y = 0

$$

We can associate this equation with the initial condition $y(t_0) = y_0$: the value of the quantity $y$ at a certain time. However, this isn't enough to uniquely determine a solution; as this DE is second-order, two variables exist in its possible solutions. Thus we will need another initial condition - the value of $y'$ at a certain time: $y'(t_0) = y_0'$.

These types of problems are extremely commonplace in real-world modeling, and we would like to know:

1. Whether we can find a solution to such initial-condition problems,
2. Whether the solution is unique, and
3. Whether the solutions have a particular form.

It turns out that we can answer all these questions in one fell swoop.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>.    ** (Existence and uniqueness theorem).** The initial-value problem $L[y](t) = 0$ with $y(t_0)=y_0, y'(t_0)=y'_0$ on some interval $I (a<t<b, t_0\in I)$ has exactly one solution. In other words, this solution exists, it is unique, and it exists throughout $I$ where it is twice differentiable.

Note that this interval $I$ is the interval in which $p(t)$ and $q(t)$ - the coefficients to $L[y](t)=0$ - are continuous, and $y(t)$ is also twice-differentiable and continuous.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Trivial. (Behold but a fraction of my incredible power.)

At this point, it will be useful for us to formally state a result we have relied on in the past:

> <span style="background-color: #12ffd7; color: black;">Principle</span>. **(Principle of superposition)**. If $y_1$ and $y_2$ are solutions to $L[y] = 0$, then the linear combination $c_1 y_1 + c_2 y_2$ is also a solution to $L[y] = 0$. This can be easily proven by the linearity of differentiation.

By this principle, we understand that with two independent solutions $y_1$ and $y_2$, we are able to construct an infinite family of solutions to a second-order ODE. The question arises, however, of whether other solutions that lie outside of the family also exist. 

To determine this, we make good use of Theorem 3.4 (Existence and Uniqueness Theorem for initial-value problems). In a certain interval $I$, let $L[y] =0$ have initial conditions $y(t_0) = y_0, y'(t_0) = y_0'$; if $y$ can be written as $y=c_1 y_1 + c_2 y_2$, then

$$
\begin{cases}
        c_1y_1(t_0) + c_2y_2(t_0) = y_0 \\
        c_1y_1'(t_0) + c_2y_2'(t_0) = y_0'
    \end{cases}
$$

We can treat $y_1(t_0), y_1'(t_0)$ and such as constants to obtain a simple linear system of equations in $c_1$ and $c_2$; we can also rewrite this system in matrix form as

$$
\begin{bmatrix}
        y_1(t_0) & y_2(t_0) \\
        y_1'(t_0) & y_2'(t_0) 
    \end{bmatrix}
    \begin{bmatrix}
        c_1 \\
        c_2
    \end{bmatrix}
    =
    \begin{bmatrix}
        y_0 \\
        y_0'
    \end{bmatrix}
$$

We know that this system has a unique solution if the determinant to the first matrix of coefficients is nonzero:

$$
 W = \begin{vmatrix}
        y_1(t_0) & y_2(t_0) \\
        y_1'(t_0) & y_2'(t_0)
    \end{vmatrix}
$$

This determinant is known as the **Wronskian**.

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **Wronskian** of solutions $y_1, y_2$ to $L[y](t) = 0$ is the matrix determinant
$$
 W = \begin{vmatrix}
            y_1 & y_2 \\
            y_1' & y_2'
        \end{vmatrix}.
$$
The equations above establish the following result:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>.** (Wronskian and Initial Value).** Let $y_1, y_2$ be two solutions to $L[y](t)=0$ with assigned initial values $y(t_0)=y_0, y'(t_0)=y_0'$. Then the unique solution to this initial-value problem can be found by choosing constants $c_1$, $c_2$ for $y=c_1 y_1 + c_2 y_2$ if and only if the Wronskian at that initial value $t_0$ is nonzero: 

$$
W(y_1,y_2)(t_0) \neq 0.
$$

As such, from the above theorem and the Existence and Uniqueness Theorem, we derive our conclusion:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Wronskian and Family of Solutions).** Let $y_1, y_2$ be two solutions to $L[y](t)=0$ over an interval $I$. Then the family of solutions

$$
y = c_1y_1 + c_2y_2
$$

> for constants $c_1, c_2$ encompasses every solution to $L[y](t) = 0$ if and only if there is a point $t_0$ in $I$ where the Wronskian is nonzero.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Let $\phi$ be any solution to $L[y](t)=0$. To prove the theorem, we must show that $\phi$ will necessarily be in the form $c_1 y_1 + c_2 y_2$.

Let $t_0$ be a point where $W(y_1,y_2)$ is nonzero. We write $y_0 = \phi(t_0)$ and $y_0' = \phi'(t_0)$; naturally, $phi(t)$ is a solution to the initial-value problem

$$
L[y](t) = 0, y(t_0) = y_0, y'(t_0) = y_0'
$$

By the above theorems, as the Wronskian is nonzero at the initial point $t = t_0$, the system of equations that determines $c_1$ and $c_2$ has one unique solution; by the Existence and Uniqueness theorem, this solution is the only solution to this initial-value problem, so $\phi$ must equal $c_1 y_1 + c_2 y_2$. The same process can be applied to any $\phi$, and thus $c_1 y_1 + c_2 y_2$ encompasses every solution of the DE.

Conversely, assume that the Wronskian is always zero. Therefore, by the above theorems, it is not always possible to find constants $c_1$ and $c_2$ such that $c_1y_1 + c_2y_2$ is a solution to some initial-value problem. However, by the Existence and Uniqueness Theorem, such a solution must exist; thus, we conclude that $L[y](t) = 0$ has solutions outside the family $c_1y_1 + c_2y_2$. 

****

These theorems formally guarantee that if two fundamental (independent) solutions to a second-order DE can be found, then the general solution can be found. However, is it always possible to find such fundamental solutions? The answer is indeed yes.


> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Fundamental solutions).** Consider the equation $L[y](t)=0$. Choose some point $t_0$ in an interval $I$ where the coefficients of the equation are continuous. Let $y_1$ be the solution to the equation that satisfies the initial conditions

$$
y(t_0) = 1, y'(t_0) =0
$$

> and $y_2$ be the solution that satisfies

$$
y(t_0) = 0, y'(t_0) =1.
$$

> Then $y_1$ and $y_2$ form fundamental solutions to $L[y](t) = 0$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

By the Uniqueness and Existence theorem, $y_1$ and $y_2$ exist and are unique. The Wronskian $W(y_1, y_2)(t_0)$ equals
$$
        \begin{vmatrix}
            y_1(t_0) & y_2(t_0) \\
            y_1'(t_0) & y_2'(t_0)
        \end{vmatrix}
        = 
        \begin{vmatrix}
            1 & 0 \\
            0 & 1
        \end{vmatrix}
        =1
$$
and is thus nonzero. As such, $y_1$ and $y_2$ form a fundamental set of solutions. 

****

This theorem informs us that any second-order DE has two fundamental solutions; however, it's a bit too shy to tell us exactly how to find these solutions. Oh dear. So what can we do when we don't know these solutions? Are there any commonalities that are shared between the fundamental solutions of the same equation?

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(Abel's Theorem).** If $y_1$ and $y_2$ are any two solutions to a second-order differential equation $L[y](t) = y''+p(t)y'+q(t) = 0$ where its coefficients are continuous on an interval $I$, then the Wronskian $W(y_1,y_2)(t)$ is given directly by 
$$
        W(y_1,y_2)(t) = ce^{-\int p(t)\ dt}
$$
> where $c$ is a constant that only depends on what the choice of $y_1$ and $y_2$ is, not on $t$ (i.e. it is not a function of $t$). This implies that - as exponential functions are never zero - the Wronskian for $L[y](t)$ is either always zero ($c=0$) or never zero ($c \neq 0$).

> <span style="background-color: #1eff12; color: black;">Proof</span>.

We note that $y_1$ and $y_2$ satisfy    
$$
\begin{cases}
            y_1'' + p(t)y_1' + q(t) = 0 \\
            y_2'' + p(t)y_2' + q(t) = 0
\end{cases}
$$
o cancel out $q(t)$, we multiply the first equation by $-y_2$ and the second equation by $y_1$, then add them together to obtain
$$
y_2''y_1 - y_1''y_2 + p(t)(y_1y_2' - y_1'y_2) = 0
$$
Now we turn to $W(y_1, y_2)(t) = y_1 y_2' - y_1' y_2$. Note that 
$$
\begin{aligned}
            W' &= y_1'y_2' + y_1y_2'' - y_1''y_2 - y_1'y_2' \\
            &= y_1y_2'' - y_1''y_2.
\end{aligned}
$$
This means that we can rewrite the above equation as
$$
W' + p(t)W = 0
$$
which is a first-order $DE$ that can be solved with integrating factor $e^{\int p(t)\ dt}$, yielding Abel's theorem.

The implications of Abel's theorem are:
1. That all possible Wronskians of a second-order DE differ only by a multiplicative constant, no matter what fundamental solutions are picked.
2. That the Wronskian can be determined without actually solving the equation.
3. That the Wronskian is either always zero or never zero.



