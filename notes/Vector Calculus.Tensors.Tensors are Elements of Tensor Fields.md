---
id: jqmpl4v1p55nm8mwx655y7w
title: Tensors are Tensor Fields
desc: ''
updated: 1752577914530
created: 1742655660227
nav_order: 3
---

## Invariant and isotropic tensors

> <span style="background-color: #03cafc; color: black;">Definition</span>. Call a tensor $T$ invariant under a given rotation $R$ if all of its components remain identical after transformation by $R$:

$$
T'_{i_1 i_2 ... i_p} = T_{j_1 j_2 ... j_p}R_{i_1 j_1} R_{i_2 j_2} ... R_{i_p j_p} = T_{i_1 i_2 ... i_p}.
$$

> <span style="background-color: #03cafc; color: black;">Definition</span>. If a tensor $T$ is invariant under **any** rotation $R$, it is called **isotropic**.

All scalars are isotropic; no vector is isotropic because they have a fixed direction, and thus will always transform under rotation. In particular, we claim that

> <span style="background-color: #ffb812; color: black;">Proposition</span>. There are only two nonzero isotropic rank $p = 1, 2,$ or $3$ tensors: a constant multiple of the totally symmetric rank $2$ Kronecker delta $\delta_{ij}$, and a constant multiple of the totally antisymmetric rank $3$ Levi-Civita symbol. 

> <span style="background-color: #1eff12; color: black;">Proof</span>.

First we prove that both tensors are invariant. For the Kronecker delta, this follows from
$$
\delta'_{ij} = \delta_{mn} R_{im}R_{jn} =  R_{in}(R^T)_{nj} = \delta_{ij}
$$
as $RR^T = I$; for the Levi-Civita symbol this follows from
$$
\epsilon_{ijk}' = \epsilon_{lmn}R_{il}R_{jm}R_{kn} = \det R\ \epsilon_{ijk} = \epsilon_{ijk}
$$
by definition of the determinant; note that if $R$ is a reflection instead of a rotation $\epsilon$ is no longer invariant, as $\det R = -1$.

To prove that the above two tensors are the only two possible invariant tensors, we consider ranks 1, 2 and 3 separately.

For rank $1$ tensors, consider the matrix $R$ of a rotation by $\pi$ counterclockwise about the $z$-axis:
$$
R = \begin{bmatrix}
-1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
Suppose that $T_i$ is a $1$-tensor. For it to be isotropic, we must have
$$
T_i' = R_{ij}T_j = T_i
$$
Looking through the rows, this suggests
$$
\begin{cases}
-T_1 = T_1 \\
-T_2 = T_2 \\
T_3 = T_3
\end{cases}
$$
which gives $T_1 = T_2 = 0$. If $-R$ is used instead of $R$, a similar argument is obtained for $T_3 = 0$; thus, any isotropic tensor of rank $1$ is a zero tensor.

For rank $2$ tensors, considering
$$
R = \begin{bmatrix}
0 & 1 & 0 \\
-1 & 0 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
yields
$$
R_{ik}R_{jl}T_{kl} = T_{ij}
$$
which across the individual rows yields
$$
T_{13}  = R_{1k}R_{3l}T_{kl} = R_{3l}T_{2l} = T_{23} 
$$
and
$$
T_{23} = R_{2k}R_{3l}T_{kl} = -R_{3l}T_{1l} = -T_{13}
$$
implying $T_{13} = T_{23} = 0$; the same argument can be made for all non-diagonal elements, which all vanish to $0$.

For diagonal elements, e.g. $T_{11}$, we havee
$$
T_{11} = R_{1k}R_{1l}T_{kl} = R_{1l}T_{2l} = T_{22}
$$
with similar arguments showing that all diagonal elements are equal.

Thus, all isotropic rank $2$ tensors have equal diagonal elements and non-diagonal elements equalling zero; this is in the form $\alpha \delta_{ij}$ for a constant $\alpha$.

