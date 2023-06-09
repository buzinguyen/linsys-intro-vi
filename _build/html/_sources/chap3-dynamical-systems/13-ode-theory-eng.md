# 13. Fundamental Theorum of ODEs
```{contents}
:local:
```
## Fundamental theorem
In this module we will discuss properties of ordinary differential equations (ODE) that guarantee that ODE has a **unique solution for a given initial condition**.

Let us have $\dot{x} = f(x, t)$, $x(t) \in \mathbb{R}^n$, $f(\cdot, \cdot) = \mathbb{R}^n \times \mathbb{R}_+ \rightarrow \mathbb{R}^n$. Let us have the initial condition $x(t_0) = x_0$. The fundamental theorem asks under what conditions does the solution to the ODE exists, with the solution means a trajectory, i.e. a function $x$ as a function of time, $x(t)$ that satisfies the differential equation. This means that if you take the derivative of that function with respect to time, we receive $f(x, t)$.

```{admonition} Theorem: Fundamental theorem (Existence and Uniqueness)
:class: important
If $f(x, \cdot): \mathbb{R}_+ \rightarrow \mathbb{R}^n, \forall x \in G \subseteq \mathbb{R}^n$ is **piecewise continuous** and $f(\cdot, t): \mathbb{R}_+ \rightarrow \mathbb{R}^n, \forall t$ is **Lipschitz continuous** then there **exists a unique** function of time $\phi(\cdot):\mathbb{R}_+\rightarrow \mathbb{R}^n$ which is differentiable ($C^1$) almost everywhere, $\phi(t_0) = x_0$ and $\dot{\phi(t)} = f(\phi(t), t), \forall t \in [t_0, t_1] \backslash D$, with $D$ a set of all points that $f$ is not continuous in time.
```{admonition} TL;DR
:class: note
Unique solution with respect to the initial condition exists if $f$ is 
* piecewise continuous function of time, and
* Lipschitz continuous function of $x$.
```

## Continuity ($C^0$)
```{admonition} Definition
:class: important
A function $f(\cdot)$ is continuous if $\forall \epsilon > 0 \; \exists \delta > 0 \; \text{s.t if}$:

$$
||x_1 - x_2|| < \delta \quad \text{then} \quad ||f(x_1) - f(x_2)|| < \epsilon
$$
```

The order of $\delta$ and $\epsilon$ matters here. From the definition it means that **if a function is continuous, then no matter how small the change in $f$ is, we can always find a bound for the change in $x$**. We also see that the definition uses norm notation, meaning that $f$ is a function between [normed vector space](../chap2-vector-matrix-operation/07-norms-eng.md), and the norm used here is any norm defined appropriately in the normed vector space. Then from this, there is another way for us to think about the definition of continuity: **if there are two points in the domain and $f$ acting on these points, if their distance is small, then if the function is continuous, then the distance being small will be maintained in the range, i.e. $f(x_1), f(x_2)$ will be close together**.

## Piecewise continuity ($PC$)
```{admonition} Definition
:class: important
A function is $PC$ if $f(x, \cdot): \mathbb{R}_+ \rightarrow \mathbb{R}^n$ is $C^0$ except at points of discontinuity, and there can only be **finitely** many of these points in any compact (closed and bounded) interval of time.
```
## Lipschitz continuity ($LC$)
```{admonition} Definition
:class: important
$f(\cdot, t): \mathbb{R}^n \rightarrow \mathbb{R}^n$ is Lipschitz continuous (LC) for all time in relevant interval if there exists a PC function $K(\cdot): \mathbb{R}_+ \rightarrow \mathbb{R}_+$ such that:

$$
||f(x_1) - f(x_2)|| \le K(t)||x_1 - x_2||
$$

If $x_1, x_2 \in \mathbb{R}^n$, we say the function is globally Lipschitz continuous.

The inequality is called the **Lipschitz inequality**, the function $K(\cdot)$ is called the **Lipschitz function**.
```

## Relations between different types of continuity
From the definitions, we can see that:
* $LC \rightarrow C^0$
* $C^0 \not\rightarrow LC$

$LC$ is a stricter condition than $C^0$.

## Candidate Lipschitz function $K(\cdot)$
```{admonition} Remark: Candidate Lipschitz function
:class: note
A candidate Lipschitz function $K(t)$ (*candidate* means that it might not work) is the a norm on the Jacobian of $f$, i.e. $||D_1 f||$ (partial derivative of $f$ with respect to the first variable, in this case it is $x$).

$$
||D_1 f|| = ||\begin{bmatrix}
    \frac{\partial f_1}{\partial x_1} & \dots & \frac{\partial f_1}{\partial x_n} \\ 
    \dots & \dots & \dots \\
    \frac{\partial f_n}{\partial x_1} & \dots & \frac{\partial f_1}{\partial x_n}
\end{bmatrix}||
$$
```

This is true because of the **mean value theorem**, which states that:

$$
||f(x_1) - f(x_2)|| \le ||Df||_i ||x_1 - x_2||
$$

Moreover, $||Df||_i$ is induced norm, so you can actually choose strategically what to use here to give you the best possible candidate Lipschitz function. **For example**, you can choose a norm that does not depend on $x$, then the Lipschitz function will be valid for all $x$.