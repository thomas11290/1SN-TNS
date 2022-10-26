## Outils de traitement du signal à numériser
    
    
Un certain nombre d'outils de traitement du signal sont définis pour des signaux analogiques (signaux définis à chaque instant par des valeurs réelles) :

- La <span style="color:rgba(var(--pst-color-link),1)">**transformée de Fourier**</span> et la <span style="color:rgba(var(--pst-color-link),1)">**densité spectrale de puissance**</span>, permettant de visualiser la représentation fréquentielle des signaux pour en extraire de l'information (exemples : bande occupée par le signal en vue d'une transmission, détection de défauts apparaissant comme des composantes fréquentielles particulières).

- Les <span style="color:rgba(var(--pst-color-link),1)">**fonctions d'auto et d'inter corrélation**</span>, permettant d'accéder à la densité spectrale de puissance du signal, mais également utiles pour d'autres fonctions (exemple : extraction d'un signal dans du bruit).

- Les <span style="color:rgba(var(--pst-color-link),1)">**filtres**</span>, permettant de construire et de modifier des signaux (exemples : modulation, réduction du bruit, suppression de certaines composantes fréquentielles).  
  

```{admonition} <span style="color:rgba(var(--pst-color-link),1)">**Objectif de la partie numérique du cours de traitement du signal**</span>
:class: note

**Il va être nécessaire de réaliser un certain nombre d'approximations, d'estimations pour passer des outils défnis de manière théorique, sur des signaux analogiques, aux outils que l'on va être capable d'implanter en numérique.**

**L'objectif du cours de traitement numérique du signal est de présenter, d'expliquer ces modifications et leurs impacts sur les résultats attendus afin d'être capable d'utiliser correctement les outils numériques et d'analyser correctement les résultats obtenus.**
```