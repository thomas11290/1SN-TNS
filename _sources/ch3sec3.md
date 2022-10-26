## Quelques propriétés

### Symétrie Hermitienne

Comme c'est la cas à temps continu, la fonction d'intercorrélation numérique possède la propriété de symétrie hermitienne :

$$
\widehat{R}_{xy}(-k)=\widehat{R}^*_{xy}(k)
$$

Soit pour des signaux réels : $\widehat{R}_{xy}(-k)=\widehat{R}_{xy}(k)$. Cette propriété est intéressante car elle permet d'économiser la moitié du temps de calcul.

### Bornes

La fonction d'autocorrélation numérique est bornée par sa valeur en $0$ qui représente la puissance du signal :

$$
\widehat{R}_{x}(k)\leq \widehat{R}_{x}(0)=P_x

$$

$P_x=R_x(0)$ représentant la puissance du signal $x$. 

Mais aussi :

$$
\widehat{R}_{xy}(k)\leq \frac{1}{2}\left(\widehat{R}_{x}(0)+\widehat{R}_{y}(0)\right)
$$