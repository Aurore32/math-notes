---
id: g3saar7em9n8mr1cgmrackv
title: Determinants
desc: ''
updated: 1736072984576
created: 1735574071094
nav_order: 6
---
## Alternative names for determinants
- The Black Death
- It That Lurks In The Darkness
- Satan's Hemmorhoids
- The Antichrist in Human Clothing 
> This post was made by the #SheldonAxler gang. Let not the evil influences of these unholy idols defile the sanctity of your linear algebra studies; do linear algebra right, stay strong, and stay ~~determined~~ - wait, no, sorry, I didn't mean to -

## Determinants: An Extermination Guide for the Home

Consider the linear map $A$ mapping the standard basis $\{\mathbf{e_1, e_2, e_3}\} = \{(1,0,0),(0,1,0),(0,0,1)\}$ in $\mathbb{R}^3$ to $A\mathbf{e_1}, A\mathbf{e_2}, A\mathbf{e_3}$. The original solid willed into existence by these basis vectors is a unit cube, volume 1; what will be the volume of the new solid formed under the wicked distortions of the almighty $A$?

The new solid under transformation will be a parallelpiped, enclosed by $A\mathbf{e_1}, A\mathbf{e_2}, A\mathbf{e_3}$; a result from several lifetimes ago tells us that the volume of such a parallel pipi is given by the scalar triple product $A\mathbf{e_1} \cdot (A\mathbf{e_2} \times A\mathbf{e_3})$. This, in turn, can be expanded in suffix notation as
$$
\begin{aligned}
A\mathbf{e_1} \cdot (A\mathbf{e_2} \times A\mathbf{e_3}) &= \epsilon_{ijk} (Ae_1)_i (Ae_2)_j (Ae_3)_k \\
&= \epsilon_{ijk}A_{ia}(e_1)_{a}A_{jb}(e_2)_{b}A_{kc}(e_3)_{c} \\
&= \epsilon_{ijk}A_{ia}\delta_{1a}A_{jb}\delta_{2b}A_{kc}\delta_{3c} \\
&\text{(as $e_1=(1,0,0), e_2=(0,1,0), e_3=(0,0,1)$)} \\
&= \epsilon_{ijk}A_{i1}A_{j2}A_{k3}
\end{aligned}
$$
> <span style="background-color: #03cafc; color: black;">Definition</span>. Define the **determinant** of a $3\times 3$ matrix $A$ to equal the above expression. As shown, it is also equal to the (signed) volume of a parallelpiped produced under transformation of a unit cube by the linear map $A$. 

> <span style="background-color: #bc42f5; color: black;">Notation</span>. Denote the determinant by $|A|$, $\det A$, "The Black Hand", or simply "The Darkness Which Prowls The Night".

> <span style="background-color: #ffb812; color: black;">Properties</span>.
1. A linear map $A$ preserves the volume of a solid if and only if its determinant is $\pm 1$.
2. If $\{e_i\}$ is a set of orthonormal vectors in the right-handed sense, then the set of vectors it transforms to is right-handed if $\det A > 0$ and left-handed if $\det A < 0$.
3. The cross-product $\mathbf{a} \times \mathbf{b}$ can be written in determinant form as 
$$
\begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k}\\
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3
\end{vmatrix}
$$
> Warning: the unironic usage of this formula in any context is a sign of clinical psychopathy.

## Determinants and their demonic offspring

A matrix in $\mathbb{R}^3$ is effectively a $2\times 2$ matrix acting in $\mathbb{R}^2$ if it looks something like this:
$$
A = \begin{bmatrix}
... & ... & 0 \\
... & ... & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
In effect, it changes only the $x$- and $y$-components and does nothing to the $z$-component; it enlarges bodies across the horizontal axes and makes them chunkier, but it fails to affect their height. It may horrify you to know that I was subjected to nearly ten years of transformation under $A$ during my teenage years.

For such a matrix, we recall the above definition of the determinant 
$\det A = \epsilon_{ijk}A_{i1}A_{j2}A_{k3} = \epsilon_{ij3}A_{i1}A_{j2}$ as $A_{k3}$ is only nonzero with $k=3$. This leads simply to 
$$
\det A = \epsilon_{123}A_{11}A_{22} + \epsilon_{213}A_{21}A_{12} = A_{11}A_{22}-A_{21}A_{12}
$$
as any terms $A_{31}, A_{32}$ etc. are zero. For a $2 \times 2$ matrix
$$
\begin{bmatrix}
A_{11} & A_{12} \\
A_{21} & A_{22}
\end{bmatrix}
$$
this is simply the product of terms on one diagonal minus the product of terms on the other.

> <span style="background-color: #bc42f5; color: black;">Observation</span>. Harvesting this demonic offspring of the $3\times 3$ determinant allows us to rewrite the $3\times 3$ determinant more clearly as
$$
\det A = A_{11}\begin{vmatrix}
A_{22} & A_{23} \\
A_{32} & A_{33}
\end{vmatrix} -
A_{21}\begin{vmatrix}
A_{12} & A_{13} \\
A_{32} & A_{33}
\end{vmatrix}
+
A_{31}\begin{vmatrix}
A_{12} & A_{13} \\
A_{22} & A_{23}
\end{vmatrix}
$$
> noting the sign pattern.


