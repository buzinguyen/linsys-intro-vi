# 5. Matrix Representation of Linear Maps
```{contents}
:local:
```

We now know what are linear maps, now let's look at how to represent those linear maps as matrix multiplication.

## Definition
First, let's look at a statement:


```{important}
Any **linear** map between **finite dimensional vector spaces** can be represented as matrix multiplication.
```

There are two important pieces of information within this statement, that is:
1. We are considering **linear map** only 
2. The vector spaces that we are operating need to be **finite dimensional**

Now, let's see how can we represent a linear map as a matrix multiplication.

Given a linear map $\mathcal{A}: U \rightarrow V$, this means that $\mathcal{A}(u) = v$ ($\mathcal{A}$ operates on an element $u$ of domain $U$ gives an element $v$ of co-domain $V$). We want to write this as $Au = v$ with $A$ now is a matrix. This means that $A$ is a matrix representation of the linear map $\mathcal{A}$.

```{warning}
The $u, v$ in $\mathcal{A}(u) = v$ and the $u, v$ in matrix multiplication $Au = v$ are not necessarily the same. We will see more why this is the case later.
```

## Bases
Let's first construct bases for both our domain and co-domain. This is an important step because the matrix representation depends on the bases of both the domain and co-domain. In another word, if you have the bases for both the domain and co-domain, and the definition of the linear map $\mathcal{A}$, you can then construct the matrix $A$. If you change the bases, then matrix $A$ will change.

Assume that $U$ is an n-dimensional vector space, and $V$ is an m-dimensional vector space, given the basis $\{u_j\}^n_{j=1}$ and $\{v_j\}^m_{j=1}$ for each vector space respectively. Recall the meaning of basis: *$\{u_j\}^n_{j=1}$ is the set of basis for vector space $U$ iff any vectors in $U$ can be represented as a linear combination of $u_j$*. In addition, the coordinate of a vector $x \in U$ w.r.t the choice of basis is unique, that is:

$$
\forall x \in U \exists! \xi = \{\xi_i\}^n_{i=1} \ni x = \Sigma_{j=1}^{n}\xi_j u_j
$$

With $\xi_i$ are the unique coordinate of $x$ wrt choice of basis in $U$. From here, we have the following derivation:

$$
\begin{align*}
    \mathcal{A}(x) &= \mathcal{A}(\Sigma_{j=1}^{n}\xi_j u_j) \\
    &= \Sigma_{j=1}^{n}\xi_j\mathcal{A}(u_j) && \text{superposition of linear map} \tag 1 \\
\end{align*}
$$
Given that each $\mathcal{A}(u_j)$ is a linear map of element from $U \rightarrow V$, i.e. $\mathcal{A}(u_j) \in V$, we then have:

$$
\begin{align*}
    \mathcal{A}(u_j) = \Sigma_{i=1}^{m} a_{ij} v_i \tag 2
\end{align*}
$$

Think of it as the operation of linear map $\mathcal{A}$ on the j-th basis of $U$ to get the representation in term of basis elements in $V$.

From (1) and (2), we have:

$$
\begin{align*}
    \mathcal{A}(x) &= \Sigma_{j=1}^{n}\xi_j\mathcal{A}(u_j) \\
    &= \Sigma_{j=1}^{n}\xi_j\Sigma_{i=1}^{m} a_{ij} v_i \\
    &= \Sigma_{i=1}^{m}(\Sigma_{j=1}^{n} a_{ij} \xi_j) v_i \\
    &= \Sigma_{i=1}^{m} \eta_i v_i \tag 3
\end{align*}
$$

But as stated above, the coordinate of a vector in a vector space w.r.t the choice of basis is unique, hence, what we end up is a linear equation describing how the coordinates of vector $x$ change under the mapping $\mathcal{A}$.

## Linear Equation
From (3), we then have:

$$
\eta_i = \Sigma_{j=1}^{n} a_{ij} \xi_j \forall i = \{1\dots m\}, j = \{1 \dots n\} \tag 4
$$

Rewriting this in matrix form, we have:

$$
\eta = A \xi \tag 5
$$

Where $A$ is a matrix whose elements are the $a_{ij}$ that we have just constructed. $A$ takes the coordinates representation of $x$ in the domain and maps to the coordinate representation of the vector in the co-domain w.r.t choices of bases $\{u_i\}_{i=1}^n, \{v_j\}_{j=1}^m$.

We can now see that $\mathcal{A}(u) = v \not \leftrightarrow Au = v$, but rather $\mathcal{A}(u) = v \leftrightarrow A \xi = \eta$.

```{note}
$\mathcal{A}(u) = v \not \leftrightarrow Au = v$ is correct if we use standard basis elements in $\mathbb{R}^n$, then the vectors themselves are the coordinates. But in general, $A$ operates on the coordinate representation of the vector rather than the vector.
```

Overall, the key takeaway is: 

```{important}
The $j^\text{th}$ column of the matrix $A$ is $\mathcal{A}(u_j)$ expressed w.r.t the basis elements $\{v_i\}$
```