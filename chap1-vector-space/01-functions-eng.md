# 1. Functions
```{contents}
:local:
```
## What is a function?
Define 2 sets of elements, we define function as a mapping of elements from 1 set into another set.

$$
\mathcal{f}:X \rightarrow Y
$$

We say this as *$f$ maps $X$ into $Y$*. $X$ is called the **domain** of f, and Y is called the **co-domain** of f. The set $f(X)$ is called the **range** of f.

We can define mathematically the range of $f$,i.e. $f(X)$ as:

$$
f(X) = \{f(x) | x \in X\}
$$

Couple of things to remember:
- In general, the range of $f$ does not equal to the co-domain of $f$. That's why we say it as $f$ maps $X$ **into** $Y$.
- However, by defition, $f$ will be called a function if for all elements $x \in X$, there exists a **unique** value $f(x)$,i.e. the function assigns a unique value $f(x) \forall x \in X$.

## Properties of functions
There are 3 properties: injective, surjective and bijective.

**Injective**: A function is called injective ("one-to-one") iff 

$$f(x_1) = f(x_2) \leftrightarrow x_1 = x_2$$ 

This means that an element in $Y$ cannot be a mapping of more than 1 element in $X$. Equivalently, $x_1 \neq x_2 \leftrightarrow f(x_1) \neq f(x_2)$.

**Surjective**: A function is called surjective ("onto") iff 

$$\forall y \in Y, \exists x \in X \ni y = f(x)$$ 

This means that every element in $Y$ is a result of the mapping from $X$ through $f$. We can think of this as *the range of $f$ expands the entire co-domain*.

**Bijective**: A function is called bijective if it is both surjective and injective.

$$\forall y \in Y, \exists! x \in X \ni y = f(x)$$

Injectivity comes in at the $\exists!$,i.e. a unique mapping.