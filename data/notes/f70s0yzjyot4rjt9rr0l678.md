## Transforming higher-order DEs into systems

Consider the generalized higher-order (constant-coefficient) differential equation:

$$
y^{(n)}(x)+a_{n-1}y^{(n-1)} + \dots + a_2 y''(x) + a_1y'(x)+a_0 y = g(x)
$$

Is there any way for us to simplify this into something easier to calculate? It turns out we need only to use a system of equations, with a set of $n$ new variables:

$$
\begin{cases}
        y_1 = y \\
        y_2 = y_1'\ (=y') \\
        y_3 = y_2'\ (=y'')\\
        \dots \\
        y_n = y_{n-1}' (=y^{(n-1)}) \\        
    \end{cases}
$$

and thus we have, from the generalized equation above, 

$$
\begin{aligned}
        y_n' &= -a_{n-1}y^{(n-1)} - \dots - a_2 y''(x) - a_1y'(x)-a_0y \\
        &=-a_{n-1}y_n - \dots - a_2y_3 - a_1y_2 - a_0y_1
    \end{aligned}
$$

with each equation being a first-order differential equation (no derivatives above the first derivative of each $y_k$). In essence, we have transformed an $n$th-order DE into a system of $n$ first-order DEs. 

Calling this a simplification of the original equation might seem the same as saying that topologically speaking, a coffee mug is equivalent to a donut, but observe the spark of genius lurking beneath the mundane waters of these blessed equations. As it turns out, it is extremely easy to rewrite these equations in matrix form: 

$$
\frac{d}{dx}\begin{bmatrix}
        y_1\\
        y_2\\
        y_3\\
        \vdots\\
        y_n
    \end{bmatrix}=
    \begin{bmatrix}
        0 & 1 & 0 & \dots & 0 \\
        0 & 0 & 1 & \dots & 0 \\
        \vdots & \vdots & \ddots & \vdots & \vdots \\
        0 & 0 & 0 & \dots & 1 \\
        -a_0 & -a_1 & -a_2 & \dots & -a_{n-1}
    \end{bmatrix}
    \begin{bmatrix}
        y_1\\
        y_2\\
        y_3\\
        \vdots\\
        y_n
    \end{bmatrix} + 
    \begin{bmatrix}
        0\\
        0\\
        0\\
        \vdots\\
        g(x)
    \end{bmatrix}
$$

Or, alternatively, writing the matrix on the left-hand side as $\mathbf{x}$, the first matrix on the right-hand side as $\mathbf{A}$, and the second matrix as $\mathbf{F}$, we have (simply!):

$$
\dot{\mathbf{x}} = \mathbf{A}\mathbf{x} + \mathbf{F}
$$

