---
id: x5ttibwtz9kw9kjjo9z2jxc
title: Integrating Factors
desc: ''
updated: 1737879178190
created: 1737879095852
nav_order: 3
---
## Non-constant coefficient DEs

This section will deal with first-order differential equations of the following form:

$$
    a(x)y' + b(x)y = c(x)
$$

in which the coefficients of $y$ and $y'$ are non-constant. In particular, the method of integrating factors will be introduced.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **Integrating factors**. 

Divide the given equation by $a(x)$ to obtain the form
$$
    y' + \frac{b(x)}{a(x)}y = \frac{c(x)}{a(x)}
$$
or, equivalently, 
$$
    y' + p(x)y = f(x)
$$
We want the left-hand side to be expressible in the form of the derivative of a function $g'(x) = y' + p(x)y$; thus consider multiplying throughout by an *integrating factor* $\mu$, such that $\mu y' + \mu y p(x)$ is $(\mu y)' = \mu y' + \mu' y$. 

This necessitates that $\mu' = \mu p(x)$, or $\int \frac{\mu'}{\mu} \ dx = \int p(x)\ dx, \ln \mu = \int p(x)\ dx, \mu = e^{\int p(x)\ dx}$. 


