---
id: 5xckuaks5kuji8gyg4ah7pv
title: Tensors are Tensors
desc: ''
updated: 1752566729132
created: 1742605673599
nav_order: 1
---
## What are tensors?

> <span style="background-color: #03cafc; color: black;">Definition</span>. A tensor is something that transforms like a tensor.

Perhaps one of the greatest distillations of human knowledge in written form ever to be recorded, alongside similar masterpieces such as "Newtonian physics are physics that make sense in a Newtonian frame of reference", "I would've won if I didn't lose!", and "risk of early-onset dementia declines sharply after the age of 70". 

Just like how you could technically define a chair as being "a four-legged object somebody could sit on, excepting cows, pigs, sofas, and all non-chair things", a tensor is everything that looks like a tensor except for the things that aren't tensors. So what constitutes "looking like a tensor", and what constitutes the "except"?

### What do tensors look like?

Just like how vectors look like a list of numbers or matrices look like a list of numbers in need of a weight-loss regime or Harry Potter looks like Daniel Radcliffe, tensors also look like a list of numbers: specifically, what we call an *array*, like a matrix or a vector - except this time it has more dimensions (three dimensions, or four, or a hundred), has more indices ($T_{ijk}$ instead of $T_{ij}$ or $x_i$), and is still a big list of numbers. 

All tensors, therefore, can be represented as arrays: a group of numbers placed together in some $n$-dimensional grid. But are all arrays tensors? If you have an array, what excepts it from being a tensor?

### What do tensors need to be?

What makes a vector a vector? You could just be tempted to say "a list of numbers", but that's not right - the list of numbers mean something specific: a point in space. A vector is a representation of a point in space.

Similarly, what makes a matrix a matrix? Basically every page of the however-many-hundred-pages-long course notes over in [[Linear Algebra]] was dedicated to stressing this: a matrix is not just an array of numbers, but a representation of a linear map - something that maps a point in $\mathbb{R^n}$ to $\mathbb{R^m}$.

If vectors and matrices both represent something concrete, something that goes beyond the numbers that are present in the array itself, then it's reasonable to say that if we do something to that vector or that matrix - if we **change its basis** from Cartesian to whatever coordinate system we like, that underlying "something" - the point represented by a vector, or the linear map by a matrix, will remain exactly the same.

