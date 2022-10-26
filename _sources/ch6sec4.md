## Classification des filtres numériques rationnels : RIF, RII

**<span align="center" style="color:rgba(var(--pst-color-link),1)">Les filtres rationnels sont divisés en deux catégories :</span>**

**<span align="center" style="color:rgba(var(--pst-color-link),1)">- Les filtres rationnels dits "à réponse impulsionnelle infinie" (ou RII),</span>**

**<span align="center" style="color:rgba(var(--pst-color-link),1)">- Les filtres rationnels dits "à réponse impulsionnelle finie" (ou RIF).</span>**

### Filtres à réponse impulsionnelle infinie (RII)

La définition vue précédemment pour les filtres numériques rationnels définit en réalité les filtres rationnels dits "à réponse impulsionnelle infinie" (RII, ou IIR en anglais) :

```{prf:definition} Définition des filtres RII par leur fonction de transfert

$$
H(z) =\frac{Y(z)}{X(z)}=\frac{\sum_{k=0}^{N-1} b_k z^{-k}}{\sum_{k=0}^{M-1} a_k z^{-k}}
$$

```
En utilisant le fait que $TZ^{-1}\left[z^{-k}X(z)\right]=x(n-k)$ et en fixant $a_0$ à $1$ (par analogie avec les filtres analogiques), cette définition par la fonction de transfert en $z$ conduit, dans le domaine temporel, à une équation récurrente (là où nous avons une équation différentielle pour les filtres analogiques) :

```{prf:definition} Définition des filtres RII dans le domaine temporel 

$$
y(n) =-\sum_{k=1}^{M-1} a_k y(n-k) + \sum_{k=0}^{N-1} b_k x(n-k).
$$

```
On parle de filtres "à réponse impulsionnelle infinie" car, ainsi définis, ils présentent une réponse impulsionnelle qui s'auto-entretient :

$$
h(n) =-\sum_{k=1}^{M-1} a_k h(n-k), \; \textrm{pour} \; n\geq N
$$

Chaque nouvelle valeur ne dépend que des valeurs passées et on peut donc ainsi obtenir un nombre infini de valeurs (ou coefficients) pour la réponse impulsionnelle.

On dit encore <span align="center" style="color:rgba(var(--pst-color-link),1)"> **filtres récursifs**</span> car ce sont des filtres qui possèdent une boucle de réaction, boucle de réaction qui permet d'obtenir cette réponse impulsionnelle qui s'auto-entretient.\

<span align="center" style="color:rgba(var(--pst-color-link),1)">**Un filtre numérique rationnel de type RII est donc défini par deux vecteurs de coefficients, $A=\left[a_0 \; a_1 ... \; a_{M-1}\right]$ et $B=\left[b_0 \; b_1 ... \; b_{N-1}\right]$, et peut être implanté sous Matlab de la manière suivante : *y=filter(B,A,x)}*, si *x* représente le signal à filtrer, *y* le signal filtré et *B* et *A* les tableaux de coefficients définissant le filtre à utiliser.**</span>

## Filtres à réponse impulsionnelle finie (RIF)

On définit les filtres numériques rationnels à "Réponse Impulsionnelle Finie" (RIF, FIR en anglais) ou<span align="center" style="color:rgba(var(--pst-color-link),1)">**filtres non récursifs**</span>, de la manière suivante, en supprimant tout bonnement la boucle de réaction.

```{prf:definition}  Définition des filtres RIF par leur fonction de transfert
$$
H(z) =\frac{Y(z)}{X(z)}=\sum_{k=0}^{N-1} b_k z^{-k}
$$
```

Ce qui conduit dans le domaine temporel à :

```{prf:definition} Définition des filtres RIF dans le domaine temporel
$$
y(n) =\sum_{k=0}^{N-1} b_k x(n-k).
$$

```
Les coefficients $b_k$ définissant le filtre RIF sont donc les échantillons prélevés sur la réponse impulsionnelle :

$$
h(n) =\sum_{k=0}^{N-1} b_k \delta(n-k)=b_n, \; n=0,...,N-1
$$

car

$$
\delta(n-k) = \left\{
\begin{array}{rl}
1 & \mbox{pour } n=k\\
0 & \mbox{pour } n\neq k. \\
\end{array} \right. \;
$$

Un des intérêts fondamentaux de ces filtres est qu'ils ne posent pas de problèmes d'instabilité. Ils présentent également très simplement un TPG constant, la condition étant que leur réponse impusionnelle soit paire ou impaire, comme nous le verrons par la suite. 

<span align="center" style="color:rgba(var(--pst-color-link),1)">**Les filtres RIF ne sont définis que par un vecteur de coefficients, $B=\left[b_0 \; b_1 ... \; b_{N-1}\right]$, et peuvent être implantés sous Matlab de la manière suivante : *y=filter(B,1,x)*, si *x* représente le signal à filtrer, *y* le signal filtré et *B* le tableau de coefficients définissant le filtre à utiliser.**</span>
