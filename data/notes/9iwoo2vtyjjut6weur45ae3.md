We begin with an important result that will be used throughout our discussion in this section:
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. "Nonhomogeneous" shall be used instead of "inhomogeneous" (with certain exceptions, e.g. when I forget to).

> <span style="background-color: #1eff12; color: black;">Proof</span>.     I think "nonhomogeneous" sounds cooler. $\square$

Now that that's out of the way, we move on to less important things. 

> <span style="background-color: #03cafc; color: black;">Definition</span>.  Nonhomogeneous second-order DEs are ones of the form 
$$
    L[y](t) = g(t)
$$
> where $L[y](t)$ is as defined above, and $g(t)$ is any function of $t$ that is nonzero. The equation
$$
    L[y](t) = 0
$$
> is thus referred to as the homogeneous equation corresponding to $L[y](t) = g(t)$, and was discussed at length in the previous section. 

To proceed, we formulate several statements that may seem trivial, but are important to our upcoming discussion:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Solutions to inhomogeneous equations. **    (Solutions to inhomogeneous equations). If $Y_1$ and $Y_2$ are both solutions to a certain inhomogeneous DE $L[y](t) = g(t)$, then $Y_1-Y_2$ is a solution to the corresponding homogeneous equation. 

This can be easily proven by substituting $Y_1$ and $Y_2$ into the DE; thus, we have $Y_1 - Y_2 = c_1 y_1 + c_2 y_2$ for fundamental solutions $y_1$ and $y_2$ and constants $c_1, c_2$. As such, it quickly follows that 

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Solutions to inhomogeneous equations. ** The general solution to $L[y](t) = g(t)$ can be fully described by

$$
        y(t) = c_1y_1 + c_2 y_2 + Y(t)
$$

>  where $c_1 y_1 + c_2 y_2$ is the general solution to the homogeneous equation and $Y(t)$ is a specific solution to the inhomogeneous equation.

> <span style="background-color: #1eff12; color: black;">Proof</span>.     As proven by the above theorem, for any two solutions $Y_1$ and $Y_2$ to $L[y](t) = g(t)$, we have $Y_1 - Y_2 = c_1y_1 + c_2y_2$. Thus set $Y_1 = y(t)$ and $Y_2 = Y(t)$ to obtain the desired result.

The implications of the above results inform us on how to approach such inhomogeneous equations:

1. First, we should approach the corresponding homogeneous equation and obtain its solutions.
2. We should then find some specific solution $Y(t)$ to the inhomogeneous equation.
3. The general solution will be the combination of the results of the above two steps.

The second step of finding a specific solution, in particular, is of interest to us in this section. To this end, we present two different approaches:

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Method of undetermined coefficients)**.

..."Method of undetermined coefficients" is a more civilized way to say guessing. The method is guessing. 

The idea behind this method is that the right-hand side $g(t)$ of the inhomogeneous equation can enable us to make educated guesses about what the solution might look like; for example, if it's an exponential function, then it's a bit unlikely that the solution will be a polynomial. We will assume the solution to be in some form (e.g. $e^{ax}$ where $a$ is unknown), set the coefficients of that form to be unknown, and then plug it into the DE to find the coefficients.
  
A table of what solution to guess based on the form of $g(t)$ is shown below:
 
|$g(t)$ | Solution to guess |  
| --- | --- |
| Exponential ($e^{at}$) | $be^{at}$ |
| \sin kt, \cos kt$ | $A \sin kt + B \cos kt$|
| $P_n(t)$ (Polynomial of deg $n$) | Polynomial of the same degree |
| $P_n(t)e^{at}$ | $Q_n(t)e^{at}$ |
| $P_n(t)\sin kt, P_n(t)\cos kt$ | $Q_n(t)\sin kt + R_n(t)\cos kt$ |
<br/>
    

...where $P_n(t), Q_n(t), R_n(t)$ represent polynomials of degree $n$ for some $n$. Essentially, whenever we have an elementary function multiplied by a polynomial for $g(t)$, guess a polynomial of the same degree for the solution. The proof of the above cases is left to the reader. (Yes, I'm making you do my dirty work.)

One thing to note about this method: the degenerate sub-case. (And no, that is not a description of myself.) What happens if the solution we guess turns out to be part of the homogeneous equation's solution? For instance, what if we guess $Ae^{4x}$, but $e^{4x}$ is a fundamental solution to the corresponding homogeneous equation? In this case - like in the repeated root case for constant coefficients before it - we multiply our original guessed solution with $t$, then proceed as normal. If the solution is still degenerate, then $t^2$ will do.

The main limitation of this method is its scope: it does not apply to anything other than linear or multiplicative combinations of elementary functions (trig, exponential, algebraic) - for instance, $\sin e^t$ sould lead to absolute collapse. So what happens if the right-hand side of the inhomogeneous equation is more complicated?

****

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Method of variation of parameters)**. This method presents a general method for solving inhomogeneous second-order DEs, applicable to any equation; in fact, it is powerful enough to derive a general formula for the solution of any such equation. However, it involves considerably greater work and effort than the undetermined coefficients method, and the latter is still preferable when the right-hand side is a fairly simple function. 

