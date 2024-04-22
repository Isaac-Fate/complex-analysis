# Cauchy's Integral Formula

````{prf:theorem} Cauchy's Integral Formula
:label: thm:5

Let $D$ be an open disk,
and $\Omega$ an open set containing $\overline{D}$.
If $f$ is holomorphic in $\Omega$.
Then for any point $z \in D$, we have

```{math}

f(z) = \frac{1}{2 \pi i}\oint_{C}\frac{f(\zeta)}{\zeta - z}\dif\zeta
```

where $C = \partial D$ is the positively oriented circle boundary of $D$.

````

````{prf:proof}

We will consider the contour integrals of the integrand

```{math}

g(\zeta) = \frac{f(\zeta)}{\zeta - z}, \quad\zeta\in D \setminus\{z\}
```

Consider the $\Gamma_{\delta, \varepsilon}$ be a keyhole contour illustrated
in {numref}`fig:2`.
Here $\delta$ denotes width of the corridor and $\varepsilon$
is the radius of the small arc $\gamma_{\varepsilon}$ centered at $z$.
The outer arc is denoted by $\gamma$ and the two line segments forming the corridor
are denoted by $\ell_1$ and $\ell_2$.
Cauchy's Theorem tells us the counter integral
along $\Gamma_{\delta, \varepsilon}$ is zero, i.e.,

```{math}
:label: eq:9
\int_\gamma g(\zeta) \dif\zeta
+ \int_{\gamma_{\varepsilon}} g(\zeta) \dif\zeta
+ \int_{\ell_1} g(\zeta) \dif\zeta
+ \int_{\ell_2} g(\zeta) \dif\zeta
= 0

```
```{figure} /figures/keyhole-for-proving-the-cauchy-integral-formula.png
---
name: fig:2
---
The keyhole contour $\Gamma_{\delta, \varepsilon}$.
```

As $\delta \to 0$,
the corridor gets narrower and narrower,
the integrals along $\ell_1$ and $\ell_2$
will cancel each other.
To see this, consider the illustration in {numref}`fig:3`.

```{figure} /figures/adding-a-quadrilateral-to-two-line-segments.png
---
name: fig:3
---
By adding a quadrilateral to the two line segments, the sum of the contour integrals along $\ell_1$ and $\ell_2$ is equivalently transformed to the sum of contour integrals along $\ell_3$ and $\ell_4$. As $\delta \to 0$, both lengths of $\ell_3$ and $\ell_4$ tend to zero, and hence the contour integrals along them will also vanish
by the ML inequality.
```

Meanwhile, as $\delta \to 0$,
the contour integrals along arcs will tend to
the integrals along the circles, i.e.,
$\int_\gamma g(\zeta) \dif \zeta \to \oint_C g(\zeta) \dif \zeta$
and $\int_{\gamma_{\varepsilon}} g(\zeta) \dif \zeta \to \oint_{C_\varepsilon} g(\zeta) \dif \zeta$
Hence, letting $\delta \to 0$, {eq}`eq:9` becomes

```{math}
:label: eq:10
\oint_C g(\zeta) \dif\zeta
+ \oint_{C_\varepsilon} g(\zeta) \dif\zeta
= 0

```

We now turn our focus to the contour integral on $C_\varepsilon$.
Exploiting the fact that $f$, we can write

```{math}

g(\zeta) & = \frac{f(\zeta)}{\zeta - z}\\& = \frac{1}{\zeta - z}(
f(z) + f^\prime(z) (\zeta - z) + \psi(\zeta)
) \\& = \frac{f(z)}{\zeta - z} + \left[
f^\prime(z) + \frac{\psi(\zeta)}{\zeta - z}\right]
```

where $\frac{\psi(\zeta)}{\zeta - z} \to 0$ as $\zeta \to z$.
Note that the term $f^\prime(z) + \frac{\psi(\zeta)}{\zeta - z}$ is bounded
in a sufficiently small neighborhood of $z$.
Therefore, as $\varepsilon \to 0$, $\oint_{C_\varepsilon} f^\prime(\zeta) + \frac{\psi(\zeta)}{\zeta - z} \dif \zeta \to 0$.
Hence, the only $\frac{f(z)}{\zeta - z}$ will contribute to
the integral as $\varepsilon \to 0$.
Let the negatively oriented
circle $C_\varepsilon$ be the parametrized by $\zeta(t) = z + e^{i t}$
where $t$ goes from $2\pi$ to $0$.
We have

