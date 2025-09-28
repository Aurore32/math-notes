## What are multilinear maps?

Sometimes you flip to a new chapter in your math textbook, stare at it, get angry, and then when the overwhelming tidal wave of rage and devastation finally recedes from your body all that's left is for you to wonder "why?" Why did people look at this:
$$
\int
$$
and think to themselves, "you know what I want? Two $\int$s. **THREE** $\int$s. Throw a $\oint$ hula-hoop around it for good measure." 

These people are exactly the type of people who look at linear maps, and go, "I bet I can make this even more torturous and deranged." Thanks for nothing, Ricci-Curbastro and Levi-Civita; may your flaming purgatory in the bowels of hell last as long as both of your names combined.

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **multilinear map** $f$ is an extension of linear maps to a domain of multiple vectors at once: it maps $n$ vectors $\mathbf{v_1, ..., v_n}$, each belonging to (potentially distinct) vector spaces $V_1, V_2, ..., V_n$, to a vector $\mathbf{w}$ in vector space $W$. Denote this as $f(\mathbf{v_1, ..., v_n}) = \mathbf{w}, f: V_1 \times V_2 \times ... \times V_n \to W$.

The "multi" part of "multilinear" comes from the fact that $f$ has linearity in each of the $n$ variables it accepts as its input. A regular linear map $A(\mathbf{x})$ is linear because it satisfies the following condition:
$$
A(\lambda \mathbf{x} + \mu \mathbf{y}) = \lambda A(\mathbf{x}) + \mu A(\mathbf{y})
$$
Analogously, for a multilinear map this linearity condition holds for each of $\mathbf{v_1}, ..., \mathbf{v_n}$:
$$
\begin{aligned}
f(\mathbf{v_1, ..., \lambda v_i + \mu u_i, ..., v_n}) \\
= \lambda f(\mathbf{v_1, ..., v_i, ... v_n}) + \mu f(\mathbf{v_1, ..., u_i, ..., v_n})
\end{aligned}
$$
for **every one of** $i = 1, ..., n$. For instance, a **bi-linear map** $f: U \times V \to W$ for vector spaces $U, V, W$ has the property that, for four vectors $\mathbf{a, b, c, d}$,
$$
\begin{aligned}
f(\alpha \mathbf{a} + \beta \mathbf{b}, \gamma \mathbf{c} + \delta \mathbf{d}) &= \alpha f(\mathbf{a}, \gamma \mathbf{c} + \delta \mathbf{d}) + \beta f(\mathbf{b}, \gamma \mathbf{c} + \delta \mathbf{d}) \\
(&= \alpha\gamma(f(\mathbf{a}, \mathbf{c}) + ...))
\end{aligned}
$$



