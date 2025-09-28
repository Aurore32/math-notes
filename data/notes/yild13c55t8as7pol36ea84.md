> <span style="background-color: #03cafc; color: black;">Definition</span> (Linear combination). Let $V$ be a vector space and $\mathbf{v_1,v_2, ..., v_n} \in V$ be vectors. A **linear combination** of these $n$ vectors is another vector of the form
$$
a_1v_1+a_2v_2+...+a_nv_n
$$
> where $a_1,a_2,...,a_n \in \mathbb{R}$ or $\mathbb{C}$.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Span). The **span** of $n$ vectors $v_1, v_2, ..., v_n$ is the set of all vectors $v$ that are linear combinations of $v_1, v_2, ..., v_n$:
$$
v = \{v\ |\ v = a_1v_1+a_2v_2 + ... + a_nv_n\}
$$
> The span of an empty list () is defined to be $\{0\}$.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Spanning set). If the span of $v_1,v_2,...,v_n$ is the vector space $V$, then we say that $v_1,v_2,...,v_n$ **spans** $V$. 

> <span style="background-color: #03cafc; color: black;">Definition</span> (Linear independence). We say that a list of vectors $(v_1,v_2,...,v_n)$ are **linearly independent** if the only coefficients $a_1, a_2, a_3, ..., a_n$ which satisfy
$$
a_1v_1+a_2v_2+...+a_nv_n = 0
$$
> are $a_1=a_2=a_3=...=a_n=0$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If $(v_1, v_2, ..., v_n)$ are linearly independent and span $V$ such that every element $v \in V$ can be written as $v = a_1v_1+a_2v_2+...+a_nv_n$, a linear combination of the $v_i$s, then the coefficients $a_1, a_2, ..., a_n$ are unique.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Assume for the sake of contradiction that $v \in V$ can be written two ways: $v = \sum a_i v_i,$ and $v = \sum b_i v_i$ where $a_i \neq b_i$ for $i = 1, 2, ..., n$. Then $v-v=\sum(a_i-b_i)v_i=0$. However, as $(v_1,v_2,...,v_n)$ are linearly independent, there is no other combination of coefficients other than $(a_1-b_1)=(a_2-b_2)=...=(a_n-b_n)=0$. This yields a contradiction.

Let's see an example for the simplest vector space, $\mathbb{R^2}$. Suppose that two vectors $\mathbf{a, b}$ span $\mathbb{R^2}$. If they are linearly independent, then $\alpha = 0, \beta = 0$ are the only coefficients that make $\alpha \mathbf{a}+\beta \mathbf{b}=0$ possible; in other words, $\mathbf{a}$ is not a scalar product of $\mathbf{b}$, and they do not lie on the same line. This means that the angle between them is $\pi$, and their vector product (as defined in 2D) is 0:
$$
\mathbf{a\times b = |a||b|}\sin \pi = 0
$$
To prove the above theorem, we can also utilize the properties of the vector product:
> <span style="background-color: #1eff12; color: black;">Proof</span>. Assume for the sake of contradiction that there exists some $\lambda' \neq \lambda$, $\mu' \neq \mu$, all real numbers, such that for vectors $(v_1,v_2)$ and a vector $v \in \mathbb{R^2}$, $v = \lambda v_1 + \mu v_2 = \lambda'v_1 +\mu'v_2$. Performing the vector product of both sides with $v_1$ yields
$$
\lambda v_1 \times v_1 + \mu v_2 \times v_2 = \lambda' v_1 \times v_1 + \mu' v_2 \times v_2
$$
> or
$$
(\mu-\mu')v_1\times v_2 = 0
$$
> as $v_1 \times v_1 = v_2 \times v_2 = 0$ and $v_1 \times v_2 = v_2 \times v_1$. If $v_1$ and $v_2$ are linearly independent, then $v_1 \times v_2 \neq 0$. Thus $\mu - \mu' = 0, \mu - \mu'$, and we reach a contradiction.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Basis). A set of vectors $\{v_1,v_2,...,v_n\}$ is a basis of a vector space $V$ if they are linearly independent and span $V$. For example, $\{(0,1),(1,0)\}$ is a basis of $\mathbb{R^2}$.

Let's show two examples in $\mathbb{R^2}$ and $\mathbb{R^3}$.
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Two vectors $v_1, v_2 \in \mathbb{R^2}$ form a basis of $\mathbb{R^2}$ if they are linearly independent.

> <span style="background-color: #1eff12; color: black;">Proof</span>. Let $r$ be any vector in $\mathbb{R^2}$ and suppose that $r = \alpha v_1 + \beta v_2$. Taking the vector product with $v_1$ on both sides yields $r\times v_1 = \beta v_2 \times v_1$ and $\beta = \frac{r\times v_1}{v_2\times v_1}$; similarly, $\alpha = \frac{r\times v_2}{v_2 \times v_1}$. As $v_1,v_2$ are linearly independent, $v_1\times v_2 \neq 0$ and thus $\alpha$ and $\beta$ always exist for any $r$. Therefore, $v_1$ and $v_2$ form a basis of $\mathbb{R^2}$ by definition.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Three vectors $v_1,v_2,v_3\in \mathbb{R^3}$ form a basis of $\mathbb{R^3}$ if they are linearly independent. The condition for linear independence in $\mathbb{R^3}$ is the triple product: $[v_1,v_2,v_3]\neq 0$.

