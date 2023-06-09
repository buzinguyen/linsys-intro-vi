# 12. Singular Value Decomposition

If we have matrix $A \in \mathbb{C}^{m\times n}$. Assume that $\text{rank}(A) = r \le \min{(m, n)}$. The theorem of SVD states that:

```{admonition} Theorem: Singular Value Decomposition
:class: important
There exists unitary matrices $U \in \mathbb{C}^{m\times m}$, $V \in \mathbb{C}^{n \times n}$ such that

$$
A = U \Sigma V^*
$$

With $V^*$ the complex conjugate transpose of $V$, $\Sigma \in \mathbb{R}^{m \times n}$ is a diagonal matrix which has the following form:

$$
\begin{align*}
    \Sigma = \begin{bmatrix}
        \Sigma_r & 0_{r \times (n-r)} \\
        0_{(m-r) \times r} & 0_{(m-r) \times (n-r)}
    \end{bmatrix}
\end{align*}
$$

With $\Sigma_r$ a **diagonal square matrix** with the diagonal entries are the non-zero singular values of $A$, denotes $\text{diag}(\sigma_1, \sigma_2, \dots, \sigma_r)$
```

From here, we can think more about the structure of $U, V$. Let us have the following form of the matrices $U, V$

$$
\begin{align*}
    U &= \begin{bmatrix}
        U_1 & U_2
    \end{bmatrix} \; \text{with} \; U_1 \in \mathbb{C}^{m\times r}, U_2 \in \mathbb{C}^{m \times (m-r)} \\
    V &= \begin{bmatrix}
        V_1 & V_2
    \end{bmatrix} \; \text{with} \; V_1 \in \mathbb{C}^{n\times r}, V_2 \in \mathbb{C}^{n \times (n-r)}
\end{align*}
$$

With this and the theorem, we can now break down further the decomposition into:

$$
A = U\Sigma V^* = U_1 \Sigma_r V_1^*
$$

We also have $U^*U = I_m$, $V^*V = I_n$, $U_1^*U_1 = I_r$, $V_1^*V_1 = I_r$.

From here we have:

$$
\begin{align*}
    &AA^* = U_1 \Sigma_r V_1^*(U_1 \Sigma_r V_1^*)^* = U_1 \Sigma_r V_1^*V_1\Sigma_r^*U_1^* = U_1 \Sigma_r^2 U_1^*\\
    &AA^*U_1 = U_1 \Sigma_r^2 \; \text{with} \; U_1 = \begin{bmatrix}
        u_1 & u_2 & \dots & u_r
    \end{bmatrix}
\end{align*}
$$

Look at the last equation, it has the form of eigenvalues and eigenvectors ($Av = \lambda v$). We call that the columns $u_i$ of $U_1$ is the **left singular vectors** of the matrix $A$.

Similarly, using the same break down, we will have:

$$
\begin{align*}
    &A^*A = (U_1 \Sigma_r V_1^*)^*U_1 \Sigma_r V_1^* = V_1 \Sigma_r^* U_1^*U_1 \Sigma_r V_1^* = V_1 \Sigma_r^2 V_1^* \\
    &A^*A V_1 = V_1 \Sigma_r^2 \; \text{with} \; V_1 = \begin{bmatrix}
        v_1 & v_2 & \dots & v_r
    \end{bmatrix} \\ 
    &A^*A v_i = \sigma_i^2 v_i
\end{align*}
$$

We call $v_i$ the **right singular vectors** of matrix $A$.