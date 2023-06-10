# 8. Induced Norms
```{contents}
:local:
```

We will look at induced norms, i.e. norms that are induced by some function operations.

## Definition
```{admonition} Definition
:class: important
Consider $\mathcal{A}: (U, \mathbb{F}) \rightarrow (V, \mathbb{F})$ a map from 1 vector space to another over the same field. We also require $\mathcal{A}$ to be linear and continuous. Suppose $U, V$ are all normed vector spaces, with associated norms $||\cdot||_u$ and $||\cdot||_v$. We define the induced norm of the map $\mathcal{A}$ as follows:

$$
||\mathcal{A}||_i = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_v}{||u||_u}
$$

```{note}
The $i$ in $||\mathcal{A}||_i$ stands for induced norm.
```

*How to intuitively understand this?* The induced norm gives us a sense (a measure) of the action of the linear operator by measuring the action of the operator on all vectors $u \in U \text{s.t} u \neq \theta$ and then take a supremum of all the measures. Notice that we are having $||\mathcal{A}u||_v$ w.r.t the norm in $V$. Think of this like:
* Apply the mapping (operator) $\mathcal{A}$ onto $u$ then measure the result using measurement from $V$, i.e. ||\mathcal{A}u||_v
* For each of those measurement, divide it by original measure (before operation) measured in $U$, i.e. $||u||_u$
* Take the supremum of all of these, then we get the overall sense of how the operator acts.

On another note, we are only writing the definition of induced norm by $||\cdot||_u, ||\cdot||_v$ which stand for norms in $U, V$ without specifically specify which norms are they. It means that we can choose any norms available within normed vector space $U, V$ to use here in order to calculate the induced norm $||\cdot||_i$.

**Example**: Define the induced 1-norm as $||\mathcal{A}||_{1,i}$, then:

$$
||\mathcal{A}||_{1,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_1}{||u||_1}
$$

Similarly, for the induced 2-norm:

$$
||\mathcal{A}||_{2,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_2}{||u||_2}
$$

<!-- We see the definition of induced norm on the linear operator $\mathcal{A}$. How will this affect the matrix representation of $\mathcal{A}$?  -->

## Concrete forms of induced norms
Given the operator $\mathcal{A}: \mathbb{F}^n \rightarrow \mathbb{F}^m$. Write the induced $p$-norm as $||A||_{p, i}$ with $p$ representing the type of norm that we are choosing. The induced $p$-norm on the operator $\mathcal{A}$ is:

$$
||\mathcal{A}||_{p,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_p}{||u||_p}
$$

Let's look at some of the matrix norms (induced norms) that we usually use, and their concrete forms.

**Example**: 

* Given the induced 1-norm $||\mathcal{A}||_{1,i}$, we can show the following

    $$
    ||\mathcal{A}||_{1,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_1}{||u||_1} = \max_{j \in \{1 \dots n\}}\{\Sigma_{i=1}^{m}|a_{ij}|\}
    $$

    This is called the **max column sum**.

* Given the induced 2-norm $||\mathcal{A}||_{2,i}$

    $$
    ||\mathcal{A}||_{2,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_2}{||u||_2} = \max_{j \in \{1 \dots n\}}\{\lambda_i(A^*A)\} ^ \frac{1}{2}
    $$

    With $A^*$ the conjugate transpose of $A$, $\lambda_i(\cdot)$ the $i^{\text{th}}$ eigenvalue ($A^* A$ is a squared matrix).

* Given the induced $\infty$-norm $||\mathcal{A}||_{\infty,i}$

    $$
    ||\mathcal{A}||_{\infty,i} = \sup_{u \neq \theta} \frac{||\mathcal{A}u||_\infty}{||u||_\infty} = \max_{i \in \{1 \dots m\}}\{\Sigma_{j=1}^{n} | a_{ij}|\}
    $$

    This is called the **max row sum**.

Let's now try to prove that those concrete forms are actually induced from the definition w.r.t the norms that we are using.

**Proof**: Induced 1-norm

```{admonition} Remark: The 1-norm
:class: note

Given the vector space $\mathbb{F}^n$, given the vector $x \in \mathbb{F}^n$ the 1-norm is:

$$||x||_1 = \Sigma_{i=1}^{n} |x_i|$$
```

From the definition of induced $p$-norm applied for 1-norm, we have the induced 1-norm:

$$
\begin{align*}
    ||\mathcal{A}||_{1,i} &= \sup_{x \neq \theta} \frac{||\mathcal{A}x||_1}{||x||_1} \\
    &= \sup_{x \neq \theta} \frac{\Sigma_{i=1}^{m} |(\mathcal{A}x)_i|}{\Sigma_{i=1}^{n} |x_i|} && \text{$\mathcal{A}: \mathbb{F}^n \rightarrow \mathbb{F}^m$, $x \in \mathbb{F}^n$} \\
    & && \rightarrow \mathcal{A}x \in \mathbb{F}^m \text{ i.e. $\mathcal{A}x$ has dimension $m \times 1$} \\
    &= \sup_{x \neq \theta} \frac{\Sigma_{i=1}^{m} |\Sigma_{j=1}^{n}a_{ij}x_j|}{\Sigma_{i=1}^{n} |x_i|} \\
    &\le \sup_{x \neq \theta} \frac{\Sigma_{i=1}^{m} \Sigma_{j=1}^{n}|a_{ij}||x_j|}{\Sigma_{i=1}^{n} |x_i|} \\
    &= \sup_{x \neq \theta} \frac{\Sigma_{j=1}^{n}(|x_j|\Sigma_{i=1}^{m} |a_{ij}|)}{\Sigma_{i=1}^{n} |x_i|} \\
    &= \dots \\
    &\le \max_{j \in \{1 \dots n\}}\{\Sigma_{i=1}^{m}|a_{ij}|\}
\end{align*}
$$

From here, we have that $||\mathcal{A}||_{1,i} \le \max_{j \in \{1 \dots n\}}\{\Sigma_{i=1}^{m}|a_{ij}|\}$, not an equality. But the derivation so far is w.r.t the choice of vector $x$. If we can choose a vector $x$ s.t the value of $x = \begin{bmatrix}0 & 0 & \dots & 1 & \dots & 0 & 0\end{bmatrix}^\intercal$ with the index of value $1$ in $x$ is the index of the maximum column sum of $A$, then from the inequality we achieve the equality.


