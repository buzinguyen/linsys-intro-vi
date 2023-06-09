# 4. Linear Maps
```{contents}
:local:
```
## Maps between vector spaces
Define 2 vector spaces $(V, \mathbb{F})$ and $(W, \mathbb{F})$. Define the map $\mathcal{A}$ that takes the element of $V$ to element of $W$.

```{admonition} Definition
:class: important
$\mathcal{A}$ is a linear map iff:

$$\mathcal{A}(\alpha_1 v_1 + \alpha_2 v_2) = \alpha_1 \mathcal{A}(v_1) + \alpha_2 \mathcal{A}(v_2)$$

Notice that $v_1, v_2$ are elements of $V$, and $\mathcal{A}(v_1), \mathcal{A}(v_2)$ are elements of $W$. This is called **superposition**.
```

## Range space and null space
Given a linear map $\mathcal{A}:U \rightarrow V$

**Range space**

$$\mathcal{R}(\mathcal{A}) = \{v | v = \mathcal{A}(u), u \in U\}$$

In another word, the range space is a set of elements in the co-domain $V$ that comes from the elements of the domain $U$. We often call the range space **the image of $\mathcal{A}$**.

**Null space**:

$$\mathcal{N}(\mathcal{A}) = \{u | \mathcal{A}(u) = \theta_v\}$$

In another word, the null space is the set of $u \in U$ such that the linear map $\mathcal{A}(u)$ equals the zero element in co-domain $V$. We often call the null space **the kernel of $\mathcal{A}$**.

```{admonition} Theorem
:class: important
The range space of $\mathcal{A}$ is a subspace of co-domain $V$; the null space of $\mathcal{A}$ is a subspace of the domain $U$.
```

```{admonition} Definition
:class: important
Given $b \in V$

1. If the linear equation $\mathcal{A}(u) = b$ has at least 1 solution, i.e. there is a $u$ that satisfies $\mathcal{A}(u) = b$ $\leftrightarrow$ $b \in \mathcal{R}(\mathcal{A})$
2. If $b \in \mathcal{R}(\mathcal{A})$, then:  
  2.1. The linear equation $\mathcal{A}(u) = b$ has a **unique** solution $\leftrightarrow \mathcal{N}(\mathcal{A}) = \{\theta_u\}$. i.e. the only thing in the null space is the zero vector.  
  2.2. Let $x_0 \in U$  s.t. $\mathcal{A}(x_0) = b$, then $\mathcal{A}(u) = b \leftrightarrow u - x_0 \in \mathcal{N}(\mathcal{A})$
```

From the theorem we can see that there is a relationship between the size of the null space and the solution of the linear equation $\mathcal{A}(u) = b$.

```{note}
Think of matrix multiplication as linear transformation. The rank of the matrix determines the dimension of the transformation result. For example, a 3D matrix with rank 2 has a transformation that results in a 2D space. Then, the 1D that goes missing is within the null space of the matrix.

Think of it in the system of equation $Ax = v$, if $v = \begin{bmatrix}0\\0\end{bmatrix}$ then the null space gives us all the possible solutions to the equation.
```

