 ## Systèmes à temps discret

```{prf:definition} Systèmes numériques

**Un système à temps discret, ou système numérique, est un opérateur $T$ qui transforme un signal discret, $x$, placé à l'entrée du système (signal d'entrée ou de commande) en un signal discret, $y$, en sortie du système (signal de sortie ou réponse) : $y=T(x)$.**
```    
    
### Types de systèmes à temps discret
        
```{prf:definition} Systèmes linéaires

Un système à temps discret défini par l'opérateur $T$ est dit linéaire si :

$$
T\left(\alpha x_1 + \beta x_2 \right)=\alpha T\left(x_1\right)+\beta T\left(x_2\right)
$$
        
$\forall$ $x_1$, $x_2$ signaux d'entrée du système et $\alpha$, $\beta$ $\in \mathbb{C}$.

```
```{prf:definition} Systèmes sans mémoire

Un système à temps discret est dit sans mémoire si sa sortie à l'instant $n$ ne dépend que de son entrée à l'instant $n$. 
        
Dans tous les autres cas le système sera dit à mémoire, mémoire qui peut être finie (la sortie à l'instant $n$ dépend uniquement de l'entrée aux instants $n$ à $n-N$) ou infinie (la sortie à l'instant $n$ dépend de toutes les valeurs passées de l'entrée).
```       
```{prf:definition} Systèmes causaux

Un système à temps discret est dit causal si sa sortie à l'instant $n$ ne dépend que des valeurs passées de son entrée (instants $m \leq n$). 

Un système à temps discret est dit anticausal si sa sortie à l'instant $n$ ne dépend que des valeurs futures de son entrée (instants $m > n$).
```
```{prf:remark}

- Un système peut être constitué d'une partie causale et d'une partie anticausale.

- Nous verrons par la suite que la sortie d'un système peut également dépendre de ses valeurs passées (présence d'une boucle de récation).

- Un système numérique sera toujours causal à un retard près.

```        
```{prf:definition} Systèmes invariants dans le temps

Un système à temps discret défini par l'opérateur $T$ est dit invariant dans le temps (ou invariant par translation temporelle) si :

$$
y(n-n_0)=T\left(x(n-n_0) \right) \; \text{pour }  y(n)=T\left(x(n) \right)
$$

$n_0$ représentant un retard de $n_0$ échantillons.
```       
```{prf:definition} Systèmes stables

Un système à temps discret est stable si à toute entrée bornée correspond une sortie bornée : $|x(n)|<\infty \Rightarrow |y(n)|< \infty$ (condition BIBO = Borned Input Borned Output). 
```

### Exemples de systèmes à temps discret
        
```{prf:example} Introduction d'un retard

Un système numérique introduisant un retard de $n_0$ échantillons est défini par $y(n)=x(n-n_0)$ ($x(n+n_0)$ représente une avance).
```

```{prf:example} Calcul d'une valeur cumulée

Un système numérique calulant une valeur cumulée est défini par $y(n)=\sum_{k=-\infty}^n x(k)$.
```      
```{prf:example} Calcul d'une valeur moyenne

Un système numérique peut calculer une valeur moyenne, par exemple entre échantillons voisins : $y(n)=\frac{1}{3}\left(x(n-1)+x(n)+x(n+1)\right)$.
``` 

```{prf:example} Filtres numériques

Un système numérique peut réaliser un filtrage linéaire du signal d'entrée. Une équation récurrente lie alors entrée et sortie, par exemple : $y(n)=x(n)+0.5x(n-1)+0.3x(n-2)$.
```

```{note}

**Les filtres numériques font l'objet d'un chapitre complet par la suite (chapitre $6$).**
       
```
        
## Etude des systèmes à temps discret : transformée en $z$

```{note}
**Tout comme la transformée de Laplace permet l'étude des systèmes analogiques linéaires invariants dans le temps, la transformée en $z$ va permettre l'étude des systèmes numériques linéaires invariants dans le temps.**

**Les principaux éléments concernant cette transformée sont donnés dans un des chapitres suivant (chapitre $5$) et elle est utilisée dans le chapitre $6$ pour étudier les filtres numériques linéaires invariants dans le temps.**
```