> <span style="background-color: #bc42f5; color: black;">Observation.</span> The scalar triple product $[v_1,v_2,v_3]$ provides a way of determining whether the three vectors $v_1,v_2,v_3$ are coplanar (share a plane). If the triple product is zero, they share a plane; otherwise, they do not share a plane. <br/><br/> To explain this, let's take a look at what the triple product means; $[v_1,v_2,v_3]=v_1\cdot(v_2\times v_3)$. $v_2\times v_3$ is the direction normal to both $v_2$ and $v_3$. If the dot product between $v_1$ and a vector in this direction is zero, $v_1$ is normal to this normal direction, meaning that $v_1$ is in the same plane as $v_2$ and $v_3$. <br/><br/>
Thus we have:
$$
\begin{cases}
v_1,v_2,v_3 \text{ coplanar if $[v_1,v_2,v_3] = 0$} \\
v_1,v_2,v_3 \text{ not coplanar if $[v_1,v_2,v_3] \neq 0$}
\end{cases}
$$

> <span style="background-color: #1eff12; color: black;">Proof</span>. Similar to the $\mathbb{R^2}$ case, suppose that for any vector $r \in \mathbb{R^3}$, there exist $\alpha, \beta, \gamma \in \mathbb{R}$ such that $r = \alpha v_1 + \beta v_2 + \gamma v_3$. Taking the dot product with $v_2 \times v_3$ on both sides gives
$$
r\cdot (v_2 \times v_3) = \alpha[v_1,v_2,v_3] + 0 + 0
$$
> as $[v_2,v_2,v_3]=v_2\cdot(v_2\times v_3) = [v_3, v_2, v_2] = v_3(v_2\times v_2) = 0$, and by a similar logic the last two terms are both zero. Thus we have $\alpha = \frac{r\cdot (v_2 \times v_3)}{[v_1,v_2,v_3]}$ and a similar process can determine $\beta$ and $\gamma$. As the triple product is not equal to zero, $\alpha,\beta$ and $\gamma$ exist for all vectors $r\in\mathbb{R^3}$ and thus $v_1,v_2,v_3$ is a basis for $\mathbb{R^3}$.

> When $r$ is the zero vector, we find that $\alpha=\beta=\gamma=0$ uniquely and thus $v_1,v_2,v_3$ are linearly independent.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Standard basis). The standard basis for the set $\mathbb{R^n}$ is $\{\mathbf{e_1,e_2,...,e_n}\}$ such that $\mathbf{e_1}=(1,0,...,0), \mathbf{e_2}=(0,1,...,0), ..., \mathbf{e_n}=(0,0,...,0,1)$.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Orthonormal basis). Call a basis $\{\mathbf{e_1,e_2,...,e_n}\}$ **orthonormal** if the dot product of any two distinct elements $\mathbf{e_i\cdot e_j} = 0$ (i.e. any two vectors in the basis are perpendicular), and the magnitude of any vector in the basis $\mathbf{e_i \cdot e_i} =1$. In other words, any two vectors in the basis are normal and every vector in the basis is a unit vector. The standard basis for $\mathbb{R^n}$ is orthonormal.

We now generalize the results found in $\mathbb{R^2}$ and $\mathbb{R^3}$ to $\mathbb{R^n}$.

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. If ${v_1, v_2, ..., v_n}$ is a set of $n$ linearly independent vectors in the vector space $\mathbb{R^n}$, then the set forms a basis of $\mathbb{R^n}$. Indeed, this is true not only for $\mathbb{R^n}$; it is true for any $n$-dimensional vector space.

> <span style="background-color: #03cafc; color: black;">Definition</span> (Dimension). The **dimension** of a vector space $V$, denoted $\dim V$, is the number of elements in its basis.

This definition only makes sense if every possible basis of a vector space is of the same size, which we will prove below:

> <span style="background-color: #1eff12; color: black;">Proof</span>. Suppose that two sets of vectors $u = {u_1,u_2,...,u_m}$ and $v = {v_1,v_2,...,v_n}$ form bases for a vector space $V$. <br/><br/>
Without loss of generality, and for the sake of contradiction, let $n > m$. As $\{v_1, v_2, ..., v_n\}$ forms a basis, the vector $u_1 \in V$ can be written as a linear combination of vectors in $v$: $a=a_1v_1 + a_2v_2 + ... + a_nv_n$ for scalars $a_1,a_2,...,a_n$. <br/><br/>
Thus, we have $v_1=u_1-a_2v_2-a_3v_3-...-a_nv_n$ and thus $v_1$ can be written as a linear combination of $v'=\{u_1, v_2, ..., v_n\}$. As such, $v'$ also forms a basis. This process can be repeated for $u_2, u_3, ..., u_m \in u$, which eventually leads to the basis $w=\{u_1,u_2,u_3,...,u_m,v_{m+1},v_{m+2},...,v_{n}\}$. <br/><br/>
The steps above imply that the vectors in $w$ are linearly independent, but as $\{u_1,u_2,...,u_m\}$ is already a basis, all of $v_{m+1},v_{m+2},...,v_n$ can be written as linear combinations of $u_1,...,u_m$. Thus, $w$ is not linearly independent and we reach a contradiction.