This gives us the tools to construct a **coordinate-independent** definition of tensors, based on multilinear maps. Let's start small with a familiar example - a rank $2$ tensor, more affectionately known as a matrix (representation of a linear map) - and extrapolate from there. We know that such "tensors" - matrices - are linear maps which take a single vector $\mathbf{x}$ and map it to another vector $\mathbf{x}'$:
$$
\mathbf{x}'_i = A_{ij}\mathbf{x}_j \text{ (summation notation)}
$$  
This suggests to us the generalization
$$
\mathbf{x}'_i = T_{i i_1 ... i_{p-1}}\mathbf{x}^1_{i_1} \mathbf{x}^2_{i_2} ... \mathbf{x}^{p-1}_{i_{p-1}}
$$
for a tensor of rank $p$, taking $n$ vectors $\mathbf{x}^1, \mathbf{x}^2, ..., \mathbf{x}^n$ to return a single vector $\mathbf{x}'$. Alternatively, multiplying both sides by $\mathbf{x_i}'$
$$
(\mathbf{x}'_i)^2 = T_{i i_1 ... i_{p-1}}\mathbf{x}'_i\mathbf{x}^1_{i_1} \mathbf{x}^2_{i_2} ... \mathbf{x}^{p-1}_{i_{p-1}}
$$
results in a map from $p$ vectors to a real number.

 
> <span style="background-color: #03cafc; color: black;">Definition</span>. A tensor $T_{i_1 i_2 ... i_p}$ of rank $p$ can be defined as a multilinear map $T: V_1 \times V_2 \times ... \times V_n \to V$ on $n$ vectors, denoted $\mathbf{x}^1, \mathbf{x}^2, ..., \mathbf{x}^n$, which outputs a vector $\mathbf{x}'$ with components

$$
\mathbf{x}'_i = T_{i i_1 ... i_{p-1}}\mathbf{x}^1_{i_1} \mathbf{x}^2_{i_2} ... \mathbf{x}^{p-1}_{i_{p-1}}. \text{ (summation over each index)}
$$

> or, equivalently,
$$
x = T_{i_1 i_2 ... i_{p}}\mathbf{x}^1_{i_1} \mathbf{x}^2_{i_2} ... \mathbf{x}^{p}_{i_{p}}
$$
> which maps $p$ vectors $\mathbf{x_1, ..., x_p}$ to a real number $x$.


We note that the $n+1$ vector spaces $V_1, ... V_n$ and finally $V$ **need not be** the same vector space; as such, just as linear maps can spit out a vector from $\mathbb{R^m}$ when you throw in a vector from $\mathbb{R^n}$ if it has dimensions $m \times n$, tensors can also have non-symmetrical dimensions. We focus on "square" (or cube, or hypercube, etc.; I don't exactly know the fifth-dimensional lingo the Generation $\Omega$ hyperkids are using today) tensors for now.

In order to show that this is indeed equivalent to the previous definition of a tensor we have given, we proceed towards showing that 1) multilinear maps are independent of basis, and 2) multilinear maps transform like tensors. This necessitates the introduction of some new (and improved) tensor operators, so buckle up!

## Tensor operations

> <span style="background-color: #ffb812; color: black;">Proposition</span>. Preservation of the tensor transformation law.

There is one commonality that unites all the following tensor operations: ~~they all suck~~ given two tensors $S$ and $T$, they will all output another tensor, be it $S + T$ (addition), $S \otimes T$ (~~lamps in an electric circuit~~ tensor multiplication), or anything of the like - meaning that it preserves the tensor transformation law.

### Linear operations on tensors

> <span style="background-color: #03cafc; color: black;">Definition</span>. Linear operations on two tensors $S$ and $T$ - i.e. addition, subtraction, and scalar multiplication by a scalar $\alpha$ - are defined as long as $S$ and $T$ are of the same rank to be carried out component-by-component, i.e.
$$
(\alpha S + \beta T)_{i_1 i_2 ... i_p} = \alpha S_{i_1 ... i_p} + \beta T_{i_1 ... i_p}.
$$

It's not difficult to show that this is still a tensor: under an orthogonal transformation matrix $R$, we have
$$
\begin{aligned}
(\alpha S + \beta T)'_{i_1 ... i_p} &= \alpha S'_{i_1 ... i_p} + \beta T'_{i_1 ... i_p} \\
&= \alpha S_{j_1 ... j_p} R_{i_1 j_1} R_{ i_2 j_2} ... R_{i_p j_p} + \beta T_{j_1 ... j_p} R_{i_1 j_1 } R_{i_2 j_2} ... R_{i_p j_p} \\
&= (\alpha S + \beta T)_{j_1 ... j_p}R_{i_1 j_1 } R_{i_2 j_2} ... R_{i_p j_p} \\
\end{aligned}
$$
which is indeed how a tensor is transformed by definition.

### Tensor multiplication

> <span style="background-color: #03cafc; color: black;">Definition</span>. Given two tensors $S$ and $T$ of ranks $p$ and $q$ respectively, define the **tensor product** $S \otimes T$ outputting a tensor of rank $p + q$ on a component-by-component basis as
$$
(S\otimes T)_{i_1 i_2 ... i_p j_1 ... j_q} = S_{i_1 i_2 ... i_p} T_{j_1 ... j_q}
$$

