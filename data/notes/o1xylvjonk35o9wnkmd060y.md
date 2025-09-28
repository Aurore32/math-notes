## Systems of $2\times 2$ equations
Consider a general system of linear equations in two variables $x_1$ and $x_2$:
$$
\begin{cases}
A_{11} x_1 + A_{12} x_2 = d_1 \\
A_{21} x_1 + A_{22} x_2 = d_2
\end{cases}
$$
This can be rewritten in matrix form as
$$
A\mathbf{x=d}
$$
where column vectors $\mathbf{x} = \begin{bmatrix}x_1\\x_2\end{bmatrix}$ and $\mathbf{d}=\begin{bmatrix}d_1\\d_2\end{bmatrix}$. The general solution of this system can arise from substitution, e.g. writing $x_2 = \frac{d_1-A_{11}x_1}{A_{12}}$ and substituting into the second equation:
$$
\begin{aligned}
A_{21}x_1 + A_{22}x_2 &= A_{21}x_1 + A_{22} \frac{d_1-A_{11}x_1}{A_{12}} = d_2 \\
&= (A_{21} - \frac{A_{22}A_{11}}{A_{12}})x_1 +\frac{A_{22}}{A_{12}}d_1 \\
\frac{A_{21}A_{12}-A_{11}A_{22}}{A_{12}}x_1 &= d_2 - \frac{A_{22}}{A_{12}}d_1 \\
\frac{-\det A}{A_{12}}x_1 &= \frac{A_{12}d_2 - A_{22}d_1}{A_{12}} \\
x_1 &= \frac{A_{22}d_1 - A_{12}d_2}{\det A}
\end{aligned}
$$
with $\det A = A_{22}A_{11}-A{12}A_{21}$, as previously defined. Analogously, substituting $x_1$ back into the equations gives 
$$
x_2 = \frac{- A_{21}d_1 + A_{11}d_2}{\det A}
$$
This solution is unique as long as $\det A \neq 0$. Thus, the linear system of two equations in two variables represented by $A\mathbf{x=d}$ has solution 
$$
\begin{aligned}
\mathbf{x} &= \begin{bmatrix}
\frac{A_{22}d_1 - A_{12}d_2}{\det A} \\
\frac{- A_{21}d_1 + A_{11}d_2}{\det A}
\end{bmatrix} \\
&= \frac{1}{\det A}\begin{bmatrix}
A_{22}d_1 - A_{12}d_2 \\
- A_{21}d_1 + A_{11}d_2
\end{bmatrix} \\
&= \frac{1}{\det A} \begin{bmatrix}
A_{22} &- A_{12} \\
- A_{21} & A_{11}
\end{bmatrix}\begin{bmatrix}
d_1 \\
d_2
\end{bmatrix} = \frac{1}{\det A} \begin{bmatrix}
A_{22} &- A_{12} \\
- A_{21} & A_{11}
\end{bmatrix}\mathbf{d}
\end{aligned}
$$
However, matrix algebra also gives $\mathbf{x = A^{-1}d}$. Thus we conclude that:

> <span style="background-color: #12ffd7; color: black;">Theorem</span>. The inverse of a $2 \times 2$ matrix $A$ is given generally by:
$$
A^{-1} = \frac{1}{\det A} \begin{bmatrix}
A_{22} &- A_{12} \\
- A_{21} & A_{11}
\end{bmatrix}.
$$
Note that this only makes sense if $\det A \neq 0$ (more on this later!)
## Inverse of a general $n\times n$ matrix

Recall the *Laplace expansion formulae* for determinants of an $n\times n$ matrix, $A=\{A_{ij}\}$:

