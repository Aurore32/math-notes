> Evil Riemann: my infinite sums actually never equal zero.

Riemann was the first to rigorously define the concept of integration. His only venture into number theory blossomed into one of the most consequential unsolved problems ever to grace the field. And yet, for all his wisdom, he could not even anticipate the simplest flaw in the postulation of the hypothesis that now bears his name:

![alt text](./assets/images/image-14.png)

Suffice it to say, Riemann was a fool and someone is now a million dollars richer.

This launches us straight into

### Partitions and Riemann Sums

> <span style="background-color: #03cafc; color: black;">Definition</span>. To rigorously define the notion of (one type of) an integral, we begin with **partitions**. A **partition** $D$ of an interval $[t_a, t_b]$ is given by the finite set of $n$ points
$$
t_a = t_0 < t_1 < t_2 < ... < t_n < t_b
$$
> with its corresponding modulus, denoted $|D|$, representing the longest sub-interval of the partition:
$$
|D| = \max_{i = 1, 2, ..., n}|t_{i} - t_{i-1}|
$$

Given this, we now define

> <span style="background-color: #03cafc; color: black;">Definition</span>. **Riemann sums** over a partition $D$, for a bounded function $f$, denoted $\sigma(D, \zeta)$. If $D$ is as above, then 
$$
\sigma(D,\zeta) = \sum_{i=1}^{n} f(\zeta_i)(t_i - i_{i-1})
$$
> for **any** $t_{i-1} < \zeta_i < t_i$, meaning that for a given partition the Riemann sum is non-unique. 

Suppose that the sub-intervals are the same length $h = \frac{t_n - t_0}{n}$, with $t_j = a + j h$. If we take $\sigma_i = t_i$, we obtain the unique Riemann sum
$$
\sigma(D) = \sum_{i=1}^nf(t_i)h.
$$


~~The above expression is a succinct and poignant summary of Riemann's tragic life in mathematical form. Riemann had a lifelong fascination with the Greek letter zeta, indicated through both the above use of $\zeta$ and its use in the zeta function; an unconscious reflection of his status as the world's first zeta male. However, the use of $\sigma$ - both lowercas and uppercase, and twice too - in the above expression demonstrates his unfilfilled yet ever-present yearning towards becoming sigma. Unfortunately, it was not to be as he died of LBS (little baby syndrome) when he was 39~~

### Integrals and Integrability

> Supposedly Jane Austen's last novel, posthumously published after such works as "Sense and Sensibility", "Pride and Prejudice", "Differentials and Differentiability", etc., etc.

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **bounded function** $f:\mathbb{R \to R}$ (finite at every point) is **integrable** if the above Riemann sum reaches a limit when the modulus of $D$ tends to zero:
$$
\lim_{|D| \to 0}\sigma(D, \zeta) = I
$$
i.e. when the sub-divisions made by the partition $D$ become infinitely small - independently of the choice of $\zeta$ within the intervals, and the partition $D$ used. As such, it is insufficient for the partition yielding sub-intervals of the same length to converge; **all** partitions must converge, and the value they converge to is called

> <span style="background-color: #03cafc; color: black;">Definition</span>. The **Riemann definite integral** of $f$ over the interval $[t_a, t_b]$ is denoted
$$
\int_{t_a}^{t_b} f(t)\ dt
$$
> and equals the above limit $I$.

Integrals should be thought of as the limiting value of a sum, **not** the area under a curve. Integrals should be thought of as the limiting value of a sum, **not** the area under a curve. And just in case you've forgotten, integrals should be thought of as the limiting value of a sum, **not** the area under a curve.

As always, we have

> <span style="background-color: #12ffd7; color: black;">Theorem</span> **Fundamental Theorem(s) of Calculus**. 

$$
\frac{d}{dx} \int_{t}^{x} f(t)\ dt = f(x)
$$
> and
$$
\int_{t_a}^{t_b} \frac{df}{dt}\ dt = f(t_b) - f(t_a).
$$