We make the important clarification that this **is** defined for tensors which aren't of the same "dimensions" (e.g. a $2\times 2$ rank-$2$ tensor and a $1\times 3$ rank-$1$ tensor).

This is **not** matrix multiplication, or the dot product, or anything we've seen before as we know it; it's something entirely new, defined between **any** two tensors. When we're just dealing with vectors and matrices, it's actually not all that hard to visualize. Consider the tensor product between
$$
\ S = \begin{bmatrix}
4 \\
2 \\
0
\end{bmatrix},\ T = \begin{bmatrix}
6 & 9 & 4 \\
2 & 0 & 6 \\
9 & 4 & 2
\end{bmatrix}
$$
where 
$$
(S\otimes T)_{1 i j}= S_1 T_{ij} = 4T_{ij}
$$
and as such $(S\otimes T)_{1ij}$ is the matrix $4T$, $(S\otimes T)_{2ij}$ is $2T$, and $(S\otimes T)_{3ij}$ is $0T$. The tensor product can thus be thought of as taking a tensor $T$ (in this case, a matrix), layering $3$ copies of it into a new dimension, then multiplying each copy by $4$, $2$ and $0$ (or with the elements of another vector). 

As such, for a vector ($1$-tensor) with $3$ rows and a matrix ($2$-tensor) with dimensions $3\times 3$, the tensor product results in a $3\times 3 \times 3$ $3$-tensor; the dimensions add on top of each other, as does the rank. 

In addition, we provide a 

> <span style="background-color: #1eff12; color: black;">Proof</span> that the tensor product obeys the tensor transformation law.

Under a transformation matrix $R$:
$$
\begin{aligned}
(S\otimes T)'_{i_1 i_2 ... i_p j_1 ... j_q} &= (S_{i_1 i_2 ... i_p})' (T_{j_1 j_2 ... j_q})' \\
&= S_{k_1 k_2 ... k_p} R_{i_1 k_1} R_{i_2 k_2} ... R_{i_p k_p} T_{l_1 l_2 ... l_q} R_{j_1 l_1} R_{j_2 l_2} ... R_{j_q l_q}\\ 
&= S_{k_1... k_p}T_{l_1...l_q} R_{i_1 k_1} ... R_{i_p k_p} R_{j_1 l_1} ... R_{j_q l_q} \\
&= (S\otimes T)_{k_1 k_2 ... k_p l_1 ... l_q}R_{i_1 k_1} ... R_{i_p k_p} R_{j_1 l_1} ... R_{j_q l_q}
\end{aligned}

$$
which obeys the tensor transformation law.

> <span style="background-color: #03cafc; color: black;">Example</span>: for $n$ vectors $\mathbf{x_1, x_2, ..., x_n}$, an $n$-tensor can be constructed from the tensor product $\mathbf{x_1 \otimes x_2 \otimes ... \otimes x_n}$, defined through
$$
(\mathbf{x_1 \otimes x_2 \otimes ... \otimes x_n})_{i_1 ... i_n} = (\mathbf{x_1}_{i_1}) ... (\mathbf{x_n})_{i_n}.
$$

### Tensor contraction

> <span style="background-color: #03cafc; color: black;">Definition</span>. Let $T$ be the $n$-tensor with components denoted $T_{i j p... q}$. Define a **contraction** over the pair of indices $i$, $j$ (which can be chosen arbitrarily as any pair of indices) as the tensor $S$ with components
$$
S_{p ... q} = \delta_{ij} T_{ij p ... q}\text{ (denoting summation over $i$ and $j$!)}
$$
Fully written out, this is 
$$
S_{p...q} = T_{11 p... q} + T_{22 p... q} + ... + T_{nn p... q}
$$
which eagle-eyed readers will notice is a generalization of the trace of a matrix, now understood as a contraction of a $2$-tensor:
$$
S = T_{11} + ... + T_{nn}.
$$
This is, as always, still a valid tensor due to it being a sum of tensors.

### Symmetric and anti-symmetric matrices

