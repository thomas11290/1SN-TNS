# Introduction


```{prf:definition} Traitement numérique du Signal

<span style="color:rgba(var(--pst-color-link),1)"> **Le traitement numérique du signal désigne l'ensemble des opérations effectuées sur un signal numérique à traiter, défini à des instants discrets par un nombre fini de valeurs, pour fournir un autre signal numérique, également défini à des instants discrets par un autre nombre fini de valeurs, représentant le signal traité.** </span>

```

Travailler avec des signaux et des traitements numériques présente un certain nombre d'avantages. Les principaux étant :

- Une plus grande robustesse vis à vis du bruit (dans le cadre des transmissions).

- Une meilleure stabilité et reproductibilité des équipements. Il est, en effet, possible, en numérique, de construire des systèmes identiques, comme il est possible d'anticiper les dérives temporelles liées aux conditions extérieures (température, pression...). Les marges à prendre en compte au moment de la conception des équipements sont donc réduites.

- La possibilité de définir des fonctions nouvelles, notamment des fonctions évoluant dans le temps tel que, par exemple, le filtrage adaptatif, mais également des fonctions de compression, de codage correcteur d'erreurs...

Le nombre fini de valeurs représentant le signal numérique à traiter peut être issu d'un processus numérique (on dit aussi discret) ou provenir d'un signal analogique (représentant une grandeur physique qui évolue dans le temps) qui a été numérisé (on dit aussi discrétisé). 

```{prf:definition} Numérisation du Signal
<span style="color:rgba(var(--pst-color-link),1)"> **Pour numériser un signal analogique (défini à tout instant par des valeurs réelles) deux opérations sont nécessaires : une opération d'échantillonnage (discrétisation dans le domaine temporel) et une opération de quantification (discrétisation dans le domaine des amplitudes).**</span>
```

Nous allons considérer, dans la suite, des signaux déterministes et regarder plus en détail les opérations d'échantillonnage et de quantification. Les résultats obtenus restent valables pour des signaux aléatoires. Seul le formalisme utilisé pour les démonstrations changerait en faisant appel aux équations normales.