```{math}
\oint_{C_\varepsilon}\frac{f(z)}{\zeta - z}\dif\zeta& = f(z) \oint_{2 \pi}^{0}\frac{1}{e^{i t}} i e^{i t}\dif t \\& = -f(z) \oint_{0}^{2 \pi} i \dif t \\& = - 2 \pi i f(z)

```

In summary,

```{math}
:label: eq:11
\lim_{\varepsilon \to 0}\oint_{C_\varepsilon} g(\zeta) \dif\zeta = - 2 \pi i f(z)

```

Letting $\varepsilon \to 0$ in {eq}`eq:10` and plugging in {eq}`eq:11`,
we obtain

```{math}
\oint_C g(\zeta) \dif\zeta - 2 \pi i f(z) = 0

```

which is exactly what we wanted to show.

````

````{prf:corollary} 
:label: eq:12

If $f$ is a holomorphic function in $\Omega$,
then $f$ is complex differentiable infinitely many times
in $\Omega$.
Moreover, if $D \subseteq \Omega$
is disk whose closure $\overline{D}$ is also contained in $\Omega$,
then the $n$-th derivative of $f$ is given by

```{math}
:label: eq:12

f^{(n)}(z) = \frac{n!}{2 \pi i}\oint_C \frac{f(\zeta)}{(\zeta - z)^{n+1}}\dif\zeta, \quad\forall z \in D

```

where $C = \partial D$ is the positively oriented circle boundary of $D$.

````

````{prf:proof}

We shall prove by induction on $n$.
The induction hypothesis is
that $f$ has $n$-th derivative everywhere in $\Omega$
and it is given by {eq}`eq:12` for all $n \in \N^\ast$.

\noindent **Base Case:**  The conclusion immediately follows
from {prf:ref}`thm:1` when $n=1$.

\noindent **Inductive Step:**  Assume {eq}`eq:12` holds
for $n=k$. We will show that it also holds for $n=k+1$.
By the induction hypothesis, now it is given that $f$ has $k$-th order derivative
everywhere in $\Omega$ and the derivative is given by {eq}`eq:12`.

Pick a closed disk $\overline{D} \subseteq \Omega$ and a point $z$ in it.
By the definition of complex derivatives, we consider the quotient

```{math}
:label: eq:13
\frac{f^{(k)}(z+h) - f^{(k)}(z)}{h}
= \frac{k!}{2 \pi i}\cdot\frac{1}{h}\oint_C f(\zeta) \left(\frac{1}{(\zeta - z - h)^{k+1}} - \frac{1}{(\zeta - z)^{k+1}}\right)\dif\zeta
```

Using the formula

```{math}

A^m - B^m = (A - B) \sum_{j=0}^{m-1} A^{m-j-1} B^j

```

the term in the integrand of {eq}`eq:13` can be simplified to

```{math}
:label: eq:14
\frac{1}{(\zeta - z - h)^{k+1}} - \frac{1}{(\zeta - z)^{k+1}}& = \left(\frac{1}{\zeta - z - h} - \frac{1}{\zeta - z}\right)\sum_{j=0}^{k}\frac{1}{(\zeta - z - h)^{k-j} (\zeta - z)^j}\nonumber\\& = \frac{h}{(\zeta - z - h)(\zeta - z)}\sum_{j=0}^{k}\frac{1}{(\zeta - z - h)^{k-j} (\zeta - z)^j}
```

Substituting {eq}`eq:14` into {eq}`eq:13` gives

```{math}
:label: eq:15
\frac{f^{(k)}(z+h) - f^{(k)}(z)}{h}
= \frac{k!}{2 \pi i}\oint_C f(\zeta)
\frac{1}{(\zeta - z - h)(\zeta - z)}\sum_{j=0}^{k}\frac{1}{(\zeta - z - h)^{k-j} (\zeta - z)^j}\dif\zeta
```

Now, taking letting $h \to 0$ on both sides of {eq}`eq:15`,
we observe that $(\zeta - z - h) \to (\zeta - z)$.


:::{note}

Here, we will interchange the order of $\lim_{h \to 0}$ and $\oint_C$.
One should verify that this is indeed allowed and
the limit on the right-hand side of {eq}`eq:15` exists.
The approximation

