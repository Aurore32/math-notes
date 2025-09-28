Recall that an inhomogeneous equation is one that does not have $y=0$ as a solution; e.g. $5y' - 3y = 10$ is inhomogeneous, having an added term 10 on the right-hand side compared to the homogeneous equation. These added terms are "forcing" terms.

> <span style="background-color: #bc42f5; color: black;">Method</span>. The **particular integral** solution. This method applies to inhomogeneous equations where one side is completely homogeneous with constant coefficients (all terms contain $y$ or a derivative of $y$) and the other side is a function of $x$. For instance, $2y' + 3y = 3x^2 + x$ is applicable.

The method for solving this type of equation is to first solve the equation as though it was homogeneous (turn the right-hand side to 0), which yields the *complementary function*, then guessing one particular solution to the equation, known as a *particular integral*.
 The general solution is the sum of both. 

 Take the following radioactive decay model as an example:

> <span style="background-color: #03cafc; color: black;">Example</span>. A radioactive isotope $A$ decays at a rate proportional to the remaining amount of nuclei in its sample, $a$, into isotope $B$, which further decays at a rate proportional to the remaining amount of nuclei in its sample, $b$. <br/><br/>
Given that the constants of proportionality are $k_a$ and $k_b$ respectively, and that the initial number of nuclei present in each sample are $a_0$ and 0 respectively, determine an expression for the remaining nuclei in sample $B$, $b(t)$.

We have
$$
    \begin{aligned}
        \frac{da}{dt} &= -k_a a \\
        \frac{db}{dt} &= k_a a - k_b b
    \end{aligned}
$$
Solving the first equation yields $a = \lambda e^{-k_a t}$ for some constant $\lambda$, with the initial condition that when $t=0$, $a=a_0$; thus, $a=a_0 e^{-k_a t}$. Substituting into the second equation yields $\frac{db}{dt} = a_0 e^{-k_a t} - k_b b$, or $b' + k_b b = a_0 e^{-k_a t}$. 

The homogeneous equation has solution $\lambda e^{-k_b t}$ for any constant $\lambda$. Try $b = \alpha e^{-k_a t}, b' = -k_a \alpha e^{-k_a t}$ for the particular integral; 
plugging this into the equation gives $-k_a \alpha e^{-k_a t} + k_b \alpha e^{-k_a t} = a_0 e^{-k_a t}$, and dividing both sides by $e^{-k_a t}$ gives $(k_b - k_a)\alpha = a_0, \alpha = \frac{a_0}{k_b - k_a}$.

We also need $b(0) = 0$, so if $b = \frac{a_0}{k_b - k_a}e^{-k_a t} + \lambda e^{-k_b t}$, $\frac{a_0}{k_b - k_a} + \lambda = 0$, so $\lambda = -\frac{a_0}{k_b - k_a}$. Thus $b = \frac{a_0}{k_b - k_a}(e^{-k_a t} - e^{-k_b t}).$ 


