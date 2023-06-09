# 9. Inner Products

Let's look at **inner products** and **inner product space**.

```{admonition} Definition
:class: important
Let the field $\mathbb{F}$ be $\mathbb{R}$ or $\mathbb{C}$, and consider the linear space $(H, \mathbb{F})$. The function:

$$
\langle\cdot,\cdot\rangle: H \times H \rightarrow \mathbb{F}
$$

is called an **inner product** if, for each $x, y, z \in H$ and $\alpha \in \mathbb{F}$:

1. $\langle x, y+z\rangle = \langle x, y\rangle + \langle x, z\rangle$
2. $\langle x, \alpha y\rangle = \alpha \langle x, y\rangle$
3. $|x|^2 \equiv \langle x, x\rangle > 0$ *iff* $x \neq \theta_H$
4. $\langle x, y\rangle = \overline{\langle y, x\rangle}$
```

```{admonition} Definition
:class: important
A complete inner product space is known as a *Hilbert space*.

```{note}
The completeness definition here refers to the fact that every Cauchy sequence in the space must converge.
```

A vector $v \in H$ that satisfies $|v| = \langle v, v\rangle = 1$ is said to be a *unit vector*.

```{admonition} Remark
:class: note
Inner products allow us to define orthogonality of vectors and discuss angles between vectors.
```