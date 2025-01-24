---
id: 1cdknz7rz4s37vg3bf9e6zc
title: Examples of Linear Maps
desc: ''
updated: 1735375596058
created: 1735372205306
nav_order: 4
---
## Examples of matrices as linear maps

1. **Rotation** by $\theta$ about $z$-axis in $\mathbb{R}^3$ ($z$-coordinate fixed):
$$
R=\begin{bmatrix}
\cos \theta & -\sin \theta & 0 \\
\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
2. **Stretch** by a factor of $\lambda$, $\mu$, $\nu$ in the $x$-, $y$- and $z$-axis respectively:
$$
S = \begin{bmatrix}
\lambda & 0 & 0 \\
0 & \mu & 0 \\
0 & 0 & \nu
\end{bmatrix}
$$
3. **Reflection **in the plane $\mathbf{x \cdot n} = 0$ in $\mathbb{R}^3$, where $\mathbf{n}$ is a unit normal vector. Suppose we are reflecting a point with position vector $\mathbf{p} = \vec{OP}$ about the plane. Then its image after reflection, $P'$, is connected to $P$ by two times the normal vector from $P$ to the plane. Call the foot of this normal $N$. Then:
$$
\vec{OP'} = \vec{OP} + \vec{PN} + \vec{NP'} = \vec{OP} - 2 \vec{NP}
$$
which equals
$$
\mathbf{p} - 2\vec{NP}
$$
where $\vec{NP}$ is $(\mathbf{p\cdot n})\mathbf{n}$.
> <span style="background-color: #1eff12; color: black;">Proof</span>. $\vec{NP}$ must be parallel to $\mathbf{n}$ as it is normal to the plane; suppose it is equal to $d\mathbf{n}$ for some scalar $d$. Then as $N$ lies on the plane, we have $\vec{ON} = \vec{OP} - \vec{NP} = \mathbf{p} - d\mathbf{n}$ and $\vec{ON}\cdot \mathbf{n} = 0$ by the equation of the plane. Thus $(\mathbf{p}-d\mathbf{n})\cdot \mathbf{n} = 0$, yielding $d = \mathbf{p \cdot n}$.<br/><br/>
Using suffix notation, $\mathbf{p} - 2(\mathbf{p\cdot n})\mathbf{n}$ can be expanded as follows:
$$
\begin{aligned}
\mathbf{p} - 2(\mathbf{p\cdot n})\mathbf{n} &= p_{i} - 2(p_jn_j)n_i \\
&= \delta_{ij}p_j - 2(p_jn_j)n_i \\
&= p_j(\delta_{ij}-2n_jn_i) \\
&= \mathbf{p}'
\end{aligned} 
$$
> Note the trick of using $\delta_{ij}$ to transform the suffix $i$ into $j$!
>
Therefore, the matrix representing a transformation from $\mathbf{p}$ to $\mathbf{p}'$, its reflection about a plane with normal vector $\mathbf{n}$, can be expressed by
$$
R = \{
\delta_{ij} - 2n_j n_i
\}.
$$

4. **Shear** in any axis (e.g. the $x$-axis) in $\mathbb{R}^3$. A shear is any transformation that transforms a vector $(x,y,z)$ onto, for instance, $(x+\lambda y, y, z)$, preserving the two other coordinates while adding a scalar multiple of another coordinate onto one coordinate. This can be simply expressed as
$$
S = \begin{bmatrix}
1 & \lambda & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$