> <span style="background-color: #03cafc; color: black;">Definition</span>. A $n$-tensor $T_{ijp ...q}$ is **symmetric** about a pair of indices $i$ and $j$, again arbitrarily chosen, if $T_{ijp...q} = T_{jip...q}$ (swapping the indices); call $T$ **anti-symmetric** about the same pair of indices if instead $T_{ijp...q} = -T_{jip...q}$. 

If a tensor is symmetric (or anti-symmetric) in **all** possible pairs of indices, call it **totally** symmetric (or anti-symmetric).

> <span style="background-color: #ffb812; color: black;">Proposition</span>. In $\mathbb{R^3}$, there are no nonzero rank-$4$ or higher tensors that are totally anti-symmetric. 

> <span style="background-color: #1eff12; color: black;">Proof</span>.

Suppose for the sake of contradiction that $T_{i_1 i_2 ... i_p}$ is an anti-symmetric rank-$p$ tensor in $\mathbb{R^3}$, with $p > 3$ and $i_j = 1, 2, 3$ for all $j = 1, 2, ..., p$. By the Pigeonhole Principle, we have $3$ numbers ($1, 2, 3$) and $p$ boxes to fit them into with $p > 3$; sooner or later there will be a repeated index. 

Without loss of generality, let $i_j = i_k$. Thus
$$
T_{i_j i_k ... i_p} = T_{i_k i_j ... i_p}
$$
by $i_j = i_k$, and
$$
T_{i_j i_k ... i_p} = -T_{i_k i_j ... i_p}
$$
by antisymmetry, leading to 
$$
T_{i_j i_k... i_p} = 0.
$$
This is valid for **any** component of $T$, as by the Pigeonhole Principle (stated above) all components of $T$ will have at least one repeated index. Thus, all totally anti-symmetric tensors of rank $4$ or higher in $\mathbb{R^3}$ are zero tensors. 

> Note that this proof can be extended naturally to rank-$p$ or higher tensors in $\mathbb{R^n}$ with $p > n$.

***

Armed with all of this, we return to

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. Tensors are multilinear maps: every multilinear map taking $n$ vectors in $\mathbb{R^3}$ (or some other space) and outputting a real number can be represented by a tensor, and every tensor corresponds to a multilinear map which is invariant under change of basis (by definition of multilinear maps).

> <span style="background-color: #1eff12; color: black;">Proof</span>.

As multilinear maps from the combined space of $n$ vectors to the reals are simply linear combinations of the components of these $n$ vectors, say $\mathbf{x^1, ..., x^n}$, any multilinear map $f$ of this form can be expressed as 
$$
f(\mathbf{x^1, ..., x^n}) = \sum_{i_1}\sum_{i_2}...\sum_{i_n}T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n}
$$
which is the most general form, because it is an arbitrary linear combination of every possible product of the components of these $n$ vectors. Written in summation notation, this is identical to the definition of tensors as multilinear maps provided above.

The object $T_{i_1 ... i_n}$ transforms like a tensor because the entire multilinear map is independent of basis, by definition:

$$
T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n} = (T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n})'
$$
in an alternative basis marked by transformation matrix $R$, leading to
$$
\begin{aligned}
T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n} &= (T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n})' \\
T_{i_1 ... i_n}\mathbf{x^1}_{i_1} ... \mathbf{x^n}_{i_n} &= T_{j_1 ... j_n}'\mathbf{x^1}_{j_1}' ... \mathbf{x^n}_{j_n}' \\
\end{aligned}
$$
switching indices from $i$ to $j$ on the right-hand side.
We know that $R_{j_k i_k}\mathbf{x}^k_{i_k} = (\mathbf{x}^k_{j_k})'$ by tensor transformation laws, so multiplying by $R_{j_1 i_1} R_{j_2 i_2} ... R_{j_n i_n}$ on the left-hand side gives
$$
\begin{aligned}
T_{i_1 ... i_n}(R_{j_1 i_1}\mathbf{x^1}_{i_1}) ... (R_{j_n i_n}\mathbf{x^n}_{i_n}) &= T_{j_1 ... j_n}'\mathbf{x^1}_{j_1}' ... \mathbf{x^n}_{j_n}' (R_{j_1 i_1} R_{j_2 i_2} ... R_{j_n i_n})\\
T_{i_1 ... i_n}(\mathbf{x}^1_{j_1})' ... (\mathbf{x}^n_{j_n}) &= T_{j_1 ... j_n}'(\mathbf{x^1}_{j_1}') ... (\mathbf{x^n}_{j_n}') (R_{j_1 i_1} R_{j_2 i_2} ... R_{j_n i_n})
\end{aligned}
$$
Eliminating the $\mathbf{x}'$ terms from both sides gives
$$
T_{i_1 ... i_n} = T_{j_1 ... j_n}'(R_{j_1 i_1} R_{j_2 i_2} ... R_{j_n i_n})
$$
which obeys the tensor transformation law.


