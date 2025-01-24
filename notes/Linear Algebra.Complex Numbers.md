---
id: dsj2qe8miwbf9b8bx301eo9
title: Complex Numbers
desc: ''
updated: 1734662945615
created: 1734661935146
nav_order: 1
---

## Introduction, in brief
Let's start with a return to form: complex numbers. In the realm of linear algebra specifically, complex numbers are important for two reasons. First, in the set of complex numbers $\mathbb{C}$, we can guarantee that a polynomial of degree $n$ will have $n$ roots by the Fundamental Theorem of Algebra; never again will we have to worry about equations like $\lambda^2 + 1 =0$ making us more confused than tasting a burger from Pizza Hut and finding it delicious. This becomes particularly relevant when we have to deal with these polynomials, which arise when we find the eigenvalues of a particular matrix - more on that later. 


> Definition (Complex number). 

We define the imaginary unit $i$ as satisfying $i^2 = -1$; as such, we also define the set of complex numbers $\mathbb{C}$ to encompass all numbers of the form $$z=a+bi$$    where $a$ and $b$ are real. We write $a = \text{Re}(z)$, $b=\text{Im}(z)$, and the complex conjugate $\bar{z}=a-bi$ (a theorem in algebra will demonstrate that if $z$ is a root of a polynomial, then $\bar{z}$ is too).

But second of all - and much more thematically - while real numbers are *one-dimensional*, all lying upon the same infinitely long number line, complex numbers are two-dimensional; it is useful to think of $z=a+bi$ as a vector in the *complex plane*, $\begin{bmatrix}
    a\\b
\end{bmatrix}$. 

The representation of complex numbers as vectors is done on an *Argand plane*, analogous to the Cartesian plane but with the x-axis representing the real part of $z$ and the y-axis representing the imaginary part.

What follows is a carousel of important results for complex numbers which are truly astounding in their mind-numbingness, not because of what they are but because we've seen them all before. More on this below.