$$
\det A = \sum_{j}A_{ij}\Delta_{ij} = \sum_{i}A_{ij}\Delta_{ij}
$$
Now suppose that we replace the $I$th row of $A$ with the $i$th row of $A$, $I\neq i$, such that we create a new matrix $A'$ with two identical rows (row $I$ = row $i$). Per a previously proven property, the matrix $A'$ has zero determinant as it has two identical rows; however, the cofactors $\Delta_{Ij}$ will remain unchanged as they involve the rest of the matrix aside from row $I$, which were not affected. Using row $I$ to take the determinant via the Laplace expansion formula gives
$$
\sum_{j}A'_{Ij}\Delta_{Ij}=\sum_{j}A_{ij}\Delta_{Ij}=0
$$
Swapping the $I$th column of $A$ with the $i$th column produces an identical result:
$$
\sum_{j}A'_{jI}\Delta_{jI}=\sum_{j}A_{ji}\Delta_{jI}=0
$$
Thus we have, for any $I$ and using suffix notation:
$$
\begin{cases}
A_{ji}\Delta_{jI}=0 \\
A_{ij}\Delta_{Ij}=0
\end{cases}
$$
if $i \neq I$. However, if $i = I$, nothing has been swapped and we simply have
$$
\begin{cases}
A_{ji}\Delta_{jI}=\det A \\
A_{ij}\Delta_{Ij}=\det A
\end{cases}
$$
by Laplace expansion; alternatively, using the Kronecker delta, we have
> <span style="background-color: #12ffd7; color: black;">Lemma</span>.
$$
\begin{cases}
A_{ji}\Delta_{jI}=\delta_{iI}\det A, \text{ summing over $j$} \\
A_{ij}\Delta_{Ij}=\delta_{iI}\det A, \text{ summing over $j$}
\end{cases}
$$
This leads finally to
> <span style="background-color: #12ffd7; color: black;">Theorem</span>. **General inverse for $n\times n$ matrices**. For a $n\times n$ square matrix $A$ with $\det A \neq 0$, its inverse is given by 
$$
A^{-1} = \frac{1}{\det A}\{\Delta_{ji}\} = \frac{1}{\det A} \begin{bmatrix}
\Delta_{11} & \Delta_{12} & ... & \Delta_{1n} \\
\Delta_{21} & \Delta_{22} & ... & \Delta_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
\Delta_{n1} & \Delta_{n2} & ... & \Delta_{nn}
\end{bmatrix}^T
$$
(Note the tiny little transpose there!)
> We assert that $A^{-1} A = AA^{-1} = I$.

> <span style="background-color: #1eff12; color: black;">Proof</span>.

