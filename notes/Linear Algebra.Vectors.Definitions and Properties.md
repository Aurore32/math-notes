---
id: cijw6w7tpvzehpgzd9u59gf
title: Definitions and Properties
desc: ''
updated: 1734665930788
created: 1734665589401
---
> <span style="background-color: #03cafc; color: black;">Definition</span> (Vector space). A *vector space* $V$ over $\mathbb{R}$ or $\mathbb{C}$ is a collection of entities ("vectors") $\mathbf{v} \in V$, in which we define two operations: addition of two vectors and scalar multiplication with a vector.

These "vectors" (notice that I am stubbornly using quotation marks here like a conspiracy theorist who believes that Big Archimedes fabricated vectors to steal your money, because technically, we aren't supposed to know what vectors are yet; we're defining them here) must satisfy the following properties under addition and scalar multiplication:

### Addition
1. Commutativity: $\mathbf{a + b = b + a}$
2. Associativity (order does not change result): $\mathbf{(a+b)+c=a+(b+c)}$
3. Identity: there is a vector $\mathbf{0}$ such that $\mathbf{a+0=a}$.
4. Existence of inverses: for all vectors $\mathbf{a}$, there exists another vector in $V$ which we denote $-\mathbf{a}$ such that $\mathbf{a+(-a)=0}$.

### Scalar Multiplication
Here $\lambda, \mu$ denote scalars and all bolded letters represent vectors.
1. Scalar distributive property: $\lambda\mathbf{(a+b)}=\lambda\mathbf{a}+\lambda\mathbf{b}$.
2. Vector distributive property: $\mathbf{a}(\lambda+\mu)=\mathbf{a}\lambda+\mathbf{a}\mu$
3. Associativity: $\lambda(\mu\mathbf{a})=\mu(\mathbf{a}\lambda)$
4. Identity: $1\mathbf{a}=\mathbf{a}$.

It is implicitly stated that the sum of two "vectors" in $V$ (suspicious name, that) will be another "vector" (also in $V$), and the scalar multiplication of a vector will give another vector; thus we can say that vector spaces are *closed* under addition and scalar multiplication; that is, these two operations map elements of $V$ to $V$.

Notice also that vectors (as we understand them; the matrix kind) of any size will all satisfy these properties, whether they have two or three or ten entries; in fact, vectors with a single entry - which are just scalars - also satisfy these properties. Thus, any $\mathbb{R}^n$ - the set of $n$-tuples of real numbers - are vector spaces; all lines through the origins are vector spaces (as in, all points on these lines), but lines not through the origin are not - they do not contain (0,0), the zero vector.


The geometric meaning of vectors, of course, are more familiar to us: objects $\mathbf{v}$ with a length denoted $|\mathbf{v}|$, and a direction which remains unchanged under scalar multiplication (either parallel or antiparallel).

> <span style="background-color: #03cafc; color: black;">Definition</span> (Unit vector). A unit vector, usually denoted with a little hat like this - $\mathbf{\hat{v}}$ - is a vector with length 1.


