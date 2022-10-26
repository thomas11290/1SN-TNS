# Densité Spectrale de Puissance (DSP)

La Densité Spectrale de Puissance reflète la contribution de chaque fréquence à la puissance moyenne du signal. Elle permet de fournir une représentation fréquentielle aux signaux aléatoires pour lesquels nous ne pouvons calculer une transformée de Fourier (mais reste utilisable pour les signaux déterministes). Elle est donnée par la transformée de Fourier de la fonction d'autocorrélation du signal :

$$
    S_{x}(f)=TF\left[R_x(\tau)\right]
$$

Il est donc naturel d'envisager d'estimer en numérique la densité spectrale de puissance d'un signal aléatoire en prenant la TFD de l'estimation de sa fonction d'autocorrélation. On appelera cet estimateur l'estimateur "de base". Malheureusement cet estimateur "de base" s'avère ne pas être consistant : il est biaisé et sa variance ne tend pas vers $0$ lorsque l'on augmente la durée d'observation pour réaliser l'estimation. On définit donc des estimateurs de la DSP plus satisfaisants, à partir de cet estimateur "de base".