Essentially, that's what makes a tensor a tensor: invariance under changes of basis. A tensor represents something that doesn't change even in a different coordinate system (and as we'll see, that "something" is a **multi-linear map** between vector spaces), and do not depend on any set of particular coordinates: a constant of the universe, like $\pi$ or $e$ or the speed of light.

## Tensor transformation laws

### Vector transformations

Suppose we have a vector $\mathbf{x} = x_i \mathbf{e}_i$, $i = 1, 2, ..., n$, in some orthonormal basis $\mathbf{e}_i$; this vector is a set of coordinates in the basis $\mathbf{e_i}$ describing a point whose existence is itself independent from its coordinate system. As such, under a change of basis to an alternate set of **orthonormal** basis vectors $\mathbf{e_i} \to \mathbf{e_i}'$ described by
$$
\begin{aligned}
\mathbf{e_i}' &= R_{ij}\mathbf{e_j} \\
&= R_{i1}\mathbf{e_1} + R_{i2}\mathbf{e_2} + ... + R_{in}\mathbf{e_n} \\




\end{aligned}
$$
where $R_{ik}$ are the elements of a $n\times n$ matrix $R$, we have
$$
\mathbf{e_i}' \cdot \mathbf{e_j}' = R_{ik}R_{jl}(\mathbf{e_k}\cdot\mathbf{e_l}) =  R_{ik}R_{jl}\delta_{kl} = R_{ik}R_{jk} = (RR^T)_{ij}
$$
due to orthonormality between $\mathbf{e_k}$ and $\mathbf{e_l}$, and due to orthonormality between $\mathbf{e_i}'$ and $\mathbf{e_j}'$ we have
$$
(RR^T)_{ij} = \delta_{ij}
$$
and thus
$$
RR^T = I
$$
where $I$ is the identity matrix. If $\mathbf{e_i}' = R_{ij}\mathbf{e_j}$, then we have
$$
\begin{aligned}
\mathbf{e_i}' &= R_{ij}\mathbf{e_j} \\

&=
\begin{bmatrix}
R_{i1}(e_1)_1 + R_{i2}(e_2)_1 + ... + R_{in}(e_n)_1 \\
R_{i1}(e_1)_2 + R_{i2}(e_2)_2 + ... + R_{in}(e_n)_2 \\
\vdots \\
R_{i1}(e_1)_n + R_{i2}(e_2)_n + ... + R_{in}(e_n)_n
\end{bmatrix} \\
&=
\begin{bmatrix}
\mathbf{e_1} & \mathbf{e_2} & ... & \mathbf{e_n}
\end{bmatrix}

\begin{bmatrix}
R_{i1} & R_{i2} & ... & R_{in}
\end{bmatrix}^T

\end{aligned}
$$
interpreting the row vector of vectors as shorthand for the matrix
$$
\begin{bmatrix}
\mathbf{e_1} & \mathbf{e_2} & ... & \mathbf{e_n}
\end{bmatrix}  = \begin{bmatrix}
(e_1)_1 & (e_2)_1 & ... & (e_n)_1 \\
(e_1)_2 & (e_2)_2 & ... & (e_n)_2 \\
\vdots & \vdots & \ddots & \vdots \\
(e_1)_m & (e_2)_m & ... & (e_n)_m
\end{bmatrix}
$$
leading to
$$
\begin{bmatrix}
\mathbf{e_1}' & \mathbf{e_2}' & ... & \mathbf{e_n}'
\end{bmatrix} = \begin{bmatrix}
\mathbf{e_1} & \mathbf{e_2} & ... & \mathbf{e_n}
\end{bmatrix} R^T
$$
and
$$
\begin{bmatrix}
\mathbf{e_1}' & \mathbf{e_2}' & ... & \mathbf{e_n}'
\end{bmatrix} R
 = \begin{bmatrix}
\mathbf{e_1} & \mathbf{e_2} & ... & \mathbf{e_n}
\end{bmatrix}
$$
due to the properties of *orthogonal matrices* $R$ (which, as mentioned in [[Linear Algebra.Transformation Groups]], are either rotations, reflections, or combinations of both). This gives us
$$
\mathbf{e_j} = R_{ij}\mathbf{e_i}' 
$$

providing us with our transformation law for vectors: if $\mathbf{x} = x_i \mathbf{e}_i$ can be written in an alternate orthonormal basis $\mathbf{e_i}'$ as $\mathbf{x} = x_i' \mathbf{e_i}'$, then

$$
x_i \mathbf{e_i} = x_i R_{ji} \mathbf{e_j}' = x_i' \mathbf{e_i}' = x_j' \mathbf{e_j}'
$$
simply changing index labels, resulting in
$$
R_{ji}x_i = x_j',
$$
or, relabeling,
$$
R_{ij}x_j = x_i'.
$$

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Vector transformation law**. For a vector with components $x_i$ in orthonormal basis $\mathbf{e_i}$ and new components $x_i'$ in another orthonormal basis $\mathbf{e_i}'$, the following relationship holds true:
$$
R_{ij}x_j = x_i'.
$$
As a vector equation, this can be expressed as
$$
\mathbf{x}' = R\mathbf{x}.
$$

> Note that the definition of $R$ here, i.e. $\mathbf{e_i'}=R_{ij}\mathbf{e_j}$, is actually the inverse of how we defined the transformation matrix in [[Linear Algebra.Eigenvalues and Eigenvectors.Change of Basis]]: there we had $\mathbf{e_i}' = R_{ji}\mathbf{e_j} = R^T_{ij}\mathbf{e_j}$. The two definitions are inverses of one another.

### Matrix transformations

As mentioned, matrices can be understood as representations of linear maps: for a vector $\mathbf{x} \in \mathbb{R^n}$ and a $n \times n$ matrix $A$, the matrix product
$$
A\mathbf{x} = \mathbf{x'}
$$
maps $\mathbf{x}$ to a new vector $\mathbf{x'} \in \mathbb{R^n}$ in a way that satisfies the conditions of linearity. A *change of basis* for a linear map is equivalent to asking this: if $A$ took $\mathbf{x}$ to $\mathbf{x'}$ with both being written in the basis $\mathbf{e_i}$, what matrix $A'$ would take $\mathbf{x}$ to $\mathbf{x'}$ in the basis $\mathbf{e_i'}$?

To accomplish this, simply change basis for both $\mathbf{x}$ and $\mathbf{x'}$ as per the vector transformation law (supposing that $R$ is the transformation vector between bases $\mathbf{e_i}$ and $\mathbf{e_i}'$):
$$
A'(R\mathbf{x}) = R\mathbf{x'}
$$
with $A'$ being the matrix after a change of basis. Using $\mathbf{x'} = A\mathbf{x}$, we have
$$
A' (R\mathbf{x}) = R(A\mathbf{x})
$$
or $A' R = RA$, giving
$$
A' = RAR^{-1} = RAR^{T} 
$$
and in summation notation,

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Matrix transformation law**. For a $n\times n$ matrix $A$ and a transformation matrix $R$ between two bases $\mathbf{e_i}$ and $\mathbf{e_i'}$, we have
$$
A'_{ij} = R_{ik}A_{kl}R^T_{lj} = R_{ik}R_{jl}A_{kl}.
$$
> with $A'$ being the matrix under a change of basis by $R$.

Note that - crucially - **the matrix changes under a change of basis, but not the linear map itself.**

### General tensor transformations

Compare the vector transformation law
$$
x'_i = R_{ij} x_j
$$
and the matrix transformation law
$$
A'_{ij} = R_{ik}A_{kl}R^T_{lj} = R_{ik}R_{jl}A_{kl}.
$$
Aside from the obvious - the fact that the first formula is slightly more sane and slightly less inclined towards an extended stay in the University's insane asylum (also known as its Math Department) than the second - how are these two transformation laws related? Tidying up the indices may reveal slightly more. For vectors, now labeled $T_{i_1}$ instead of $x_i$, we have
$$
T_{i_1}' = R_{i_1 j_1} T_{j_1}
$$
and for matrices, now labeled $T_{i_1 i_2}$ and with $k$, $l$ becoming $j_1$ and $j_2$, we have
$$
T_{i_1 i_2}' = R_{i_1 j_1} R_{i_2 j_2} T_{j_1 j_2}.
$$
Besides swiftly arriving at the conclusion that mathematicians should've never been let out of their pink little playpens and that every parent should mathematician-proof their house and that chalk companies deserve to be internationally sanctioned for being responsible for this crime against humanity, we *also* swiftly arrive at our Final Destination (trademark, copyright):

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **General tensor transformation law.** A tensor $T_{i_1 i_2 ... i_p}$ of rank $p$ (with $p$ indices) is something that transforms like a tensor; that means that, under a matrix $R$ representing a change of basis from $\mathbf{e_i}$ to $\mathbf{e_i}'$, $T$ transforms to $T'$ component-by-component as follows:
$$
T'_{i_1 i_2 ... i_p} = (\Pi_{k=1}^p R_{i_k j_k})T_{j_1 j_2 ... j_p} = R_{i_1 j_1} R_{i_2 j_2} ... R_{i_p j_p} T_{j_1 j_2 ... j_p}.
$$

> Note that $R$ is required to be orthogonal (and thus a transformation matrix between two orthonormal bases, marking a rotation, a reflection or both), and that second-rank tensors (analogous to matrices) can be represented as square matrices.

A tensor of rank $p$ is also known as a $p$-tensor. A tensor of rank $0$ is also sometimes known as a real number. Real numbers are nice and warm and cuddly. Why can't we be studying them all the time?

### What is not a tensor?

$$
T_{ij} = \begin{bmatrix}
6 & 9 & 4 \\
2 & 0 & 6 \\
9 & 4 & 2
\end{bmatrix}
$$
This is a tensor. We know that because it's a square, and it has loads of numbers in it, and it even has that funny little thing at the bottom we call an index. That means it has to be a tensor, right? Right?

WRONG, you stupid bonehead. It's not. Or at least, we don't know if it is.

If we say a vector is a tensor or a matrix is a tensor, what does that mean, exactly? We aren't saying that the list of numbers making up the vector is a tensor; we're saying that the **point** the vector describes is a tensor, because it doesn't change under a change of basis. We aren't saying that the array making up a matrix is a tensor either; we're saying that the **linear map** the matrix represents is a tensor, because that doesn't change under a change of basis.

Therefore, it's crucial that we all repeat after me: just like how a vector represents a point and a matrix a linear map, a tensor is **not** an array of numbers, but the **multilinear map** that array of numbers represents. A tensor is **not** an array of numbers, but the **multilinear map** that array of numbers represents. A tensor is **not** an array of numbers, but the **multilinear map** that array of numbers represents. ~~I haven't talked to my family in six months please get me out of here~~

Therefore, if a real number **doesn't** describe a quantity that's invariant under change of basis, or if a vector **doesn't** describe the same point, or if a matrix **doesn't** describe a linear map, then they aren't tensors. Is $A = 3$ a tensor? If $A$ means area, then it isn't - area depends on the basis used. Again, is 
$$
T_{ij} = \begin{bmatrix}
6 & 9 & 4 \\
2 & 0 & 6 \\
9 & 4 & 2
\end{bmatrix}
$$
a tensor? If it's a linear map, sure, but if the numbers mean "number of ants crawling on each square of my $3\times 3$ chocolate bar" then probably not.

> <span style="background-color: #ffb812; color: black;">Proposition</span>. One final note: both the Levi-Civita symbol $\epsilon_{ijk}$ and the Kronecker delta $\delta_{ij}$ are tensors. They have the special property of being a little baby and not changing their components even when everyone else is changing their basis. Call these tensors **invariant tensors** (more on this later!)