```{math}
\abs{\frac{1}{(z+h)^p} - \frac{1}{z^p}}\leq\abs{h}\frac{p 2^p}{\abs{z}^{p+1}},
\quad p \in\N^\ast\text{ and $h$ is sufficiently small}
```

maybe helpful.

:::

Hence, {eq}`eq:15` yields

```{math}
\lim_{h \to 0}\frac{f^{(k)}(z+h) - f^{(k)}(z)}{h}
= \frac{k!}{2 \pi i}\oint_C f(\zeta)
\frac{1}{(\zeta - z)^2}\frac{k+1}{(\zeta - z)^{k}}\dif\zeta
= \frac{(k+1)!}{2 \pi i}\oint_C
\frac{f(\zeta)}{(\zeta - z)^{k+2}}\dif\zeta
```

which exactly {eq}`eq:12` when $n=k+1$.
And we can show that $f$ has $k+1$-th order derivative everywhere in $\Omega$.
This completes the proof.

````

````{prf:theorem} 
:label: thm:1

Suppose $f$ is holomorphic in an open set $\Omega$, and $D$ is an open disk
centered at $z_0$ whose closure is contained in $\Omega$. Then $f$ has a power
series expansion at $z_0$ in the form

```{math}
:label: eq:1

f(z) = \sum_{n=0}^\infty\frac{f^{(n)}(z_0)}{n!}(z - z_0)^n \quad\forall z \in D

```

````

````{prf:theorem} Liouville's Theorem
:label: thm:2

Let $f$ be an entire function.

````

````{prf:theorem} Fundamental Theorem of Algebra
:label: thm:3

Every polynomial with degree greater than $0$ with complex coefficients has a
root in $\C$.

````

````{prf:proof}

Let polynomial $p(z)$ be given by

```{math}

p(z) = a_n z^n + \cdots a_1 z + a_0

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
\frac{p(z)}{z^n} = a_n + \frac{a_{n-1}}{z} + \cdots + \frac{a_1}{z^{n-1}} + \frac{a_0}{z^n}
```

Note that when $\abs{z} \to \infty$, the modulus of the quotient $p(z) / z^n$ will
tend to $\abs{a_n}$.
This implies that there exists $R > 0$ such that

```{math}
:label: eq:2
\abs{\frac{p(z)}{z^n}} > \frac{\abs{a_n}}{2}
```

whenever $\abs{z} > R$. Rearranging {eq}`eq:2`, we have

```{math}
\abs{\frac{1}{p(z)}} < \frac{2}{\abs{a_n}}\cdot\frac{1}{\abs{z}^n} < \frac{2}{\abs{a_n} R^n}\quad\text{if }\abs{z} > R

```

The above inequality shows $1 / p(z)$ is bounded outside the disk $D$ centered
at $0$ with radius $R$.

For points inside the closed disk $\overline{D}$, since function $\abs{1 / p(z)}$ is
continuous and $\overline{D}$ is compact, $\abs{1 / p(z)}$ attains its maximum $M$ on $\overline{D}$.

Therefore, we see that $1 / p(z)$ is indeed bounded on entire complex plane $\C$.
By Liouville's theorem {prf:ref}`thm:2`, $1 / p(z)$ is constant, which leads to a
contradiction since polynomials with degree greater than $0$ are non-constant.



:::{note}

The last assertion that polynomials with degree greater than $0$ are
non-constant seem evident. But the reader should still prove it. See {prf:ref}`pro:1`.
And the proof is not that trivial.

:::

````

````{prf:proposition} 
:label: pro:1

Polynomials with degree greater than $0$ are non-constant.

````

Now, we have proved polynomial $p(z)$ must have one root. Using mathematical
induction we can show that it actually has $n$ roots, and can be factorized as

```{math}

p(z) = a_n (z^n - z_1) (z^n - z_2) \cdots(z^n - z_n)

```

````{prf:corollary} 

Every polynomial $p(z) = a_n z^n + \cdots + a_1 z + a_0$ of degree $n \geq 1$ with
complex coefficients has exactly $n$ roots in $\C$. If these $n$ roots are
denoted by $z_1, \ldots, z_n$, then $p(z)$ can be factorized as

```{math}

p(z) = a_n (z^n - z_1) (z^n - z_2) \cdots(z^n - z_n)

```

````

````{prf:proof}

We shall prove by induction.

