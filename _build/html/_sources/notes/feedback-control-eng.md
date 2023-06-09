# Notes on feedback control
The materials in this part heavily stems from MAE433 lecture note taught at Princeton University

## State-space systems
```{admonition} Question: Why does if $\dot{x} = Ax$ then the solution is $x(t) = e^{At}x_0$ 
:class: note

Before talking about the matrix $A$, let us first look at a simpler case where we have $\dot{x} = ax$, with $a$ a scalar value.

We have the following derivation:

$$
\begin{align*}
    &\dot{x} = ax \\
    &\leftrightarrow \frac{\dot{x}}{x} = a \\ 
    &\leftrightarrow \int_{x_0}^{x(t)} \frac{\dot{x}}{x} \,dx = \int_{0}^{t} a \,dt && \text{taking integral both sides} \\ 
    &\rightarrow \log{x(t)} - \log{x_0} = at \\ 
    &\leftrightarrow \log{\frac{x(t)}{x_0}} = at \\
    &\leftrightarrow \frac{x(t)}{x_0} = e^{at} \\
    &\leftrightarrow x(t) = e^{at} x_0
\end{align*}
$$
```