For rank $3$ tensors, considering both the above transformation matrices yields that $T_{ijk} = 0$ if any two indices are equal and $T_{ijk} = -T_{jik}$. This is in the form $\beta \epsilon_{ijk}$. $\ \square$

### Rank $2$ tensor decomposition

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Any rank $2$ tensor (which is just a fancy name for a matrix) can be decomposed into a **traceless** rank $2$ tensor and two isotropic tensors $\alpha \delta_{ij}$ and $\epsilon_{ijk} B_{k}$ for another tensor $B$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Begin with the symmetric/anti-symmetric decomposition of a rank $2$ tensor $T$. For any $T$, we have
$$
T_{ij} = \frac{T_{ji} + T_{ij}}{2} + \frac{T_{ij} - T{ji}}{2}
$$
of which the first term is symmetric and the second is anti-symmetric; denote the first term $S_{ij}$ and the second $A_{ij}$. If the tensor $S$ has trace $Q$, then the tensor $S - \frac{Q}{3}\delta_{ij}$ has trace zero ("traceless") due to the additive properties of trace; thus we have
$$
S_{ij} = P_{ij} + \frac{Q}{3}\delta_{ij}
$$
further decomposing $S$ into a *traceless* tensor $P$ and an isotropic tensor $\delta_{ij}$. Similarly, we can decompose any antisymmetric tensor $A_{ij}$ of rank $2$ into the product contraction
$$
A_{ij} = \epsilon_{ijk}B_{k}
$$
for some rank $1$ tensor $B$, as $A_{ji} = \epsilon_{jik}B_{k} = - A_{ij}$. In total, this gives us
$$
T_{ij} = P_{ij} + \frac{Q}{3}\delta_{ij} + \epsilon_{ijk}B_k.
$$
In particular, $B_{k}$ is $\frac{1}{2} \epsilon_{ijk}A_{ij}$.


## Tensor fields and their derivatives

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **tensor field** over $\mathbb{R^3}$ assigns a tensor $T_{i_1 ... i_k}$ to every point $\mathbf{x} \in \mathbb{R^3}$; such a tensor field can be written $T(\mathbf{x}): \mathbb{R^3} \to \mathbb{R^m}$, with $m$ the **number of components** (not the rank) of the tensor.

Defining a (partial) derivative of a tensor field takes a bit of work. One possible interpretation is a component-by-component derivative: differentiating a tensor field just leaves us with the tensor containing the derivatives of all its components, much like differentiating a vector field. But with the tensor product, we can do something better.

> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the $N$th **tensor-valued** derivative of a rank-$m$ tensor field $T$ as the rank-$m+n$ tensor $X$ with components

$$
X_{i_1 ... i_n j_1 ... j_m} = \frac{\partial}{\partial x_{i_1}} ...\ \frac{\partial}{\partial x_{i_n}} T_{j_1 ... j_m}
$$
where $x_{i_1}, ..., x_{i_n}$ are arbitrarily chosen variables in the domain of the tensor field.

Note that this is defined on a **component-by-component** basis: the components of this new tensor field are every possible $n$th-derivatives of the original tensor component. 

We note, very importantly, that this is a tensor product - specifically, a tensor product between the original tensor and $n$ different instances of the differential operator $\nabla$, which makes a repeat appearance:
$$
X = \nabla \otimes \nabla \otimes ... \otimes \nabla \otimes T
$$

 In order to prove that it indeed outputs a tensor, we need $\nabla$ itself to be a tensor; why is this so?

> <span style="background-color: #ffb812; color: black;">Proposition</span>. The differential operator $\nabla$ is a tensor; it is invariant with respect to changes of basis.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

