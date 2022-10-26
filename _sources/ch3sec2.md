## Calcul dans le domaine fréquentiel

En partant de l'expression 

$$R_{xy}(k)=\sum_{n=-\infty}^{+\infty}x(n)y^{*}(n-k)$$ 

On remarque qu'il est possible d'écrire la fonction d'intercorrélation comme un produit de convolution :

$$
\widehat{R}_{xy}(k) = x(k) \ast y^*(-k)
$$

On peut alors estimer la fonction d'intercorrélation dans le domaine fréquentiel de la manière suivante :

```{prf:definition} Estimateur fréquentiel

$$
\widehat{R}_{xy}(k) = TFD^{-1}\left[TFD\left[x(k)\right]TFD^*\left[y(k)\right]\right]
$$

```
 <span style="color:rgba(var(--pst-color-link),1)"> L'intérêt de cette estimation fréquentielle est qu'elle permet de réduire le temps de calcul.</span> 
En effet, en utilisant l'algorithme de la FFT (voir paragraphe {numref}`secFFT`), le temps de calcul pour obtenir $N$ élements de $\widehat{R}_{xy}$ est donné par 

$$\sim 3Nlog_2(N)+N \text{ opérations d'addition/multiplication}$$

($2$ FFT, $1$ FFT inverse et $N$ produits), si on fait le calcul avec un estimateur fréquentiel, au lieu de 

$$N+(N-1)+...+1=\frac{N(N+1)}{2}\sim \frac{N^2}{2}$$

($N$ pour $k=0$, $N-1$ pour $k=1$, ... $1$ pour $k=N-1$), en utilisant une estimation dans le domaine temporel.

Et 

$$3Nlog_2(N)+N<<\frac{N^2}{2}, \text{ surtout quand } N \text{ est grand.}$$

```{admonition} Attention! 
:class: warning

Ce calcul, utilisant un passage dans le domaine fréquentiel, suppose que la transformée de Fourier discrète inverse transforme un produit en produit de convolution linéaire. Or nous avons vu que la transformée de Fourier discrète (ou TFD inverse) transformait un produit en produit de convolution circulaire, c'est-à-dire un produit de convolution entre signaux périodisés (période $N$). Néanmoins nous avons également vu plus tôt qu'il est possible de se ramener à un produit de convolution linéaire en utilisant du Zero Padding (au moins autant de zéros ajoutés que de longueur de signal avant de passer dans le domaine transformé).
```