## Contracting products and the quotient rule

Let's finish with two last comments on tensor products. 

### Contracting a product

Given two tensors $S$ and $T$ of ranks $p$ and $q$ respectively, it's occasionally useful to apply a contraction to the tensor product $S \otimes T$, i.e. $(S \otimes T)_{\text{contracted}}$ has components
$$
\delta_{ij}S_{ik_1 ... k_{p-1}}T_{jl_1 ... l_{q-1}} = S_{ik_1 ...k_{p-1}}T_{i l_1 ...l_{q-1}}
$$
which, when both tensors are vectors, wears a familiar guise:
$$
(S \otimes T)_{\text{contracted}} = S_{i} T_i = S \cdot T
$$
resulting in a $0$-tensor, otherwise known as a number.

Tensor contraction is a little bit like tensor division. Consider the tensor product between $S$ of rank $(m+n)$ and $T$ of rank $n$, with components
$$
S_{i_1 i_2 ... i_m j_1 j_2 ... j_n}T_{j_1 j_2 ... j_n}
$$
which has $n$ free indices $i_1, ..., i_m$ and is summed over $j_1, ..., j_n$; this results in a tensor of rank $m+n - n = m$, still obeying the tensor transformation law. This leads naturally to

### Tensor quotients

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **Tensor quotient rule.** Suppose that for an indexed array (just a list of numbers; not necessarily a tensor) $T$ with $n+m$ free indices, and **all** tensors $S$ of rank $m$, the product contraction between $S$ and $T$ satisfies
$$
T_{i_1 i_2 ... i_n j_1 ... j_m} S_{j_1 ... j_m} = V_{i_1 i_2 ... i_n}

$$
> where $V$ is a tensor of rank $n$; then $T$ is a tensor. If $n = m = 1$, this says that $T$ (a rank-$2$ array, or a matrix/a linear map) mapping a $1$-tensor to another $1$-tensor (two vectors) is a tensor.
 
> <span style="background-color: #1eff12; color: black;">Proof</span>. 

Begin by decomposing $S$ into a sum of tensor products of vectors in the form $a_{j_1}...b_{j_m}$. (Such sums can always be found for every tensor because the space of tensors of rank $p$ is equivalent to the product of $p$ vector spaces, all of which are spanned by some basis.) As tensors are additive, we only need to consider the singular term $a_{j_1}...b_{j_m}$ and thus the equation
$$
T_{i_1 i_2 ... i_n j_1 ... j_m}a_{j_1}...b_{j_m} = V_{i_1 i_2 ... i_n}.
$$
Multiplying both sides by another $n$ tensors $c_{i_1} ... d_{i_n}$ gives
$$
(c_{i_1} ... d_{i_n})T_{i_1 i_2 ... i_n j_1 ... j_m}a_{j_1}...b_{j_m} =  (c_{i_1} ... d_{i_n})V_{i_1 i_2 ... i_n}
$$
where the right-hand side is a scalar. By definition, $T$ is thus a multi-linear map as it maps $n+m$ vectors $a, ... b, c, ..., d$ to a scalar; as such, it is a tensor. $\square$