$\nabla$ is the vector operator given by
$$
\begin{bmatrix}
\frac{\partial}{\partial x_1} \\
\frac{\partial}{\partial x_2} \\
\vdots \\
\frac{\partial}{\partial x_n}
\end{bmatrix}
$$
awaiting a function to differentiate; suppose that we change basis via a matrix $R$ to an alternate set of variables $x_1', x_2', ..., x_n'$ such that, by the tensor transformation law,
$$
x_i' = R_{ij}x_j = R_{i1}x_1 + ... + R_{in}x_n
$$
leading to
$$
\frac{\partial x_i'}{\partial x_p} = 0 + ... + R_{ip} + ... + 0 = R_{ip},
$$
treating $x_j$ as a variable to be differentiated.  Similarly, we also have
$$
x_i = R_{ji}x_j' = R_{1i}x_1' + ... + R_{ni}x_n'
$$
leading to
$$
\frac{\partial x_i}{\partial x_q'} = R_{qi},\ \frac{\partial x_q}{\partial x_i'} = R_{iq}.
$$
Thus by the chain rule,
$$
(\nabla')_i = (\frac{\partial}{\partial x_i})' = \frac{\partial}{\partial x_i'} =\frac{\partial}{\partial x_q} \frac{\partial x_q}{\partial x_i'} = \frac{\partial}{\partial x_q} R_{iq} = \nabla_q R_{iq}
$$
which follows the tensor transformation law. Thus $\nabla$ is a tensor.

***

As $\nabla$ is a tensor, any rank-$2$ tensor product involving $\nabla$ can be subject to our previous antisymmetric, symmetric and traceless tensor decomposition. For instance, we may have
$$
T = \mathbf{F} \otimes \nabla,\ T_{ij} = \frac{\partial}{\partial x_j} F_i
$$
for a vector field $\mathbf{F}$; it follows that this rank-$2$ tensor can be decomposed into the isotropic component
$$
\frac{\text{Tr }T}{3}\delta_{ij} = \frac{\partial_k F_k}{3}\delta_{ij} = (\frac{\nabla \cdot \mathbf{F}}{3}) \delta_{ij}
$$
the traceless, symmetric component
$$
S_{ij} - \frac{1}{3}\nabla \cdot \mathbf{F}
$$
and the antisymmetric component
$$
\epsilon_{ijk}B_k = \epsilon_{ijk}(\frac{1}{2}\epsilon_{ijk}\nabla_i F_j) = -\frac{1}{2} \epsilon_{ijk} (\nabla \times \mathbf{F}).
$$

## Tensor integral theorems

### Invariant integrals

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **The invariance theorem.** Suppose that $T$ is a tensor defined by the integral
$$
T_{ij...k} = \int_V f(r)x_i x_j ... x_k\ dV
$$
> for some scalar function $f$, position vector $\mathbf{x}$, and **rotationally invariant** region $V$ (e.g. a sphere), where $r$ is the spherical radius $|\mathbf{x}|$; then $T$ is isotropic. 

> <span style="background-color: #1eff12; color: black;">Proof</span>. 

First, we prove that $T$ is indeed a tensor.
$T$ transforms as follows:
$$
\begin{aligned}
T'_{ij...k} = \int_V f(r)' x_i' x_j' ... x_k'\ dV'
\end{aligned}
$$
of which $f(r)'$ remains $f(r)$ as it is a scalar (and also because radius is rotationally symmetric), the $x_i$s transform like tensors because they are represented by position vectors along the coordinate axes - i.e. $x_i' = R_{il}x_l$ for some rotation matrix $R$ - and $dV$ does not transform, as a rotation does not change the magnitude of the volume component ($\det R = 1$.) Substituting gives
$$
T'_{ij...k} = \int_V f(r)R_{i'i}x_i R_{j'j}x_j ... R_{k'k}x_k\ dV = (R_{i'i}R_{j'j}...R_{k'k})T_{ij...k}
$$
which obeys the tensor transformation law.

As such, we have
$$
T'_{ij...k} = \int_V f(r)x_i' x_j' ... x_k'\ dV = T_{ij...k}
$$
because the integrand is a change of coordinates from $\mathbf{x}$ to $\mathbf{x}'$, and does not affect the value of the integral itself (in particular, the Jacobian is $\det R = 1$.). In other words, if the integrand is a tensor, it should transform like a tensor - and that means that the integrand is invariant in actual value (though not necessarily in representation) under a rotation.

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the value of a spherically symmetric integral over a single axis $x_i$ over a sphere $V$, given by the tensor
$$
T_i = \int_V \rho(r) x_i\ dV.
$$

> <span style="background-color: #1eff12; color: black;">Solution</span>. As $V$ is rotationally invariant, $T_i$ is an isotropic tensor; but all isotropic tensors of rank $1$ are zero tensors. Thus the integral is zero.

> <span style="background-color: #03cafc; color: black;">Example</span>. Find the value of a spherically symmetric integral over two axes $x_i$ and $x_j$ over a sphere $V$, given by the $2$-tensor
$$
T_{ij} = \int_V \rho(r) x_i x_j\ dV.
$$
> <span style="background-color: #1eff12; color: black;">Solution</span>. By the above results, $T_{ij}$ must be an isotropic tensor of rank $2$; the only tensor that fulfills these properties is a constant multiple of the Kronecker delta $\delta_{ij}$. Thus we have
$$
T_{ij} = \alpha \delta_{ij}
$$
> for some $\alpha \in \mathbb{R}$; as such, the trace of this tensor $T_{ii}$ is given by
$$
T_{ii} = \alpha\delta_{ii} = 3\alpha = \int_V\rho(r) x_i x_i\ dV = \int_V \rho(r)r^2\ dV
$$
> where the right-hand integral evaluates to $4\pi \int_0^R \rho(r) r^4\ dr$. This leads us to
$$
\alpha = \frac{4\pi}{3}\int_0^R \rho(r) r^4\ dr
$$
> and thus
$$
T_{ij} = (\frac{4\pi}{3}\int_0^R \rho(r) r^4\ dr)\ \delta_{ij}.
$$

### Tensor divergence theorem

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Tensor divergence theorem**. Let $T_{ij...k...l}(\mathbf{x})$ be a tensor field; define the **divergence of $T$** with respect to some index $k$ to be the sum
$$
\nabla_k \cdot T_{ij...k...l}(\mathbf{x}) = \frac{\partial}{\partial x_k}T_{ij...k...l}(\mathbf{x})
$$
> taking $k$ as the index of summation and all others as fixed. Then for a closed region $V$ in $\mathbb{R^3}$ and its boundary $S$, we have
$$
\int_V \nabla_k \cdot T_{ij...k...l}\ dV = \int_S T_{ij...k...l}\ n_k\ dS
$$
> where $\mathbf{n}$ is the normal vector to boundary $S$. (Note that the right-hand side is summed over $k$; it is in some respects analogous to $\mathbf{F \cdot n} = F_k n_k$.)

> <span style="background-color: #1eff12; color: black;">Proof</span>.

This is a consequence of the (regular) Divergence Theorem. Consider a vector field $\mathbf{v}$ formed from a contraction of the tensor $T$ with $n-1$ other constant vectors, i.e.
$$
\mathbf{v}_k = T_{ij...k...l} \mathbf{a}_i \mathbf{b}_j ... \mathbf{c}_l
$$
with $\mathbf{a, b, ..., c}$ being constant vectors. Applying the Divergence Theorem on $\mathbf{v_k}$ gives
$$
\begin{aligned}
\int_V \nabla \cdot v_k\ dV &= \int_S v_k\cdot \mathbf{dS} = \int_S v_k n_k\ dS \text{ (divergence theorem)}  \\
&= \mathbf{a_i b_j ... c_l}\int_V T_{ij...k...l}\ n_k\ dS \\ 
\end{aligned}
$$
and directly expanding $v_k$ into the above product gives
$$
\int_V \nabla \cdot v_k\ dV = \mathbf{a_i b_j ... c_l}\int_V \nabla_k \cdot T_{ij...k...l}\ dV
$$
leading to 
$$
\int_V \nabla_k \cdot T_{ij...k...l}\ dV = \int_S T_{ij...k...l}\ n_k\ dS
$$
as $\mathbf{a, b, ..., c}$ are all constant.



