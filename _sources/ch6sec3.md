## Réalisabilité d'un filtre numérique

<span align="center" style="color:rgba(var(--pst-color-link),1)"> **Un filtre numérique est réalisable si les trois conditions suivantes sont respectées :**</span>

- <span align="center" style="color:rgba(var(--pst-color-link),1)"> **Le filtre doit être causal.**</span> Cette condition se décline sur la réponse impulsionnelle du filtre de la manière suivante : $h(n)=0$ pour $n<0$.

- <span align="center" style="color:rgba(var(--pst-color-link),1)"> **Le filtre doit être stable :**</span> 

    pour toute entrée bornée, la sortie doit être bornée.  Cette condition se décline sur la réponse impulsionnelle du filtre de la manière suivante : $\sum_{n=-\infty}^{+\infty}\left|h(n)\right|<\infty$. Nous verrons par la suite, pour les filtres rationnels, que cette condition conduit à une condition portant sur les pôles de la fonction de transfert du filtre.

- <span align="center" style="color:rgba(var(--pst-color-link),1)"> **La réponse impulsionnelle du filtre, $h(n)$, doit être réelle.**</span> 
