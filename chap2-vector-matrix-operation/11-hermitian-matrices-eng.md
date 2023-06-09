# 11. Hermitian Matrices
```{contents}
:local:
```

We now know the definition of adjoints. Let's now look at self-adjoint maps

## Self-adjoint maps
Consider $(H, \mathbb{F}, \langle\cdot,\cdot\rangle _H)$. Consider linear and continuous map $\mathcal{A}:H \rightarrow H$. Meaning that $\mathcal{A}^*:H\rightarrow H$. $\mathcal{A}$ is self-adjoint if $\mathcal{A} = \mathcal{A}^*$. This also means that:

$$
\langle x, \mathcal{A}y \rangle = \langle \mathcal{A}x, y \rangle \; \forall x,y \in H
$$

## Hermitian matrices
Let $\mathcal{A} \simeq A = (a_{ij}), i, j \in 1\dots n$, with $\mathcal{A}$ the operator (map) and $A$ the matrix representation $\in \mathbb{F}^{n\times n}$.

The map $\mathcal{A}$ is self-adjoint iff $A$ is hermitian, i.e. $A = A^*$. The $A^*$ in matrix means complex conjugate transpose, i.e. \bar{a_{ji}}$.

```{admonition} Remark
:class: note
Hermitian matrices always have real eigenvalues.
```

## Unitary matrices
```{admonition} Definition: Unitary matrix
:class: important
A matrix $U$ is unitary iff

$$
U^*U = UU^* = I
$$
```

## Singular values
Let us have the matrix $A \in \mathbb{C}^{m\times n}$. We will have $AA^* \in \mathbb{C}^{m\times m}$ a square matrix. Let $\lambda_i , i=1\dots m$ be the *eigenvalues* of $AA^*$. This also means that $\lambda_i$ is real and non-negative.

If we have $\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_r \dots \ge \lambda_m$. If $r = \text{rank}(A) = \text{rank}(AA^*)$, then $\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_r \ge 0$ and all the remaining eigenvalues are all zeros.

We define the **singular values** of the matrix to be the square root of the eigenvalues.

```{admonition} Definition: Singular values
:class: important
The non-zero singular values of A are 

$$
\lambda_i^\frac{1}{2}, i = 1\dots r
$$
```