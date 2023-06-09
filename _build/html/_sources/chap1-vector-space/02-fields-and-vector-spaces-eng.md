# 2. Fields and Vector Spaces
```{contents}
:local:
```
## Fields
**What is a field?** A field $\mathbb{F}$, denotes $(\mathbb{F}, +, \cdot)$, is a set of objects/elements and 2 binary operations: multiplication ($\cdot$) and addition ($+$). The following also has to be satisfied:
* Rules for addition ($+$):
  * Associative: $(\alpha + \beta) + \gamma = \alpha + (\beta + \gamma)$
  * Commutative: $\alpha + \beta = \beta + \alpha$
  * $\exists$ identity element <span style="color:red">$0$</span>: $\alpha + 0 = \alpha$
  * $\exists$ inverse: $\forall \alpha \exists (-\alpha) \ni \alpha + (-\alpha) =$ <span style="color:red">$0$</span>
* Rules for multiplication ($\cdot$):
  * Associative: $(\alpha\beta)\gamma = \alpha(\beta\gamma)$
  * Commutative: $\alpha\beta = \beta\alpha$
  * $\exists$ identity element <span style="color:red">$1$</span>: $\alpha \cdot 1 = \alpha$
  * $\exists$ inverse: $\forall \alpha \neq 0 \exists \alpha^{-1} \ni \alpha \cdot \alpha^{-1} =$ <span style="color:red">$1$</span>

Also, multiplication distributes over addition:

$$
\alpha \cdot (\beta + \gamma) = \alpha \cdot \beta + \alpha \cdot \gamma
$$

```{note}
The operation of the element with its inverse w.r.t. the operation equals the identity element of the operation.
```
This means that, for addition ($+$), the identity is 0, and so the operation of the element on the inverse equals to 0, and vice versa, for multiplication ($\cdot$), the identity element is 1, and the operation of the element on the inverse equals to 1.

```{note}
The identity element has to be in the respective field.
```
This means that if there exists a set of elements such that the identity element does not belong to this set, the set cannot be considered a field.

Examples of fields that we usually use:
* Field of real numbers $\mathbb{R}$
* Field of complex numbers $\mathbb{C}$
* Field of rational functions with real coefficients $\mathbb{R}(s)$ e.g. $\frac{s^2 + 2s + 1}{s + 3}$


From definition of Fields, we will continue to define Vector Spaces.

## Vector Spaces
Vector space, or *linear space*, denotes $(V, \mathbb{F}, +, \cdot)$, is a set of elements $V$, here it is a set of vectors, and its respective field $\mathbb{F}$, with all the property of a field.

```{note}
Here, the addition is between vectors, but the multiplication is between a vector and elements in the field, called **scalar multiplication**. This also implies that when a field is associated with a vector space, its elements are called **scalars**.
```

For vector space, the following rules apply:
* Addition ($+$)
  * Associative: $(x + y) + z = x + (y + z)$ with $x, y, z \in V$
  * Commutative
  * $\exists$ identity element $\theta$: "0-vector"
  * $\exists$ inverse: $\forall x \in X \exists (-x) \ni x + (-x) = \theta$
* Scalar multiplication ($\cdot$)
  * $(\alpha \beta) x = \alpha (\beta x)$
  * $1 \cdot x = x$, with $1$ is the identity element from the field
  * $0 \cdot x = \theta$, with $0$ is the identity element from the field
  * Distributive: $(\alpha + \beta) x = \alpha \cdot x + \beta \cdot x$
  
Examples of vector space:
* $(\mathbb{R}^n, \mathbb{R})$
* $(\mathbb{C}^n, \mathbb{C})$
* $(\mathbb{C}^n, \mathbb{R})$

Example of not a vector space:
* $(\mathbb{R}^n, \mathbb{C})$

A special example of a vector space is a **function space**. Given a set of functions $F$ which map a set $D$ to a set $V$, with V is a vector space $(V, \mathbb{F})$, then we have $(F(D, V), \mathbb{F})$ a vector space.

This is important, because as we usually do operations with functions, it is beneficial to be able to put a vector space structure on those functions, so that we can do mathematics on that vector space.

```{admonition} How to prove a space is a vector space?
:class: note

To prove that a space is a vector space, it is simple to show the associativity and commutativity properties, but it is generally hard to show that the space is closed under the addition and scalar multiplication operations. This is where we typically spend our time when trying to prove that a space is a vector space.
```