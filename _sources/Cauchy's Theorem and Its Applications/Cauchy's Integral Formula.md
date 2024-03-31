# Cauchy's Integral Formula

````{prf:theorem}
:label: thm:13

Suppose $f$ is holomorphic in an open set $\Omega$, and $D$ is an open disk
centered at $z_0$ whose closure is contained in $\Omega$. Then $f$ has a power
series expansion at $z_0$ in the form

```{math}
:label: eq:45
\begin{align}
f(z) = \sum_{n=0}^\infty\frac{f^{(n)}(z_0)}{n!}(z - z_0)^n \quad\forall z \in D
\end{align}
```

````

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

The next theorem roughly demonstrates that the global behaviour of a holomorphic function is determined by its values on an appropriate small subset.


````{prf:theorem}

If $f$ is a holomorphic function in a connected open set $\Omega$, and vanishes on a sequence of distinct points whose limit is also in $\Omega$, then $f$ is constantly zero in $\Omega$.

In other words, let $f$ be a holomorphic function in a connected open set $\Omega$.
Suppose $\{z_n\}_{n \in \Z^+}$ is a sequence of distinct points in $\Omega$, and it converges to $z_0 \in \Omega$. If $f(z_n) = 0$ for all $n$ and $f(z_0) = 0$, then $f(z) = 0$ for all $z \in \Omega$.

````

At a first glance, this result seems magical and almost unrealistic.
How can the value of a function vanishes in the entire set only because it vanishes on a sequence of distinct points?



````{prf:proof}

We will first show that $f$ vanishes in an open disk $D_r(z_0)$ of $z_0$.
Since $f$ is holomorphic in $\Omega$, it is given by its Taylor series expansion at $z_0$:

```{math}
\begin{align*}
f(z) = \sum_{n=0}^\infty a_n  (z - z_0)^n \quad\forall z \in D_r(z_0)
\end{align*}
```

Assume $f$ is not constantly zero.
Then we can find the first nonzero coefficient $a_m$ in the expansion.
Write

```{math}
:label: eq:58
\begin{align}
f(z) & = a_m(z - z_0)^m + \sum_{k=1}^\infty a_{m+k}(z - z_0)^{m+k}\nonumber\\& = a_m(z - z_0)^m \left[1 + \sum_{k=1}^\infty\frac{a_{m+k}}{a_m}(z - z_0)^{k}\right]\end{align}
```

Note that the term $\sum_{k=1}^\infty \frac{a_{m+k}}{a_m}  (z - z_0)^{k}$ is a continuous function that vanishes at $z_0$.
Hence, we may find a sufficiently small neighbourhood $N$ of $z_0$ such that $1 + \sum_{k=1}^\infty \frac{a_{m+k}}{a_m}  (z - z_0)^{k}$ is nonzero in $N$.
By the given condition, there exists a point $z_j$ in the sequence such that $z_j \neq z_0$ and $z_j \in N$.
Plugging $z_j$ into {eq}`eq:58`, we have

```{math}
\begin{align*}
0 = f(z_j) = a_m(z_j - z_0)^m \left[1 + \sum_{k=1}^\infty\frac{a_{m+k}}{a_m}(z_j - z_0)^{k}\right]\end{align*}
```

This leads to a contradiction since the right-hand side is nonzero.
Therefore, $f$ is constantly zero in the disk $D_r(z_0)$.

Next, we will show that $f$ is zero in the entire set $\Omega$ by exploiting the fact that $\Omega$ is connected.
Let set $U$ be defined as the interior of the set of all points at which $f$ vanishes, i.e, $U = [f^{-1}(\{0\})]^\circ$
:::{note}

We apply the interior here to enforce that $U$ is open. Now, we will show that it is also closed and hence $U = \Omega$. (Of course, $U \neq \emptyset$.)

:::

Note that $U$ is a nonempty open subset of $\Omega$.
Let $w$ be an accumulation point of $U$.
Then we can find a sequence $\{w_n\}$ of distinct points in $U$.
And by the definition of $U$, $f(w_n) = 0 \; \forall n$.
Applying what we have proved above, we conclude that $f(z) = 0 \; \forall z \in D_{r^\prime} (w)$.
This shows that $w \in U$.
Therefore, $U$ contains all its points of accumulation, which means it is also closed.
Because $\Omega$ is connected and $U$ is a nonempty, both open and closed subset in $\Omega$, it follows that $U = \Omega$.
Therefore, $f(z) = 0 \; \forall z \in \Omega$.

````
