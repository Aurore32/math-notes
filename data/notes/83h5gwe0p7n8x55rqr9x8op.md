Similar to the scalar product, we can also define a binary operation known as the *vector product* over a vector space that takes two vectors and outputs another vector:

> <span style="background-color: #03cafc; color: black;">Definition</span> (Vector product). For vectors $\mathbf{a, b} \in \mathbb{R^3}$, define the *vector product* between them as
$$
\mathbf{a\times b} = |\mathbf{a}||\mathbf{b}|\sin \theta\ \mathbf{\hat{n}}
$$
> Where $\mathbf{\hat{n}}$ is the unit vector in the direction normal to both $\mathbf{a}$ and $\mathbf{b}$, and $\theta$ is the angle between the two vectors.

Essentially, the vector product takes two vectors and outputs another vector with length equal to the product of their lengths times $\sin \theta$, and in a direction normal to both of them. To make such an output unique, we restrict this direction to be the normal direction to $\mathbf{a, b}$ in a *right-handed sense*:

![alt text](./assets/images/image.png)

The vector product satisfies the following properties:
1. $\mathbf{a\times b = b\times a}$.
2. $\mathbf{a \times a = 0}$.
3. $\mathbf{a \times b = 0}\iff \mathbf{a} = \lambda \mathbf{b}$ for some $\lambda \in \mathbb{R}$, or $\mathbf{b}= 0$
4. $\mathbf{a \times}\lambda\mathbf{b} = \lambda(\mathbf{a\times b})$
5. $\mathbf{a}\times \mathbf{(b + c)} = \mathbf{a\times b + a \times c}$.

The following sections will demonstrate three nifty applications of the vector product.
### Finding normal vectors
As mentioned, the vector product outputs a vector normal in direction to both input vectors. We propose that it can be calculated as follows:
> <span style="background-color: #ffb812; color: black;">Proposition</span>: $\mathbf{a \times b} = \begin{vmatrix}\hat{\mathbf{i}} & \hat{\mathbf{j}} & \hat{\mathbf{k}} \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{vmatrix}$, in which $a_1, a_2, a_3$ are the components of $\mathbf{a}$, $b_1, b_2, b_3$ of $\mathbf{b}$, and $\mathbf{i, j, k}$ are the unit vectors in the three axes.

### Area of a triangle
If vectors $\mathbf{a}$ and $\mathbf{b}$ are two sides a triangle (with $\mathbf{b-a}$ as the third side), then we know that the area of the triangle is half the product of the lengths of two sides times the sine of the angle between them: 
$$
S = \frac{1}{2}|\mathbf{a}||\mathbf{b}|\sin \theta.
$$
However, the magnitude of the vector product itself is simply
$$
|\mathbf{a\times b}| = ||\mathbf{a}||\mathbf{b}|\sin \theta\ \mathbf{\hat{n}}| = |a||b|\sin \theta |\mathbf{\hat{n}}| = |a||b|\sin \theta
$$
as $\hat{n}$ is a unit vector. Thus, the area of the triangle is half the magnitude of the vector product.

### Area of a parallelpiped
(Derived from the Ancient Greek prefix *parallel*, meaning parallel, and *pipos*, meaning pipes.)

![alt text](./assets/images/image-1.png)

A parallelpiped is just a really jiggly parallelogram. (This should be a proposition.) We first define
> <span style="background-color: #03cafc; color: black;">Definition</span> (Scalar triple product). Write $[\mathbf{a,b,c}]$ for three vectors $\mathbf{a,b,c}$ to denote the product $\mathbf{a\cdot(b\times c)}$. As this is a vector product first and a scalar product second, this outputs a scalar.

We propose that 
><span style="background-color: #ffb812; color: black;"> Proposition</span>. ~~A parallelpiped is just a really jiggly parallelogram.~~ A parallelpiped with sides $\mathbf{a,b,c}$, which form a **right-handed system** as shown above, has volume equal to $[\mathbf{a,b,c}]$.

> <span style="background-color: #1eff12; color: black;">Proof.</span> The volume of this parallelopiped is the area of the parallelogram encompassed by $\mathbf{b,c}$ multiplied by its height. 


> First, the area of that parallelogram is $|\mathbf{b\times c}|$ - double the area of a triangle, which has area $\frac{1}{2}|\mathbf{b\times c}|$ as shown above.

> We note that the height of the parallelpiped is $|\mathbf{a}|\cos \theta$, where $\theta$ is the angle between $\mathbf{a}$ and the direction normal to the base - thus, the direction normal to both $\mathbf{b}$ and $\mathbf{c}$. 

> This direction is given by the dot product $\mathbf{a} \cdot (\mathbf{b\times c})$, as it equals $|\mathbf{a||b\times c|}\cos \theta$ where $\theta$ is exactly the angle we are looking for. This completes the proof.

As long as we choose an order of the vectors $\mathbf{a,b,c}$ such that they still form a right-handed system, the value of $[\mathbf{a,b,c}]$ should not be affected because it outputs the volume of the parallelpiped:
$$
\mathbf{[a,b,c]=[b,c,a]=[c,a,b]}
$$
However, if the three vectors form a left-handed system instead, then the value of the triple product is made negative:
$$
\mathbf{[a,b,c] = -[a,c,b] = -[b,a,c] = -[c,b,a]}
$$
### A final note on the vector product in 2D and 3D
In 3D (vectors in $\mathbb{R^3}$), the vector product is all fine and dandy; it has a geometric interpretation as a vector perpendicular to two vectors, and it outputs a vector. This definition completely collapses when we reach a different dimension, like my mental health after doing too many seeded Minecraft speedruns in an hour. As such, in 2D we simply define
$$
\mathbf{a\times b} = |\mathbf{a}||\mathbf{b}|\sin\theta.
$$
