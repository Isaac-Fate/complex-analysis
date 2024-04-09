# Local Existence of Primitives and Cauchy's Theorem in a Disk

````{prf:theorem} 

 If $f$ is holomorphic in an open disk $D \subseteq \CC$, then $f$ has a primitive there.

````

````{prf:proof}

 Without loss of generality, we may assume the disk $D$ is centered at the origin.
 If it is centered at $z_0$,
 we can translate the disk to the origin and define $f(z) = f(z + z_0)$.
 Then we find a primitive for $f$, say $F$.
 The primitive for $f$ is then given by $F(z) = F(z - z_0)$.

 Assume $D$ is centered at the origin,
 we are going to construct a primitive $F$ for $f$ in $D$
 using a contour integral.
 For any point $z \in D$,
 curve $\gamma_z$ is taken to be the horizontal line segment
 from $0$ to $\RE z$
 followed by the vertical segment from $\RE z$ to $z$.
 Note that $\gamma_z$ is indeed contained in $D$.
 Let function $F$ be defined by
 
```{math}
:label: eq:6

 F(z) = \int_{\gamma_z} f(w) \dif w
 
```

 We will show $F$ is indeed a primitive for $f$ in $D$.
 Hence, we need to estimate the quotient $\frac{F(z+h) - F(z)}{h}$ when $h \to 0$.

 This invites us to consider the contour integral of $f$ along curve $\gamma_{z_h} - \gamma_z$. As illustrated in {numref}`fig:1`,
 by adding a rectangle and a triangle without change the value of the contour integral
 due to {prf:ref}`thm:4` and {prf:ref}`cor:1`, one may verify that
 
```{math}

 F(z+h) - F(z) = \int_{\gamma_{z+h} - \gamma_z} f(w) \dif w
 = \int_\eta f(w) \dif w
 
```

 where $\eta$ is the line segment from $z$ to $z+h$.

 ```{figure} /figures/adding-a-rectangle-and-a-triangle.png
---
name: fig:1
---
Construction of curve $\eta$ by adding a rectangle and a triangle to the curve $\gamma_{z+h} - \gamma_z$.
```

````
