# 7. Norms
```{contents}
:local:
```

## Definition
Let's look at the concept of **norms** and **normed vector spaces**.

```{admonition} Definition
:class: important
A norm is **a special map** between vector spaces which takes element from a vector space $(V, \mathbb{F})$ and maps those elements to the positive real line $\mathbb{R}_{+}$

$$
||\cdot|| : (V, \mathbb{F}) \rightarrow \mathbb{R}_+
$$
```

We call a normed vector space is a vector space which has a norm defined on it.

```{admonition} Definition
:class: important
A normed vector space is a vector space which has a norm defined on it.
```

## Properties of norm
A norm $||\cdot||$ that maps $V \rightarrow \mathbb{R}_+$ satisfies the following properties:

* **Triangle property**:
    $$
    || v_1 + v_2 || \le ||v_1|| + ||v_2|| \forall v_1, v_2 \in V
    $$
* $||\alpha v|| = |\alpha| ||v||$
    ```{note}
    As the normed vector space $V$ has the associated field $\mathbb{F}$, the value of $|\alpha|$ depends on $\mathbb{F}$. If $\mathbb{F}$ is real number, then $|\alpha|$ is absolute value. Else if $\mathbb{F}$ is field of complex number ($\mathbb{C}$) then $|\alpha|$ will be the magnitude of the complex number.
    ```
* $||v|| = 0 \leftrightarrow v = \theta_v$

```{admonition} Remark
:class: note
A norm has to satisfy the above properties. Thus to check if a candidate norm is in fact a norm, we can check to see if it satifies all the above properties.
```

## Norms for vector space
**Example**: Given the normed vector space $(\mathbb{F}^n, \mathbb{F})$
* The 1-norm: $||x||_1 = \Sigma_{i=1}^{n} |x_i|$
* The 2-norm: $||x||_2 = (\Sigma_{i=1}^{n} |x_i|^2)^{\frac{1}{2}}$
* The p-norm: $||x||_p = (\Sigma_{i=1}^{n} |x_i|^p)^{\frac{1}{p}}$
* The $\infty$-norm: $||x||_\infty = \max_{i} |x_i|$

These are the norms that we use frequently in $\mathbb{R}^n$.

*How about vector space with matrices?* We can construct norms from those matrices:

## Norms for vector space with matrices
**Example**: Consider matrix $A \in \mathbb{F}^{m \times n}$
* The a-norm: $||A||_a = \Sigma_{i=1}^{m} \Sigma_{j=1}^{n} |a_{ij}|$
* The Frobenius norm: $||A||_F = (\Sigma_{i=1}^{m} \Sigma_{j=1}^{n} |a_{ij}|^2)^{\frac{1}{2}}$
* The b-norm: $||A||_b = \max_{i \in \{1 \dots m\}, j \in \{1 \dots n\}} |a_{ij}|$

Though we do not use these norms so much. In linear systems, we tend to use another definition of norm called the **induced norm**, which will be discussed later.

*What about function space? Can we have norms for function space?*

## Norms for function space
**Example**: Given functions $f(\cdot) \in C([t_0, t_1], \mathbb{F}^n)$ ($C$ stands for continuous function). Possible norms are:
* The 1-norm (**the $L_1$ norm for functions**): $||f||_1 = \int_{t_0}^{t_1} ||f(t)|| dt$. 
  
  Here interestingly, the norm $||f_1||$ inside the integral does not have to be the 1-norm, but it can rather be any of the norm that we have previously discussed.
* The 2-norm (**the $L_2$ norm for functions**): $||f||_2 = (\int_{t_0}^{t_1} ||f(t)||^2 dt) ^ \frac{1}{2}$
* The $\infty$-norm: $||f||_\infty = \max \{||f(t)||, t \in [t_0, t_1]\}$

## Relations between norms
If we have a vector that is finite in 1 norm, do we know anything about this vector in another norm?

```{admonition} Remark: Equivalence of norms
:class: note
Two norms $||\cdot||_a, ||\cdot||_b$ on $(V, \mathbb{F})$ are said to be equivalent if one can be bounded with respect to another. We write this as $\exists m_l, m_u \in \mathbb{R}_+$ s.t

$$m_l ||v||_a \le |v||_b \le m_u |v||_a$$
```

From here, we have some nice relationships

**Example**: Given a vector $x \in \mathbb{R}^n$: 

$$||x||_\infty \le ||x||_1 \le n ||x||_\infty$$