We begin by returning to our general inhomogeneous DE:
$$
y'' + p(t)y' + q(t) = g(t)
$$
and its corresponding homogeneous DE:
$$
y'' + p(t)y' + q(t) = 0
$$
At this point, let us assume that the solutions to the homogeneous DE (the *complementary function*) are already known to be encompassed by the fundamental solutions $y_1$ and $y_2$:
$$
y(t) = c_1 y_1 + c_2 y_2
$$
Recall how, in previous sections (repeated roots case in constant coefficients), we managed to obtain one fundamental solution ($y_2 = Ate^{\lambda t}$) off the other fundamental solution ($y_1 = e^{\lambda t}$) by setting $y_2 = v(t) y_1$, leading to a differential equation in $v$.

We will try something similar here. Let the specific solution to the inhomogeneous DE - i.e. the *particular integral* - be $y_p(t)$, and assume that it is in the form

$$
 y_p = v_1 y_1 + v_2 y_2
$$

where $v_1$ and $v_2$ are both functions of $t$. If we try to plug this in to the DE immediately, we obtain a sealed eldritch monstrosity from the ninth circle of hell that should have never been unleashed onto our plane of existence because repeated applications of the product rule leads to more than ten terms. 

More importantly, if we just plug this into the DE with nothing else, we have two variables/functions that need to be solved for ($v_1$ and $v_2$) and only one equation. This would yield an infinite number of solutions; we only need one solution for $y_p(t)$, so let us impose another equation on $v_1$ and $v_2$.

But what is this other equation we should impose? Let's try finding $y_p'$ to get more information, as we want $y_p'$ to be as simple as possible:

$$
y_p' = v_1'y_1 + v_1y_1' + v_2'y_2 + v_2y_2'
$$

Our top priority is to make sure that $v_1$ and $v_2$ do not have second-order derivatives, because they are the variables we want to solve for and a second-order DE is much harder than a first-order one to solve. Thus, we don't want any $v_1'$ or $v_2'$ terms in $y_p'$. For this reason, we propose that our other equation is as follows:

$$
 v_1'y_1 + v_2'y_2 = 0
$$

so that no $v_1'$ or $v_2'$ terms appear in $y_p'$ and thus no second-order derivatives appear in $y_p''$. We continue along this vein:

$$
y_p' = v_1'y_1 + v_1y_1' + v_2'y_2 + v_2y_2' = v_1y_1' + v_2y_2'
$$

from our other equation, and thus 

$$
 y_p'' = v_1'y_1' + v_1y_1'' + v_2'y_2' + v_2y_2''
$$

This gives us enough information to plug in back to the original DE:

$$
\begin{aligned}
    y_p'' + p(t)y_p' + q(t)y_p &= g(t) \\
    v_1'y_1' + v_1y_1'' + v_2'y_2' + v_2y_2'' + p(t)(v_1y_1' + v_2y_2') + q(t)(v_1y_1 + v_2y_2) &= g(t) \\
    v_1(y_1'' + p(t)y_1' + q(t)y_1) + v_2(y_2''+p(t)y_2' + q(t)y_2) + v_1'y_1' + v_2'y_2' &= g(t)
\end{aligned}
$$

where everything in the parentheses in the final equation is zero due to $y_1$ and $y_2$ being solutions to the homogeneous equation. As such, we finally obtain

$$
 v_1'y_1' + v_2'y_2' = g(t)
$$

as well as our other equation

$$
v_1'y_1 + v_2'y_2 = 0
$$

 which gives us a system of equations in $v_1'$ and $v_2'$:

$$
\begin{cases}
    v_1'y_1' + v_2'y_2' = g(t) \\
    v_1'y_1 + v_2'y_2 = 0
\end{cases}
$$

This gives us enough information to find the general solution.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **(General solution for inhomogeneous second-order differential equations).** The particular integral $y_p(t)$ for any inhomogeneous second-order DE, with its corresponding homogeneous equation having fundamental solutions $y_1$ and $y_2$, is given by:

$$
\begin{cases}
    y_p(t) = v_1y_1 + v_2y_2 \\
    v_1 = -\int \frac{g(t)y_2}{W(y_1,y_2)(t)} \ dt \\
    v_2 = \int \frac{g(t)y_1}{W(y_1,y_2)(t)}
\end{cases}
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Proceed from the system of equations above: multiplying the second equation by $\frac{y_1'}{y_1}$ obtains
$$
v_1'y_1' + v_2'\frac{y_1'y_2}{y_1} = 0
$$
and subtracting from the first obtains
$$
v_2'(\frac{y_1y_2' - y_1'y_2}{y_1}) = g(t)
$$
which very conveniently contains a Wronskian:
$$
W(y_1,y_2) = y_1y_2' - y_1'y_2
$$
and hence
$$
v_2' = \frac{g(t)y_1}{W(y_1,y_2)(t)}
$$
Substituting into the second equation gives
$$
\begin{aligned}
    v_1'y_1 &= -v_2'y_2 \\
    v_1' &= -\frac{g(t)y_1}{W(y_1,y_2)(t)}\frac{y_2}{y_1} \\
    &= -\frac{g(t)y_2}{W(y_1,y_2)(t)}.
\end{aligned}
$$
which is our desired result.
