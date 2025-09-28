Recall that our solution to the linear system of differential equations 
$$
\mathbf{\dot{x}} = \mathbf{Ax}
$$
was the sum of eigenvector products
$$
\mathbf{x}=c_1e^{\lambda_1 x }v_1 + c_2e^{\lambda_2 x}v_2 + \dots + c_ne^{\lambda_n x}v_n.
$$
Let us write this in the form 
$$
\mathbf{x} =y_1v_1 + y_2 v_2 + \dots y_n v_n.
$$
Eigenvectors are extremely valuable to us because they are essentially the "axes" upon which our solution $\mathbf{x}$ acts on - if we vary only a single variable $y_k$, then we know that the solution has only changed along the eigenvector $v_k$. This allows us to build up a "phase-portrait" of our solution $\mathbf{x}$: a graph of how the vector $\mathbf{x}$ changes as $y_1, y_2, \dots, y_n$ vary, taking these as our axes. 

For our sanity's sake, let's consider only the two-dimensional case (with $y_1$ and $y_2$ as axes) and analyze the differing examples that arise out of the different forms of $y_1$ and $y_2$.

## Sinks and sources

Consider the case where $y_1 = c_1e^{\lambda_1 x}, y_2 =c_2e^{\lambda_2 x}$ have real eigenvalues $\lambda_1$, $\lambda_2$ with the same sign: $\lambda_1\lambda_2>0$.

If both eigenvalues are negative, then both $y_1$ and $y_2$ are exponentially decaying functions; as the value of $x$ grows, $y_1$ and $y_2$ become smaller and smaller multiples of $v_1$ and $v_2$ and eventually move \it towards \normalfont the origin. Points like these are known as "stable sinks", or simply sinks:

![](assets/images/DE-ch4-stablesink.jpg)

If both eigenvalues are instead positive, both $y_1$ and $y_2$ grow exponentially and thus travel *away* from the origin when $x$ gets large, causing the arrows to point outward instead. We call this an *unstable source* point:

![](assets/images/DE-ch4-unstablesource.jpg)

Other vectors close to the eigenvectors can be drawn asymptotically to the eigenvectors, as shown:

![](assets/images/DE-ch4-stablesink-2.jpg)

If $\lambda_1, \lambda_2$ are both real but have opposite signs, we obtain a *saddle point* as follows:

![](assets/images/DE-ch4-saddlenode.jpg)

This originates from one of $y_1, y_2$ growing exponentially and the other decaying exponentially. 


## Spiral points

If $\lambda_1$, $\lambda_2$ are complex conjugates (they must be, given that they are the solutions to a quadratic equation), we have three different cases. Let $\lambda_{1,2} = a \pm bi$, resulting in $y_{1,2} = e^{ax}(\cos{bx}\pm\sin{bx})$. Then we have a phase portrait that looks like a spiral: 

![](assets/images/DE-ch4-spiral.jpg)

Why a spiral? Because if we consider the $\cos bx + \sin bx$ term on its own, that multiplied by a vector gives us an ellipse (as we know ellipses have parametric equations $x=a\cos t, y=b\sin t$). But when the $e^{ax}$ term comes in, this "ellipse" either expands exponentially, creating an outward spiral, or collapses inward exponentially, creating an inward spiral. Alternatively, if the real part is zero, the phase portrait is simply two ellipses centered at the origin.




