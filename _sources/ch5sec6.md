## Exercices

Les corrections se trouvent dans le poly d'exercices et problèmes résolus.

```{exercise} Convergence
\label{exercice_2_TZ}

Soit un réel $a\in ]0,1[$ et $u(n)$ l'échelon de Heaviside (ou échelon unité) :

$$
u(n) = \left\{
\begin{array}{rl}
1 & \mbox{pour } n>0\\
0 & \mbox{pour } n\leq 0. \\
\end{array} \right. \;
$$

1. Déterminer la transformée en z du signal $x(n) = a^n u(n)$, avec $|a|< 1$,  et préciser avec soin la région de convergence de $X(z)$.

2. Déterminer la transformée en z du signal $y(n) = -a^n u(-n-1)$, avec $|a|< 1$, et préciser avec soin la région de convergence de $Y(z)$.

3. Soit $b$ un réel tel que $b>a$ et $|b|< 1$. On considère un système de fonction de transfert :

    $$
    H(z)=\frac{1}{\left(1-az^{-1}\right)\left(1-bz^{-1}\right)}
    $$

    Déterminer la réponse impulsionnelle $h(n)$ du système dans les trois cas suivants :
    
    - la région de convergence de $H(z)$ est $|z|<a$,
    
    - la région de convergence de $H(z)$ est $a<|z|<b$,
    
    - la région de convergence de $H(z)$ est $|z|>b$.

```

```{exercise} Fonction de transfert d'un système linéaire invariant dans le temps

Soit le système d'entrée $x(n)$ et de sortie $y(n)$ défini par l'équation récurrente suivante : $y(n) - a y(n-1) = x(n)$, avec $|a|< 1$.

1. Soit $x(n) = b^n u(n)$ avec $|b|< 1$. Déterminer sa transformée en z, ainsi que son domaine d'existence.

2. Déterminer la réponse du système à l'entrée $x(n)$ définie à la question précédente, en supposant que le système est causal.

3. Déterminer la fonction de transfert, ainsi que la réponse impulsionnelle du système.
