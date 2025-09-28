This section concerns equations of the form
$$
ay_{n+2}+by_{n+1}+cy_{n} = f_n,
$$
also known as recurrence relations of order 2. The method we can use for solving these is extremely similar to the one we used for constant-coefficient DEs: eigenfunctions.

> <span style="background-color: #bc42f5; color: black;">Method</span>. **(Eigenfunctions for difference equations). **

Suppose that some operator $D[y_n] = y_n$ relates $y_n$ to $y_{n+1}$. As such, the above equation can be rewritten as:
$$
aD^2[y_n] + bD[y_n] + cy_n = f_n
$$
The eigenfunction of this operator is $y_n = \lambda^n$ for some constant $\lambda$. This is because, by definition, $y_{n+1} = \lambda^{n+1}$ (simply by substituting $n$ with $n+1$), and thus 
$$
 D[y_n] = y_{n+1} = \lambda^{n+1} = \lambda y_n
$$
which is a constant multiple of $y_n$.

Using the exact same approach as we applied to differential equations, we solve the corresponding homogeneous difference equation $aD^2[y_n] + bD[y_n] + cy_n = 0$ first by substituting in the eigenfunction $y_n = \lambda^n$:

$$
a\lambda^{n+2} + b\lambda^{n+1} + c\lambda^n = 0 \iff a\lambda^2 + b\lambda + c = 0
$$

yielding a characteristic equation of degree 2. Similarly to differential equations, if the two roots are equal, then we have $y_n = (An+B)\lambda^n$ for constants $A$, $B$. All that's left is to substitute in initial values of $y_n$ to find the constants, and we're done! 

To deal with the pesky inhomogeneous term on the right-hand side, we once again resort to our tried-and-true, sophisticated, and wondrously erudite method of guessing. 

If the right-hand side is an exponential function $k^n$ ($k \neq \lambda$), we guess $k^n$ or some multiple of this. (Be aware that $k$ is a constant!)

Finally, if the right-hand side is a polynomial, we guess a polynomial of the same degree ($y_n = n^p + ..., y_{n+1} = (n+1)^p + ...$)



