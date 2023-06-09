# 3. Subspaces and Bases
```{contents}
:local:
```
We know what is vector space, now we will follow along and discuss what is subspace, and an important characteristic of vector space in term of their bases element.

## Subspaces
Consider a vector space $(V, \mathbb{F})$, consider a set $W \subseteq V$, is $W$ a vector space? Meaning that, if we apply addition and scalar multiplication to elements of $W$, will be still be staying inside $W$? i.e. is $W$ closed under vector addition and scalar multiplication?

```{admonition} Definition
:class: important
$W$ is a subspace of $V$ if:
1. $W \subseteq V$
2. $W$ is closed under vector addition and scalar multiplication (defined for the parent space $V$) using the field associated $\mathbb{F}$
```

**Example**: Given a space $\mathbb{R}^3$, any planes that go through the origin is a subspace of $\mathbb{R}^3$. 

Some properties to consider: If $W_1, W_2$ are both subspaces of $V$, then:
1. $W_1 \cap W_2$ is a subspace
2. $W_1 \cup W_2$ is not necessarily a subspace

An example of this is if we consider the space $\mathbb{R}^3$, if $W_1$ is the x-axis, $W_2$ is the y-axis, then their union is just 2 lines, but the addition of an element from $W_1$ and an element from $W_2$ belongs to the plane Oxy, which is not the same as the union of the 2 axes.

## Linear independence
```{admonition} Definition
:class: important
Given a vector space $(V, \mathbb{F})$, given a set of vectors $\{v_1, v_2, \dots, v_p\}, v_i \in V$. This set of vectors is said to be **linearly independent** iff:

$$\alpha_1 v_1 + \alpha_2 v_2 + \dots + \alpha_p v_p = \theta \rightarrow \alpha_i = 0 (\alpha_i \in \mathbb{F})$$
```

This means that you cannot write any vector as a linear combination of other vectors:

$$
-\alpha_1 v_1 \neq \alpha_2 v_2 + \dots + \alpha_p v_p, \alpha_i \neq 0
$$

Conversely, the set of vectors is said to be **linearly dependent** iff $\alpha_1, \alpha_2, \dots, \alpha_p$ not all 0, and:

$$
\alpha_1 v_1 + \alpha_2 v_2 + \dots + \alpha_p v_p = \theta
$$

This means that if the set of vectors is linear dependent, you can write one or some of those vectors as a linear combination of other vectors. This also means that **those vectors are redundant**.

From the definition of linear independence, we define the basis set.

## Bases
```{admonition} Definition
:class: important
Define a set of vectors $B = \{b_1,, b_2, \dots, b_n\}$. This set of vectors is called a **basis** of $V$ iff:
1. $B$ spans $V$
2. $B$ is linearly independent 
```

$B$ spans $V$ means that for for any $v \in V$, we can write $v$ as a linear combination of the basis elements. i.e.:

$$
v = \alpha_1 b_1 + \alpha_2 b_2 + \dots + \alpha_n b_n
$$

This means that the set of basis has to be (1) big enough so that it can represent any vector in $V$, and that it is (2) small enough so that we do not include any redundant factors.

From here, we define the coordinates of a vector $v \in V$ as the set of scalars that multiply the basis elements to get the vector $v$:

```{admonition} Definition
:class: important
For $v \in V$, $v = \alpha_1 b_1 + \alpha_2 b_2 + \dots + \alpha_n b_n$ then $\alpha_i$, i = $1 \dots n$ are called the coordinates of $v$ w.r.t. $B$.
```

```{note}
You can have an infinite number of basis for a vector space. However, the number of elements in any basis is constant. This is the **dimension of the vector space**.
```

```{note}
Once you have chosen the basis, the set of coordinates is unique for that basis. This means that given a basis, any vector in the space is uniquely defined by its coordinate.
```