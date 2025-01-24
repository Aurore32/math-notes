---
id: b6pvgfgsebio60eelk93piq
title: Complex Exponentiation
desc: ''
updated: 1734665198826
created: 1734664048060
nav_order: 2
---
To extend exponentiation to complex numbers, we use the Taylor series definition of exponentiation:

> <span style="background-color: #03cafc; color: black;">Definition</span> (Exponential function). Define $e^z=\sum_{n=0}^{\infty}\frac{x^z}{z!}$, which can be verified to satisfy the known properties of exponentiation, such as $e^{a}e^{b}=e^{a+b}$. We assume that this sum converges for all complex numbers $z \in \mathbb{C}$.

Similarly, we would like to extend the trigonometric functions to the complex realm, where a geometric definition fails due to the budding, unhinged insanity that underlines the words "an angle of $39+46\pi i$ degrees":

> <span style="background-color: #03cafc; color: black;">Definition</span> (Complex sine and cosine). Define 
$$
\sin z = \sum_{n=0}^{\infty} (-1)^{n}\frac{x^{2n+1}}{(2n+1)!} = x-\frac{x^3}{3!}+\frac{x^5}{5!}+...
$$
> and
$$
\cos z = \sum_{n=0}^{\infty} (-1)^{n}\frac{x^{2n}}{(2n)!} = 1-\frac{x^2}{2!}+\frac{x^4}{4!}-...
$$

From the two above results, we obtain a very important formula throughout all of math.

> <span style="background-color: #12ffd7; color: black;">Theorem</span> (Euler's formula).         
$$
e^{iz}=\cos z + i\sin z
$$
> It almost feels like I should be wearing a suit and tie before doing this. We also note that any complex number can thus be written in terms of a complex exponential, as its modulus-argument form $(r,\theta)$ suggests it can be written as 
$$
        z=r(\cos \theta + i\sin \theta)=re^{i\theta}
$$
> which allows us to state that multiplication between two complex numbers $z_1=r_1e^{i\theta_1}$ and $z_2=r_2e^{i\theta_2}$ requires the multiplication of their moduli and addition of their arguments.

---

# Complex Logarithms

> <span style="background-color: #03cafc; color: black;">Definition</span> (Complex logarithm). Define the complex logarithm $\omega = \ln z$ as the number which satisfies $e^\omega = z$.<br/><br/> If $z$ is a complex number $z=re^{i\theta}$, then we have $e^{\omega} = re^{i\theta}$ and thus $\ln \frac{1}{r} = i\theta - \omega$ and $\omega = \ln re^{i\theta} = i\theta +\ln r$. (also, $\ln ab = \ln a + \ln b$ gets us here.)

> <span style="background-color: #03cafc; color: black;">Definition</span> (Complex powers). Define $z^\alpha$ for complex $z$ as $e^{\alpha\ln z}$, where we insist that the argument used for $z$ is $-\pi < \theta < \pi$, the principal argument.

This gives rise to

> <span style="background-color: #12ffd7; color: black;">Theorem</span> (De Moivre's Theorem). 
$$
        \cos n\theta + i\sin n\theta =(\cos \theta + i\sin n\theta)^n.
$$
This can be proven by induction; it is functionally identical to stating that $e^{ni\theta}=(e^{i\theta})^n$, which is obvious over the reals but not so obvious over complex numbers.
