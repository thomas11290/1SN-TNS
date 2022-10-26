## Stabilité des filtres numériques rationnels récursifs (RII)

### Condition de stabilité

En supposant, dans l'expression de la fonction de transfert définissant les filtres rationnels de type RII, que $N<M$ et en réalisant une décomposition en éléments simples on obtient :

$$
H(z) =\frac{\sum_{k=0}^{N-1} b_k z^{-k}}{\sum_{k=0}^{M-1} a_k z^{-k}}= \sum_{k=0}^{M-1} \frac{A_k}{1-p_k z^{-1}}
$$

Ce qui donne par transformée en z inverse (solution causale) :

$$
h(n) =\sum_{k=0}^{M-1} A_k p_k^{n} u(n),
$$

où $u(n)$ représente la fonction de Heaviside :

$$
    u(n) = \left\{
    \begin{array}{rl}
    1 & \mbox{pour } n>0\\
    0 & \mbox{pour } n\leq 0. \\
    \end{array} \right. \;
$$

Afin d'assurer la stabilité du système il faut que $\sum_{n=-\infty}^{+\infty}\left|h(n)\right|$ soit borné. 

Or

$$
\sum_{n=-\infty}^{+\infty}\left|h(n)\right| \leq \sum_{n=-\infty}^{+\infty}\sum_{k=0}^{M-1} \left|A_k\right| \left|p_k\right|^n u(n)
$$

$$
\sum_{n=-\infty}^{+\infty}\left|h(n)\right| \leq \sum_{k=0}^{M-1} \left|A_k\right| \sum_{n=0}^{+\infty}\left|p_k\right|^n

$$

$$
\sum_{n=-\infty}^{+\infty}\left|h(n)\right| \leq \sum_{k=0}^{M-1} \left|A_k\right| \frac{1}{1-\left|p_k\right|} \; \text{si} \; \left|p_k\right|<1
$$

$$\sum_{n=-\infty}^{+\infty}\left|h(n)\right| \; \text{sera donc borné, et le système stable, si} \; \left|p_k\right|<1 \; \forall k$$


```{prf:definition} Condition de stabilité sur $H(z)$
Un filtre numérique rationnel de type RII est stable si tous les pôles (racines du dénominateur) de sa fonction de transfert $H(z)$ sont de modules inférieurs à $1$ (on dit souvent dans le cercle unité $\Leftrightarrow$ cercle de rayon $1$).
```

Rappelons qu'il existe une condition similaire pour les filtres analogiques : un filtre analogique est stable si les pôles de sa fonction de transfert $H(p)$ sont à parties réelles négative.

```{prf:remark}


- Si tous les zéros (racines du numérateur) de la fonction de transfert du filtre, $H(z)$, sont de modules inférieurs à $1$ (dans le cercle unité), le filtre est dit à minimum de phase. Ce type de filtres est très intéressant car il est d'inverse stable, ce qui est une propriété recherchée dans beaucoup d'applications.

- La position des poles dans le cercle unité est également intéressante. Pour un filtre stable résonnant, on montre (voir exercice $4$) que plus le module des pôles associés est proche de $1$, plus la résonance est forte. Lorsque, pour un filtre stable, les pôles sont proches du cercle unité, on sait qu'il faudra faire davantage attention aux effets de la quantification des coefficients du filtre qui pourraient amener les pôles à sortir de la zone de stabilité.

- Nous verrons par la suite (exercice $4$) qu'il est également possible de définir une zone de stabilité dans le plan des coefficients du filtre.

- Il existe des méthodes de conception de filtres numériques récursifs basées sur le placement des zéros et des pôles de leurs fonctions de transfert (voir références $\left[6\right]$ et $\left[7\right]$)

```