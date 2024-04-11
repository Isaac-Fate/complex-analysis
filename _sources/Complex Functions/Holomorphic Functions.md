# Holomorphic Functions
```{index} complex differentiable functions
```

````{prf:definition} 

Let $f: \Omega \to \C$ be a function defined on an open set $\Omega \subseteq \C$.
We say $f$ is  **complex differentiable** 
at $z \in \Omega$ if the quotient

```{math}
\frac{f(z + h) - f(z)}{h}
```

converges when $h \to 0$.
Its limit is denoted by $f^\prime(z)$
and called the derivative of f at $z$.
We write

```{math}

f^\prime(z) = \lim_{h \to 0}\frac{f(z + h) - f(z)}{h}
```
```{index} holomorphic in an open set
```

We say $f$ is  **holomorphic in an open set** $\Omega$
if $f$ is complex differentiable at every point of $\Omega$.

```{index} holomorphic at a point
```

And we say $f$ is  **holomorphic at a point** $z \in \Omega$ if $f$ is holomorphic in a neighbourhood of $z$.

````

:::{note}

It should be emphasized that $f$ being holomorphic at a point $z$
is not the same as $f$ being complex differentiable at $z$.
Being holomorphic at a point is a stronger condition since
it means that $f$ should be complex differentiable
at every point in a neighbourhood of that point.

:::