$$
\begin{aligned}
A^{-1}A &= \frac{1}{\det A} \Delta_{ik}A_{jk} \\
&= \frac{\det A}{\det A} \delta_{ij} \text{ by the above lemma} \\
&= \delta_{ij}, \text{ matching the identity matrix} \\ \\
AA^{-1} &= \frac{1}{\det A} A_{ik}\Delta_{jk}  \\
&= \frac{\det A}{\det A} \delta_{ij} \text{ by the above lemma} \\
&= \delta_{ij}, \text{ matching the identity matrix} \\ \\
\end{aligned}
$$
> as $AA^{-1} = I$ and $A^{-1}A=I$, $A^{-1}$ is by definition the inverse of $I$. (A little on-the-nose, maybe, but it's true!)

Essentially, this tells us that taking an inverse of a $n\times n$ matrix is as easy as listening to Mozart sped up in your left ear while listening to the Chinese version of the Bible in reverse in your right: all you need to do is to form a matrix of cofactors $\Delta$ from $A$ by taking the cofactor of each term and leaving it there, then transpose it, then dividing it by $\det A$. What? What do you mean that's not easy? What do you mean we need to take a bajillion determinants and end up with something with time complexity $O(n\cdot n!)$?

(Okay, so let's take a rain check on that one for now. Moving on!)

## Solving linear equations

Buckle your seatbelts, guzzle down three twelve-packs of Red Bull, and PREPARE THYSELVES for the spectactular extravaganza that lies ahead, for I will demonstrate to you for the first time in your puny lives how to neutralize the terrifying, hellish devils the likes of which your minds have never comprehended. Dare you brave $3x+4=5$, for instance? Or - ***shudder*** - dare you penetrate the horrors of (gasp) $\frac{x}{2} + 3 = 6$? Or -

(*What? Wrong linear equations?*)

Okay, so never mind. Let's take a look at the above $2\times 2$ example of systems of linear equations, and see how we can generalize it:
$$
A\mathbf{x=d}
$$
This forms a valid system of $n$ equations in $n$ variables if $A$ is $n\times n$, $\mathbf{x}$ is $n \times 1$, and $\mathbf{d}$ is $n \times 1$. 
> <span style="background-color: #03cafc; color: black;">Definition</span>. If $\mathbf{d}$ is the zero vector, the system of equations is deemed **homogeneous**; otherwise, it is **inhomogeneous**.

As demonstrated, linear algebra leads to
$$
\mathbf{x=}A^{-1}\mathbf{d}
$$
if the system is inhomogeneous. Trying to calculate the solution vector $\mathbf{x}$ through directly calculating the inverse of $A$ would lead to a very tired hand and a thoroughly punched calculator. Exactly how punched? Consider just the step of taking $\det A$: using Laplace expansion, $\det A$ can be written as a sum of $n$ determinants of $(n-1)\times (n-1)$ matrices (cofactors of $A$), which, in turn, can each be written as a sum of $(n-1)$ determinants of $(n-2) \times (n-2)$ matrices, etc. 

In other words, if $f_n$ represents the number of operations required to calculate $\det A$, the we have
$$
f_n = n f_{n-1} + 2n - 1
$$
recursively, as an additional $n-1$ additions and $n$ multiplications must be made between the determinants. This leads to the $O(n\cdot n!)$ time-complexity mentioned above - a shudderingly-large number, one that must not be disturbed with a ten-kilometer iron pole while wearing ten hazmat suits and a blast jacket.  

That's no good. Clearly, we need:

## Gaussian elimination

We're going to throw matrices into the trash bin like the pieces of scrapyard junk they are; they're cramping our style. Instead, we're going back to treating systems of equations like systems of equations:

$$
\begin{cases}
A_{11}x_1 + A_{12}x_2 + ... + A_{1n}x_n = d_1 \\
A_{21} x_1 + A_{22} x_2 + ... + A_{2n} x_n = d_2 \\
\vdots \\
A_{m1} x_1 + A_{m2} x_2 + ... + A_{mn} x_n = d_m
\end{cases}
$$

(Note that this is a system of $m$ equations with $n$ variables, where $m$ need not equal $n$).

Really, who needs matrices when you have thirty minutes of free time and a truly messed-up fetish for writing the letter $x$?

The process is familiar. First insist that $A_{11}$, the leading coefficient, is nonzero; if it is, reorder the rows such that the first row has a nonzero leading coefficient. If that isn't possible, i.e. every row has a zero leading coefficient, ~~blow your piece of paper up with a homemade nuke~~ relabel $x_2, ..., x_n$ to $x_1, ..., x_{n-1}$ and start over.

We begin by eliminating a single variable, e.g. $x_1$. In order to erase every trace of $x_1$ from the miserable existence of this prison we call a system, we will need to subtract every other row by a certain multiple of the first row: if row 1 is denoted $(1) = A_{11}x_1 + A_{12}x_2 + ... + A_{1n}x_n = d_1$, row 2 is denoted $(2) = A_{21}x_1 + A_{22}x_2 + ... + A_{2n}x_n = d_2$ and so on, then $(2) - \frac{A_{21}}{A_{11}}(1)$ eliminates $x_1$ from $(2)$, $(3)-\frac{A_{31}}{A_{11}}(1)$ eliminates $x_1$ from $(3)$, ..., $(m)-\frac{A_{m1}}{A_{11}}(1)$ eliminates $x_1$ from $(m)$. We are thus left with the system
$$
\begin{cases}
(1), \\
(2) - \frac{A_{21}}{A_{11}}(1), \\
\vdots \\
(m) - \frac{A_{m1}}{A_{11}}(1).
\end{cases}
$$
This system does not involve $x_1$ in any equation except the first. And now we do it again; first insist that the leading coefficient of $x_2$ is nonzero (and take the necessary measures to ensure it is so), then eliminate $x_2$ from every equation below the second (the third, the fourth, etc.), and so on - where, after $x_2$ is eliminated, only the first and second equations will contain $x_2$. And so will only the first three equations contain $x_3$, the first four $x_4$, etc. etc. This leaves us with a system of the form
$$
\begin{cases}
A_{11}x_1 + A_{12}x_2 + ... + A_{1n}x_n = d_1 \\
0x_1 +A_{22}'x_2 + ... + A_{2n}'x_n = d_2' \\
0x_1 + 0x_2 + A_{33}'x_3 + ... + A_{3n}'x_n = d_3' \\
0x_1 + 0x_2 + 0x_3 + A_{44}'x_4 + ... + A_{4n}'x_n = d_4' \\
\vdots \\
0x_1 + 0x_2 + 0x_3 + ... + A_{mn}'x_m = d_m' \\
\end{cases}
$$
where $d'$ and $A'$ denote the remaining coefficients after elimination. Note that every subsequent row will have less variables than the last; thus, if a row is zero on the left-hand side, all the next rows will be zero as well. There are now three possible cases for the system.
1. **The overdetermined case**. If there exists an $r < n$ such that the left-hand side of equation $(r)$ is zero and the right-hand side $d_r' \neq 0$, then the system is *inconsistent* and there are no solutions.
2. **Unique solution**. If there only exists an $r = n+1$ such that the left-hand side of equation $(r)$ is zero (i.e. the previous $n$ equations are nonzero, and only from the $n+1$th equation onwards are the equations zero), and none of $d'_{n+1}, ..., d'_{m}$ are zero, then there is a unique solution that can be found by taking the value of $x_n$ and substituting into equation $(n-1)$, then taking $x_{n-1}$ and substituting into $(n-2)$, etc.
3. **Infinite solutions**. If there exists an $r<n$ such that the left-hand side of equation $(r)$ is zero and all of $d'_r, d'_{r+1}, ..., d'_m$ are zero, then there are no inconsistencies in the system, but there aren't enough equations to uniquely determine a single solution.

> <span style="background-color: #ffb812; color: black;">Remarks</span>.
1. It can be convenient to reorder the equations such that $A_{11}$ has the maximum absolute value of $(A_{11},A_{21},...,A_{n1})$.
2. Gaussian elimination can be achieved in $O(n^3)$ - much more feasible than finding matrix inverses; however, algorithms also exist to find determinants, and thus inverses, in $O(n^3)$ (which are based on Gaussian elimination).
3. A linear system is consistent if it has at least one solution, and inconsistent if it has none.
4. The above Gaussian elimination algorithm involves the following **elementary row operations**:
    - Swapping two rows
    - Adding a constant multiple of one row to another
    - Multiplying a row by a scalar constant
5. Two systems of linear equations are row-equivalent if they can each be obtained from elementary row operations of the other; these systems have the same solutions. 
6. Swapping two rows and adding a constant multiple of one row to another, alongside swapping two columns, change the determinant of the system's associated matrix by only a sign (as previously shown). Thus, performing Gaussian elimination on a matrix and transforming it into

$$
A' = \begin{bmatrix}
A_{11} & A_{12} & A_{13} & ... & A_{1n} \\
0 & A'_{22} & A'_{23} & ... & A'_{2n} \\
0 & 0 & A'_{33} & ... & A'_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & ... & A'_{nn}
\end{bmatrix}
$$
> with $\det A' = (-1)^k \det A$ where $k$ is the number of column and row swaps performed, leads to $\det A' = A_{11}A'_{22}A'_{33}...A'_{nn}$ (using the first column for Laplace expansion). As Gaussian elimination can be achieved in $O(n^3)$, the determinant can also be found in $O(n^3)$ (as what remains is simply a multiplication of the diagonal elements).