This is what would happen if linear algebra and differential equations went to a party together (only hypothetically speaking, since mathematicians aren't invited to parties), got aggressively drunk, found themselves tangled within each other's luscious locks, and birthed a love-child through mitosis; it's where the two converge, and it's where we can study both together. The rest of this section will be entirely focused on the study of systems of this form.

## Eigenvalue solutions to linear systems of DEs

How do we begin to solve systems of the form 

$$
\dot{\mathbf{x}} = \mathbf{A}\mathbf{x} + \mathbf{F}?
$$
To gain a foothold on these, let's consider the most simple case of all: a case where we simply have 
$$
\mathbf{F} = 0
$$
yielding a homogeneous equation, and 
$$
\mathbf{A}=\begin{bmatrix}
        a_1 & 0 & \dots & 0 & 0 \\
        0 & a_2 & \dots & 0 & 0 \\
        \vdots & \vdots & \ddots & \vdots & \vdots \\
        0 & 0 & \dots & a_{n-1} & 0 \\
        0 & 0 & \dots & 0 & a_n
    \end{bmatrix}
$$
resulting in the system of equations 
$$
 \begin{cases}
        y_1' = a_1 y_1 \\
        y_2' = a_2 y_2 \\
        \dots \\
        y_n' = a_n y_n
    \end{cases}
$$
all of which are solvable as $y_k = Ae^{a_k x}$. If we can focus our efforts in transforming the general case $\dot{\mathbf{x}} = \mathbf{A}\mathbf{x} + \mathbf{F}$ into this simplified (and directly solvable) case, we'll have figured out a method to solve many systems of differential equations. 

Note that in the simplified case, the matrix $\mathbf{A}$ is diagonal; our end goal should therefore be to convert every matrix $\mathbf{A}$ into a diagonal matrix, too - one that gives us precisely the scale factor of the matrix along every axis, and nothing else. 

As it turns out, we know precisely how to do that. Suppose that $\mathbf{A}$ has $n$ eigenvalues $\lambda_{1,2,\dots,n}$ satisfying $\det |A-\lambda I|=0$. Define the eigenvalue matrix $\Lambda$ as the diagonal matrix

$$
\Lambda=\begin{bmatrix}
        \lambda_1 & & & \\
        &\lambda_2 & & \\
        & & \ddots & \\
        & & & \lambda_n
    \end{bmatrix}
$$

and define $\mathbf{V}$ as the matrix of eigenvectors $v_1, v_2, \dots, v_n$, each $n \times 1$, corresponding to $\lambda_{1,2,\dots,n}$:

$$
\mathbf{V} = \begin{bmatrix}
        v_1 & v_2 & \dots & v_n
    \end{bmatrix}
$$

We know that, by definition, $Av_k = \lambda_k v_k$. Thus, we have 

$$
\begin{aligned}
        \mathbf{V \Lambda} &= \begin{bmatrix}
            \lambda_1 v_1 & \lambda_2 v_2 & \dots & \lambda_n v_n
        \end{bmatrix}\\
        &=\begin{bmatrix}
            v_1(1)\lambda_1 & v_2(1)\lambda_2 & \dots & v_n(1)\lambda_n \\
            v_1(2)\lambda_1 & v_2(2) \lambda_2 & \dots & v_n(2) \lambda_n \\
            \vdots & \vdots & \ddots & \vdots \\
            v_1(n) \lambda_1 & v_2(n) \lambda_2 & \dots & v_n(n)\lambda_n
        \end{bmatrix} \\
        &= \begin{bmatrix}
            \lambda_1v_1 & \lambda_2v_2 & \dots & \lambda_n v_n
        \end{bmatrix}\\
        &=\begin{bmatrix}
            Av_1 & Av_2 & \dots & Av_n
        \end{bmatrix}\\
        &=\mathbf{AV}
    \end{aligned}
$$

where $v_i(j)$ denotes the $j$th-row element of vector $v_i$. As such, we have $\mathbf{AV=V\Lambda}$ and finally 

$$
\mathbf{A= V\Lambda V^{-1}},\ \mathbf{\Lambda = V^{-1}AV}
$$

for invertible $\mathbf{V}$; this is the process of *diagonalization*, and it allows us to convert any matrix into a diagonal matrix of eigenvectors $\mathbf{\Lambda}$ by multiplying it with two other matrices.

How does this help our cause in solving systems of differential equations? We return to 

$$
\dot{\mathbf{x}} = \mathbf{A}\mathbf{x} + \mathbf{F}
$$

and consider only the homogeneous case for a moment (like we do for normal differential equations):

$$
\dot{\mathbf{x}} = \mathbf{A}\mathbf{x}
$$

Let us impose the change of coordinates $x = \mathbf{Tz}$ for some $n \times n$ matrix $\mathbf{T}$, and $n\times 1$ matrix $\mathbf{z}$. Thus we have 

$$
\mathbf{T\dot{z}} = \mathbf{A}\mathbf{Tz}
$$
and 
$$
\mathbf{\dot{z}} = \mathbf{T^{-1}}\mathbf{A}\mathbf{Tz}
$$
which is just our equation for a diagonal matrix of eigenvectors above! Thus we take $\mathbf{T} = \mathbf{V}$, the matrix of eigenvectors for $\mathbf{A}$, and obtain simply 
$$
 \mathbf{\dot{z}} = \mathbf{\Lambda} \mathbf{z} = \begin{bmatrix}
        \lambda_1 & & & \\
        & \lambda_2 & & \\
        & & \ddots & \\
        & & & \lambda_n
    \end{bmatrix}\mathbf{z}
$$
which gives solutions $z_1 = c_1e^{\lambda_1 x},\ z_2 = c_2e^{\lambda_2 x}, \dots, z_n = c_ne^{\lambda_n x}$ with $\mathbf{x=Vz}$, $\mathbf{V}$ as the eigenvector matrix of $\mathbf{A}$, and $\lambda_{1,2,\dots,n}$ as the eigenvalues of $\mathbf{A}$. In other words, we have
$$
\begin{aligned}
        \mathbf{x} &= \mathbf{Vz}\\
        &= \begin{bmatrix}
            v_1 & v_2 & \dots & v_n
        \end{bmatrix}\begin{bmatrix}
            c_1e^{\lambda_1 x} \\
            c_2 e^{\lambda_2 x} \\
            \vdots \\
            c_ne^{\lambda_n x}
        \end{bmatrix}\\ \\
        &=\begin{bmatrix}
            v_1(1) & v_2(1) & \dots & v_n(1) \\
            v_1(2) & v_2(2) & \dots & v_n(2) \\
            \vdots & \vdots & \ddots & \vdots \\
            v_1(n) & v_2(n) & \dots & v_n(n)
        \end{bmatrix}
        \begin{bmatrix}
        c_1e^{\lambda_1 x} \\
        c_2 e^{\lambda_2 x} \\
        \vdots \\
        c_ne^{\lambda_n x}
        \end{bmatrix}\\ \\
        &=\begin{bmatrix}
            v_1(1)c_1e^{\lambda_1 x} + v_2(1)c_2 e^{\lambda_2 x} + \dots + v_n(1)c_ne^{\lambda_1 x} \\
            v_1(2)c_1e^{\lambda_1 x} + v_2(2)c_2 e^{\lambda_2 x} + \dots + v_n(2)c_ne^{\lambda_1 x} \\
            \dots \\
            v_1(n)c_1e^{\lambda_1 x} + v_2(n)c_2 e^{\lambda_2 x} + \dots + v_n(n)c_ne^{\lambda_1 x} \\
        \end{bmatrix}\\ \\
        &= c_1e^{\lambda_1 x }v_1 + c_2e^{\lambda_2 x}v_2 + \dots + c_ne^{\lambda_n x}v_n
    \end{aligned}
$$

Which is the sum of all $e^{\lambda_k x}$ multiplied by their respective eigenvectors. This is the crucial link between eigenvalues and systems of differential equations; however, it is important to note that not all matrices are as nicely diagonalizable as the generalized example shown above. Matrices may have less than $n$ unique eigenvalues, or have complex eigenvalues, or so on.

There also exists another avenue towards the conclusion that eigenvalues are linked to systems of differential equations. Suppose we know, by divine inspiration, that functions of the form $y_k=Ae^{\lambda_k x}$ for $k=1,2,\dots,n$ were needed to solve the system $\dot{\mathbf{x}} = \mathbf{A}\mathbf{x}$ (a reasonable assumption to make, since every equation in the system is a linear sum of $y_1, y_2, \dots, y_n$ and their derivatives, and so we want $y_k$ and $y_k'$ to be in the same form). Let us assume, then, that 

$$
\mathbf{x} = \mathbf{v}e^{\lambda x}
$$

for some vector $\mathbf{v}$, and thus $\mathbf{\dot{x}} = \lambda \mathbf{x}$. Substituting into $\mathbf{\dot{x}} = \mathbf{Ax}$, we have 

$$
\lambda \mathbf{x} = \mathbf{Ax}
$$

which is the defining equation for eigenvalues of the matrix $\mathbf{A}$, and corresponding eigenvectors $\mathbf{v}$. Thus, the solution to the system is the sum of all

$$
\mathbf{x} = \mathbf{v}e^{\lambda x}
$$

with $\lambda$ an eigenvalue of $\mathbf{A}$ and $v$ a corresponding eigenvector - the same solution as the one we found above through diagonalization.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The solution to the $n \times n$ homogeneous linear system of constant-coefficient differential equations
$$
\dot{\mathbf{x}} = A\mathbf{x}
$$
> is given by $\mathbf{x} = \sum_{i=1}^n v_i e^{\lambda_i x}$, where $v_i$ and $\lambda_i$ denote the $i$th eigenvector and eigenvalue of $A$ respectively.

