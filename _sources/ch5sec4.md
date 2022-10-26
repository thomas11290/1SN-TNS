## Transformée en z inverse

### Définition


La transformée en $z$ inverse est définie par :

```{prf:definition} TZ inverse

$$
x(n)=\frac{1}{j 2 \pi}\int_{C^+}X(z)z^{n-1}dz, 
$$

où  $C^+$ est un  contour fermé inclu dans l'anneau de convergence.

```

```{prf:proof}

L'expression de la transformée en $z$ inverse découle directement du calcul de l'intégrale :

$$
J(n,k)=\int_{C^+} z^{n-k-1}dz
$$

A l'aide du théorème des résidus on montre :

$$J(n,k)=\left\{
              \begin{array}{ll}
                0, & \mathrm{ si }\; n \neq k; \\
                j 2 \pi, & \mathrm{ si }\; n = k.
              \end{array}
            \right.$$

On en déduit alors :

\begin{align*}
    \frac{1}{j 2 \pi}\int_{C^+}X(z)z^{n-1}dz&=\frac{1}{j 2 \pi}\int_{C^+}\left(\sum_{k=-\infty}^{+\infty}x(k)z^{-k}\right)z^{n-1}dz \\
    &=\frac{1}{j 2 \pi}\left(\sum_{k=-\infty}^{+\infty}x(k)\right)J(n,k)=x(n)
 \end{align*}
```

```{prf:remark}
il existe des tables de transformées en $z$ et transformées en $z$ inverse.
```

```{prf:remark} Rappel

Si $z_i$ est un pôle simple de g(z) :

$$
    Residu\left[g(z)\right]_{z=z_i}=\lim_{z \rightarrow z_i} (z-z_i)g(z)
$$

Si $z_i$ est un pôle d'ordre $\alpha$ de g(z) :

$$
    Residu\left[g(z)\right]_{z=z_i}=\frac{1}{(\alpha-1)!}\left[\frac{\partial^{\alpha-1}}{\partial z^{\alpha-1}}\left(g(z)(z-z_i)^{\alpha}\right)\right]_{z=z_i}
$$
```