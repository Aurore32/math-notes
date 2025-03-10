---
id: s4584oa4m259kma2pmw1lnq
title: Complex Vector Spaces
desc: ''
updated: 1734851058819
created: 1734683773801
nav_order: 6
---
> <span style="background-color: #03cafc; color: black;">Definition</span>. (Complex vector space) Define the complex vector space $\mathbb{C}^n$ as encompassing all vectors $(z_1,z_2,...,z_n), z_i \in C$. This vector space shares many properties with $\mathbb{R^n}$: the same standard basis, for instance. However, we will need a different definition of the scalar product because vectors such as $u=(0,i)$ will have negative norms $u\cdot u = i^2=-1$, violating the definition of a norm. <br/><br/>
Thus, we define the dot product $\mathbf{u\cdot v}$ in the complex plane as $\sum \bar{u_i} v_i$ where $\bar{u_i}$ denotes the complex conjugate. This ensures that the norm is always positive ($u\cdot u=\bar{z_1}z_1 + \bar{z_2}z_2 + ... + \bar{z_n}z_n=|z_1|+|z_2|+...+|z_n|$, which is a sum of magnitudes and thus always positive).<br/><br/>
This dot product does not satisfy $u\cdot v = v\cdot u$, but instead satisfies $u\cdot v = \bar{(v \cdot u)}$ (due to the properties of complex conjugation).

