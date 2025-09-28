> What does a mathematician and the order of the differential equation they're studying have in common? They're both high.

## Higher-order partial derivatives

> <span style="background-color: #03cafc; color: black;">Definition</span>.
**Higher-order partial derivatives** are partial derivatives of lower-order partial derivatives. For instance, a **second-order** partial derivative for a function $f(x, y)$ could be

$$
\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial}{\partial x}\frac{\partial }{\partial y}f(x,y);
$$
> Denote the above as $f_{xy}$, and more generally, any sequence of partial derivatives, in order, as $f_{x_ix_j ...}$ for variables $x_1, ..., x_m$. For a function of two variables $f(x,y)$, if the second-order derivative $f_{x_i x_j}$ satisfies $x_i \neq x_j$, then the derivative is called a **mixed** second-order partial derivative.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The mixed second-order partial derivatives of $f(x,y)$, $f_{xy}$ and $f_{yx}$, are equal at a point $(x_0, y_0)$ **if and only if** at least one of $f_{xy}$ and $f_{yx}$ are continuous at $(x_0, y_0)$.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Trivial.

This is a consequence of the Divergence Theorem.

> <span style="background-color: #03cafc; color: black;">Example</span>. Change of variables for second-order partial derivatives.


Suppose that, after I "befriended" your mom last night, your dad comes home with the milk and intimately acquaints me with the barrel of his shotgun. Now my escape velocity as I run to a point $(x,y)$ in your backyard is given by $z = f(x,y)$. We want to convert this to pole coordinates $x = \rho \cos \theta$, $y = \rho \sin \theta$. As previously shown, our first-order partial derivatives were

$$
\begin{aligned}
(\frac{\partial f}{\partial \rho})_{\theta} &= (\frac{\partial f}{\partial x})_y(\frac{\partial x}{\partial \rho})_\theta + (\frac{\partial f}{\partial y})_x(\frac{\partial y}{\partial \rho})_\theta \\
&= (\frac{\partial f}{\partial x})_y\cos \theta + (\frac{\partial f}{\partial y})_x\sin \theta \\
\end{aligned}
$$
and
$$
\begin{aligned}
(\frac{\partial f}{\partial \theta})_{\rho} &= (\frac{\partial f}{\partial x})_y\frac{\partial x}{\partial \theta} + (\frac{\partial f}{\partial y})_x\frac{\partial y}{\partial \theta} \\
&= -(\frac{\partial f}{\partial x})_y\rho \sin \theta + (\frac{\partial f}{\partial y})_x\rho \cos \theta \\
&= - y (\frac{\partial f}{\partial x})_y + x (\frac{\partial f}{\partial y})_x
\end{aligned}
$$
so what are the second-order partial derivatives - for instance, $\frac{\partial^2 f}{\partial \rho\ \partial \theta}$? We have
$$
\begin{aligned}
\frac{\partial^2 f}{\partial \rho\ \partial \theta} &= \frac{\partial}{\partial \rho}(\frac{\partial f}{\partial \theta})_{\rho} \\
&= \frac{\partial}{\partial \rho} (- y (\frac{\partial f}{\partial x})_y + x (\frac{\partial f}{\partial y})_x) \\
\end{aligned}
$$
where the operator $\frac{\partial}{\partial \rho}$ can itself be rewritten
$$
\frac{\partial}{\partial \rho} = (\frac{\partial}{\partial x})_y\cos \theta + (\frac{\partial}{\partial y})_x\sin \theta 
$$
allowing the above to be written completely in terms of $x$ and $y$.

## Taylor's theorem (multivariate case)

Recall **Taylor's theorem** in the single-variable case (to reiterate, only barely one of Taylor's ten greatest contributions to mankind, above "Cruel Summer" and far below "Exile"):

$$
f(x+h) = f(x) + \sum_{k=1}^N \frac{h^k}{k!} f^{(k)}(x) + R_N(h)
$$
for a $N+1$-time differentiable function $x$, with 
$$
R_N(h) = \frac{h^{k+1}}{(k+1)!}f^{(k+1)}(\xi)
$$
for $x < \xi < x+h$. The generalized version of this theorem to multiple variables states:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Taylor's theorem for multivariate functions**. Let $f$ be a function $\mathbb{R}^m \to \mathbb{R}$, and let $\mathbf{a}$ be a point in the domain of $f$. Suppose that the partial derivatives of $f$ up to the $N+1$th-order are all continuous at $\mathbf{a}$. Then for some $\mathbf{h} \in \mathbb{R}^m$,
$$
f(\mathbf{a+h}) = f(\mathbf{a}) + \sum_{k=1}^N  \frac{\mathbf{(h \cdot \nabla})^k}{k!}f(\mathbf{a}) + R_N(\mathbf{h})
$$
where
$$
R_N(\mathbf{h}) = \frac{\mathbf{(h \cdot \nabla)}^{N+1}}{(N+1)!}f(\mathbf{a + \theta h})
$$
for $0 < \theta < 1$, and the operator $\mathbf{(h \cdot \nabla)}$ applied to $f$ denotes the sum
$$
\mathbf{(h \cdot \nabla)}f = \mathbf{h}_i \frac{\partial f}{\partial x_i}
$$
using summation convention.

> <span style="background-color: #ffb812; color: black;">Remark</span>. By the summation convention, the operator
$$
\mathbf{(h \cdot \nabla)}^{k}
$$
> for $k \in \mathbb{N}$ can be rewritten
$$
(\mathbf{h}_{j_1} \frac{\partial }{\partial x_{j_1}})(\mathbf{h}_{j_2} \frac{\partial }{\partial x_{j_2}})...(\mathbf{h}_{j_k} \frac{\partial }{\partial x_{j_k}})
$$
> equalling
$$
\mathbf{h}_{j_1} \mathbf{h}_{j_2}...\mathbf{h}_{j_n}\frac{\partial}{\partial x_{j_1}}\frac{\partial}{\partial x_{j_2}}...\frac{\partial}{\partial x_{j_n}}.
$$
where the order of the partial derivatives does not matter, by means of partial derivatives commuting if they are continuous at $\mathbf{a}$.

Taylor's theorem also holds for vector-valued functions, where the above statement is applied *component-wise*:

$$
f_i(\mathbf{a+h}) = f_i(\mathbf{a}) + \sum_{k=1}^N  \frac{\mathbf{(h \cdot \nabla})^k}{k!}f_i(\mathbf{a}) + R_N(\mathbf{h})_i
$$

for $i = 1, 2, ..., n$. 

> <span style="background-color: #03cafc; color: black;">Example</span>. Suppose that 
$$
f(\mathbf{x}): \mathbb{R^3 \to R} = \frac{1}{|\mathbf{x}|} = \frac{1}{\sqrt{x_1^2 + x_2^2 + x_3^2}}. 
$$

> Let $|\mathbf{x}| = r.$ Then for some $\mathbf{h} \in \mathbb{R}^3$, we have
$$
\begin{aligned}
(\mathbf{h \cdot \nabla})f &= h_1f_{x_1} + h_2f_{x_2} + h_3 f_{x_3} \\
&= -h_1\frac{x_1}{r^3} -h_2\frac{x_2}{r^3}-h_3\frac{x_3}{r^3}
\end{aligned}
$$
and so on.
