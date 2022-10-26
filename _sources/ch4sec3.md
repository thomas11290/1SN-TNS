## Périodogramme cumulé (ou de Bartlett)

Cette méthode tire son nom du statisticien anglais M. S. Bartlett, qui a été le premier à la proposer. Pour calculer un périodogramme cumulé, le signal de $N$ points $x$ est divisé en $M$ parties : $x_i, \; i=1,...,M$ de $L=\frac{N}{M}$ points. Un périodogramme moyenné est alors effectué :
    
$$
\widehat{S}_{x}(n)=\frac{1}{LM}\sum_{i=1}^{M}|TFD\left[x_i(k)\right]|^{2},
$$

afin de diminuer la variance d'estimation de la DSP. La variance sera diminuée d'un facteur $M$ lorsque l'on moyenne $M$ périodogrammes indépendants.

L'inconvénient de cet estimateur va être l'augmentation du biais car le lobe central du noyau de Fejer est alors plus large ($2/L$ au lieu de $2/N$). De plus, on diminue la résolution du spectre obtenu ($L$ points calculés sur $F_e$ au lieu de $N$).