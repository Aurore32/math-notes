> Gradients are denoted by $\nabla$, pronounced "del" or "nabla" because they look like an ancient harp-like Hebrew instrument with the same shape. This is astonishing, as the list of $\nabla$-shaped objects has length $N >> 1$ and some of them roll off the tongue much better, like "Huell Babineaux's pointy head hanging upside-down on a yoga mat" and "Danny DeVito's humongous dumptruck". 

## The Gradient Vector

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **gradient** of a multivariate scalar function $f(x_1, x_2, ..., x_m): \mathbb{R^m \to R}$, denoted $\nabla f$ and pronounced ~~REDACTED~~, is defined as the vector
$$
\nabla f = \begin{bmatrix}
\frac{\partial f}{\partial x_1} \\
\frac{\partial f}{\partial x_2} \\
\vdots \\
\frac{\partial f}{\partial x_n}
\end{bmatrix}
$$
> i.e. a vector whose components are the partial derivatives of $f$ in sequence. 

> <span style="background-color: #ffb812; color: black;">Properties</span>. From the properties of (partial) differentiation, and if $f$ and $g$ are both functions mapping from $\mathbb{R^m \to R}$.n:
1. $\nabla(\lambda f + \mu g) = \lambda \nabla f + \mu \nabla g$;
2. $\nabla(fg) = f\nabla g + g \nabla f.$

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The directional derivative of $f$ in the direction of the unit vector $\hat{u}$ is given by the dot product between the gradient vector and $\hat{u}$, $(\nabla f) \cdot \hat{u}$. Simultaneously, the **direction of steepest ascent** - the direction where the function increases the most - is given by the gradient vector itself.

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Recall that the directional derivative of $f$ in the direction of $\hat{u}$ is the change of $f$ when taking an infinitesimally small step in the direction $\hat{u}$. Thus if 
$$
\hat{u} = \begin{bmatrix}
u_1 \\ u_2 \\ \vdots \\ u_m
\end{bmatrix}
$$
i.e. $u_1$ steps in direction $x_1$, $u_2$ in $x_2$, etc., and the rate of change in each of these directions are given by $\frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}$, etc., we have
$$
f'(\mathbf{x}; \hat{u}) = u_1 \frac{\partial f}{\partial x_1} + u_2 \frac{\partial f}{\partial x_2} + ... + u_m \frac{\partial f}{\partial x_m} = \nabla{f} \cdot \hat{u}.
$$
What is the maximum value of such a directional derivative, i.e. what direction does $f$ increase the quickest in? $\nabla{f}\cdot \hat{u}$ has magnitude at most $\nabla{f}$ as $\hat{u}$ is a unit vector, and this maximum is achieved when $\nabla{f}$ and $\hat{u}$ are in the same direction (the cosine of the angle in-between them is $1$). Thus, when you travel in the direction of the gradient vector, you ascend the function $f$ quickest. 

