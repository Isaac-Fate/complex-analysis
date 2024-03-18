# Cauchy's Integral Formula

````{prf:theorem} Liouville's Theorem
:label: thm:11

TODO

````

````{prf:theorem} Fundamental Theorem of Algebra
:label: thm:12

Every polynomial with degree greater than $0$ with complex coefficients has a
root in $\C$.

````

````{prf:proof}

Let polynomial $p(z)$ be given by

```{math}
\begin{align*}
p(z) = a_n z^n + \cdots a_1 z + a_0
\end{align*}
```

where $n \geq 1$ and $a_n \neq 0$.
We shall prove by contradiction.
Assume $p(z)$ has no roots in $\C$. Then the reciprocal $1 / p(z)$ is defined on the entire
complex plane.
Moreover, the derivative of $1 / p(z)$ clearly exists everywhere.
Therefore, $1 / p(z)$ is entire.
We will use Liouville's theorem to establish a contradiction.
To do so, we are going to show $1 / p(z)$ is bounded.

We have

```{math}
\begin{align*}\frac{p(z)}{z^n} = a_n + \frac{a_{n-1}}{z} + \cdots + \frac{a_1}{z^{n-1}} + \frac{a_0}{z^n}\end{align*}
```

Note that when $\abs{z} \to \infty$, the modulus of the quotient $p(z) / z^n$ will
tend to $\abs{a_n}$.
This implies that there exists $R > 0$ such that

```{math}
:label: eq:55
\begin{align}\abs{\frac{p(z)}{z^n}} > \frac{\abs{a_n}}{2}\end{align}
```

whenever $\abs{z} > R$. Rearranging {eq}`eq:55`, we have

```{math}
\begin{align*}\abs{\frac{1}{p(z)}} < \frac{2}{\abs{a_n}}\cdot\frac{1}{\abs{z}^n} < \frac{2}{\abs{a_n} R^n}\quad\text{if }\abs{z} > R
\end{align*}
```

The above inequality shows $1 / p(z)$ is bounded outside the disk $D$ centered
at $0$ with radius $R$.

For points inside the closed disk $\overline{D}$, since function $\abs{1 / p(z)}$ is
continuous and $\overline{D}$ is compact, $\abs{1 / p(z)}$ attains its maximum $M$ on $\overline{D}$.

Therefore, we see that $1 / p(z)$ is indeed bounded on entire complex plane $\C$.
By Liouville's theorem {prf:ref}`thm:11`, $1 / p(z)$ is constant, which leads to a
contradiction since polynomials with degree greater than $0$ are non-constant.



:::{note}

The last assertion that polynomials with degree greater than $0$ are
non-constant seem evident. But the reader should still prove it. See {prf:ref}`pro:4`.
And the proof is not that trivial.

:::

````

````{prf:proposition}
:label: pro:4

Polynomials with degree greater than $0$ are non-constant.

````

Now, we have proved polynomial $p(z)$ must have one root. Using mathematical
induction we can show that it actually has $n$ roots, and can be factorized as

```{math}
\begin{align*}
p(z) = a_n (z^n - z_1) (z^n - z_2) \cdots(z^n - z_n)
\end{align*}
```

````{prf:corollary}

Every polynomial $p(z) = a_n z^n + \cdots + a_1 z + a_0$ of degree $n \geq 1$ with
complex coefficients has exactly $n$ roots in $\C$. If these $n$ roots are
denoted by $z_1, \ldots, z_n$, then $p(z)$ can be factorized as

```{math}
\begin{align*}
p(z) = a_n (z^n - z_1) (z^n - z_2) \cdots(z^n - z_n)
\end{align*}
```

````

````{prf:proof}

We shall prove by induction.

**Base Case:** Suppose $n = 1$, then $p(z) = a_1 z + a_0$($a_1 \neq 0$). Setting $p(z) = 0$, we solve that $z = -a_0 / a_1$. Therefore, $z_1 = -a_0 / a_1$ is the only root of $p(z)$, and we can write $p(z) = a_1(z - z_1)$.

**Inductive Step:** Assume this corollary holds for $n = k$, we need to show that it also holds for $n = k + 1$.
By the Fundamental Theorem of Algebra {prf:ref}`thm:12`, there exists one root $z_1$ for $p(z)$.
We want to show that $p(z)$ has a factor $(z - z_1)$.
Let $\tilde{p}(z) = p(z + z_1)$.
Note that $\tilde{p}(z)$ is also a polynomial of degree $k + 1$.
Write

```{math}
:label: eq:56
\begin{align}\tilde{p}(z) = b_{k+1} z^{k+1} + \cdots + b_1 z + b_0
\end{align}
```

Because $z_1$ is a root of $p(z)$, we have $\tilde{p}(0) = p(z_1) = 0$. Substituting $z=0$ into {eq}`eq:56` yields $b_0 = 0$.
Therefore, we can write

```{math}
\begin{align*}\tilde{p}(z) = z (b_{k+1} z^{k} + \cdots b_2 z + b_1)
\end{align*}
```

Then, we recover the expression of $p(z)$ from $\tilde{p}(z)$.
Note that $p(z) = \tilde{p}(z - z_1)$.
Hence,

```{math}
\begin{align*}
p(z) = (z - z_1) \underbrace{(b_{k+1} z^{k} + \cdots b_2 z + b_1)}_{\text{a polynomial of degree $k$}}
= (z - z_1) q(z)
\end{align*}
```

Now, we may apply the induction hypothesis on $q(z)$.
We have

```{math}
\begin{align*}
p(z) & = (z - z_1) [c (z - z_2) \cdots(z - z_{k+1})]\\& = c (z - z_1) \cdots(z - z_{k+1})
\end{align*}
```

And we realized that $c$ is exactly $a_{k+1}$ since it is the coefficient of $z^{k+1}$.
Therefore, we have shown

```{math}
:label: eq:57
\begin{align}
p(z) = a_{k+1}(z - z_1) \cdots(z - z_{k+1})
\end{align}
```
{eq}`eq:57` tells us that $z_1, \ldots, z_{k+1}$ are roots of $p(z)$.
Moreover, $p(z)$ cannot have any other roots. To see this, suppose $w \neq z_j \\forall j=1, \ldots, k+1$. Then, substituting $z = w$ in {eq}`eq:57`, we see that $p(w) \neq 0$ since each factor is nonzero.

````