\noindent **Base Case:**  Suppose $n = 1$, then $p(z) = a_1 z + a_0$($a_1 \neq 0$). Setting $p(z) = 0$, we solve that $z = -a_0 / a_1$. Therefore, $z_1 = -a_0 / a_1$ is the only root of $p(z)$, and we can write $p(z) = a_1(z - z_1)$.

\noindent **Inductive Step:**  Assume this corollary holds for $n = k$, we need to show that it also holds for $n = k + 1$.
By the Fundamental Theorem of Algebra {prf:ref}`thm:3`, there exists one root $z_1$ for $p(z)$.
We want to show that $p(z)$ has a factor $(z - z_1)$.
Let $\tilde{p}(z) = p(z + z_1)$.
Note that $\tilde{p}(z)$ is also a polynomial of degree $k + 1$.
Write

```{math}
:label: eq:3
\tilde{p}(z) = b_{k+1} z^{k+1} + \cdots + b_1 z + b_0

```

Because $z_1$ is a root of $p(z)$, we have $\tilde{p}(0) = p(z_1) = 0$. Substituting $z=0$ into {eq}`eq:3` yields $b_0 = 0$.
Therefore, we can write

```{math}
\tilde{p}(z) = z (b_{k+1} z^{k} + \cdots b_2 z + b_1)

```

Then, we recover the expression of $p(z)$ from $\tilde{p}(z)$.
Note that $p(z) = \tilde{p}(z - z_1)$.
Hence,

```{math}

p(z) = (z - z_1) \underbrace{(b_{k+1} z^{k} + \cdots b_2 z + b_1)}_{\text{a polynomial of degree $k$}}
= (z - z_1) q(z)

```

Now, we may apply the induction hypothesis on $q(z)$.
We have

```{math}

p(z) & = (z - z_1) [c (z - z_2) \cdots(z - z_{k+1})]\\& = c (z - z_1) \cdots(z - z_{k+1})

```

And we realized that $c$ is exactly $a_{k+1}$ since it is the coefficient of $z^{k+1}$.
Therefore, we have shown

```{math}
:label: eq:4

p(z) = a_{k+1}(z - z_1) \cdots(z - z_{k+1})

```
{eq}`eq:4` tells us that $z_1, \ldots, z_{k+1}$ are roots of $p(z)$.
Moreover, $p(z)$ cannot have any other roots. To see this, suppose $w \neq z_j \ \forall j=1, \ldots, k+1$. Then, substituting $z = w$ in {eq}`eq:4`, we see that $p(w) \neq 0$ since each factor is nonzero.

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

f(z) = \sum_{n=0}^\infty a_n (z - z_0)^n \quad\forall z \in D_r(z_0)

```

Assume $f$ is not constantly zero.
Then we can find the first nonzero coefficient $a_m$ in the expansion.
Write

```{math}
:label: eq:5

f(z) & = a_m(z - z_0)^m + \sum_{k=1}^\infty a_{m+k}(z - z_0)^{m+k}\nonumber\\& = a_m(z - z_0)^m \left[
1 + \sum_{k=1}^\infty\frac{a_{m+k}}{a_m}(z - z_0)^{k}\right]
```

Note that the term $\sum_{k=1}^\infty \frac{a_{m+k}}{a_m}  (z - z_0)^{k}$ is a continuous function that vanishes at $z_0$.
Hence, we may find a sufficiently small neighbourhood $N$ of $z_0$ such that $1 + \sum_{k=1}^\infty \frac{a_{m+k}}{a_m}  (z - z_0)^{k}$ is nonzero in $N$.
By the given condition, there exists a point $z_j$ in the sequence such that $z_j \neq z_0$ and $z_j \in N$.
Plugging $z_j$ into {eq}`eq:5`, we have

```{math}

0 = f(z_j) = a_m(z_j - z_0)^m \left[
1 + \sum_{k=1}^\infty\frac{a_{m+k}}{a_m}(z_j - z_0)^{k}\right]
```

This leads to a contradiction since the right-hand side is nonzero.
Therefore, $f$ is constantly zero in the disk $D_r(z_0)$.

Next, we will show that $f$ is zero in the entire set $\Omega$ by exploiting the fact that $\Omega$ is connected.
Let set $U$ be defined as the interior of the set of all points at which $f$ vanishes, i.e., $U = [f^{-1}(\{0\})]^\circ$
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