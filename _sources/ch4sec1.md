## Estimateurs "de base" : corrélogramme, périodogramme
        
### Définitions
        
La manière la plus naturelle d'estimer la densité spectrale de puissance du signal $x$ est d'utiliser sa définition en utilisant l'estimée de la fonction d'autocorrélation et la transformée de Fourier discrète :
        
```{prf:definition} Corrélogramme       
        
$$
\widehat{S}_{x}(n)=TFD\left[\widehat{R}_x(k)\right]=\sum_{k=0}^{N-1} \widehat{R}_x(k) e^{-j 2 \pi \frac{kn}{N}}, \; n=0,...,N-1
$$

```        
        
On appelle cet estimateur le corrélogramme, biaisé ou non biaisé selon que l'on utilise un estimateur biaisé ou non biaisé pour l'estimation de la fonction d'autocorrélation. Le corrélogramme utilisant un estimateur biaisé pour la fonction d'autocorrélation est également appelé périodogramme et est donné par l'expression suivante, en notant $X(n)$ la TFD d'une réalisation du signal $x$ (tableau de $N$ points).

```{prf:definition} Périodogramme
        
$$
\widehat{S}_{x}(n)=\frac{1}{N}|X(n)|^{2} \; \left(=\frac{1}{N} TFD\left[x(k) \ast x^*(-k)\right]\right)
$$

```
Notons que cette définition de la DSP par périodogramme permet un lien plus direct avec le cadre des signaux déterministes : la densité spectrale de puissance ou d'énergie est en effet proportionnelle au module de la transformée de Fourier du signal au carré pour les signaux déterministes.

### Problèmes posés par ces estimateurs "de base"

On constate qu'en moyenne les estimateurs de la fonction d'autocorrélation se comportent comme la fonction d'autocorrélation théorique multipliée par une fenêtre (rectangulaire pour l'estimateur non biaisé, triangulaire pour l'estimateur biaisé) :

\begin{align*}
\mathbb{E}\left[\widehat{R}_x(k)\right] &= \Pi_N(k) R_{x}(k) \quad \text{dans le cas d'un estimateur non biaisé.}\\
                    &= \frac{N-|k|}{N}R_{x}(k) \quad \text{dans le cas d'un estimateur biaisé.}
\end{align*}
        
Ce qui donne pour l'estimée de la densité spectrale de puissance :

$$
\mathbb{E}\left[\widehat{S}_{x}(n)\right]= S_{x}(n) \ast W(n)
$$

où $W(n)$ représente la transformée de Fourier de la fenêtre. Les estimateurs de base de la DSP possèdent donc un biais convolutif avec :

- $W(n)=\frac{\sin\left(\pi n\right)}{\sin\left(\frac{\pi n}{N}\right)}$ dans le cas de l'utilisation d'un estimateur non biaisé pour la fonction d'autocorrélation.

- $W(n)=\left(\frac{\sin\left(\pi n\right)}{\sin\left(\frac{\pi n}{N}\right)}\right)^2$ (noyau de Fejer) dans le cas de l'utilisation d'un estimateur biaisé pour la fonction d'autocorrélation.

et leur variance ne tend pas vers $0$ quand $N$ tend vers l'infini. Il est difficile d'établir la variance de ces estimateurs pour un signal de distribution quelconque. Cette variance est donc calculée dans le cas particulier du bruit blanc et généralisée par approximation aux autres signaux (voir ref $\left[2\right]$, page $258$). <span style="color:rgba(var(--pst-color-link),1)"> ** Ces estimateurs de la DSP (corrélogramme, périodogramme) ne sont donc pas consistants </span>. De plus, l'estimateur utilisant une estimation non biaisée pour la fonction d'autocorrélation peut donner des valeurs négatives pour la DSP.
