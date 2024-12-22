---
id: bof4d8unu2g8shqxa7vhs4p
title: Geometric Equations
desc: ''
updated: 1734665480372
created: 1734665325248
---
## Complex equation of a line
This equation is not called "complex equation of a line" because it involves complex numbers, but because it is unnecessarily complex. Observe. 

What can we do if we want to find a line that goes through the point $x_0$ on the Argand diagram and is parallel to some complex number $\omega$? By what we know of vector equations for lines, we can write the line as $x = x_0 + \lambda \omega$ for some real scalar $\lambda$. If we rewrite this as $\frac{x-x_0}{\omega}=\lambda$ and take the conjugate of both sides, we obtain
$$
    \frac{\bar{x}-\bar{x_0}}{\bar{\omega}}=\bar{\lambda}=\lambda
$$
as $\lambda$ is real. Thus the conjugate of this expression is equal to itself:
$$
    \frac{\bar{x}-\bar{x_0}}{\bar{\omega}}=\frac{x-x_0}{\omega}
$$
which gives us the equation of a line parallel to $\omega$ and passing through $x_0$. 

## Complex equation of a circle
A circle with center $x_0$ and radius $r$, in abstract terms, is simply a locus of points a distance $r$ away from the center $x_0$. (In less abstract terms, it can be referred to as "an inferior donut" or "a superior oval".) This can be formulated as 
$$
    |x-x_0|=r
$$
or, squaring both sides,
$$
 \begin{aligned}
        |x-x_0|^2&=r^2 \\
        (x-x_0)(\bar{x}-\bar{x_0})&=r^2
    \end{aligned}
$$
