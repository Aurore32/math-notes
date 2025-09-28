> cf. Better Call Saul, s06e11, "Breaking Bad"

As it turns out, we can derive close to everything we covered in the Differential Equations course with Linear Algebra - in particular, the solution to second-order ordinary differential equations. For a differential equation of the form
$$
\frac{d^2 x}{dt^2} + b\frac{dx}{dt} + cx = 0,
$$
or
$$
\ddot{x} + b\dot{x} + cx = 0,
$$
the change of variable $y = \dot{x}$ (a technique we used in Differential Equations!) yields the linear system of equations in $\dot{x}$ and $\dot{y}$
$$
\begin{cases}
\dot{x} = y \\
\dot{y} = -cx - by
\end{cases}
$$
or, in matrix form,
$$
\begin{bmatrix}
0 & 1 \\
-c & -b
\end{bmatrix}
\begin{bmatrix}
x \\ y
\end{bmatrix}
=
\begin{bmatrix}
\dot{x} \\ \dot{y}
\end{bmatrix}
$$
This is a special case of the general system of differential equations
$$
A\mathbf{x} = \dot{\mathbf{x}},
$$
or
$$
\begin{bmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22}
\end{bmatrix}
\begin{bmatrix}
x \\ y
\end{bmatrix}
=
\begin{bmatrix}
\dot{x} \\ \dot{y}
\end{bmatrix}
$$

As shown, $A$ can be transformed into one of three canonical forms through a change of basis with some matrix $P$:
$$
\begin{aligned}
P^{-1}A\mathbf{x} = P^{-1}\mathbf{\dot{x}} \\
P^{-1}AP(P^{-1}\mathbf{x}) = P^{-1}\mathbf{\dot{x}} \\
P^{-1}AP\mathbf{z} = \dot{\mathbf{z}}
\end{aligned}
$$
where $\mathbf{z} = P^{-1}\mathbf{x}$, and $P^{-1}AP$ is one of three canonical forms:
1. $P^{-1}AP = \begin{bmatrix} \lambda_1 & 0\\ 0 & \lambda_2 \end{bmatrix}$. As such, the system of equations is separated:
$$
\begin{cases}
\lambda_1 z_1 = \dot{z_1} \\
\lambda_2 z_2 = \dot{z_2}
\end{cases}
$$
leading to $z_1 = A_1e^{\lambda_1 t}, z_2 = A_2 e^{\lambda_2 t}$ where $A_1$ and $A_2$ are constants. 

2. $P^{-1}AP = \begin{bmatrix} \lambda & 0\\ 0 & \lambda \end{bmatrix}$. The solution is simply $z_1 = A_1 e^{\lambda t}, z_2 = A_2 e^{\lambda t}$.

3. $P^{-1} AP = \begin{bmatrix} \lambda & 1\\ 0 & \lambda \end{bmatrix}$. We thus have
$$
\begin{cases}
\lambda_1 z_1 + z_2 = \dot{z_1} \\
\lambda_2 z_2 = \dot{z_2}
\end{cases}
$$
yielding $z_2 = A_2 e^{\lambda_2 t}$, and substituting into the first equation gives $z_1 = A_1e^{\lambda_1 t} + A_2te^{\lambda_2 t}$.

To obtain solutions for $\mathbf{x}$ from $\mathbf{z}$, simply multiply 
 by $P$.