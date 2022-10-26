## Périodogramme avec fenêtrage

Comme nous l'avons évoqué dans le chapitre sur la transformée de Fourier discrète en parlant de TFD pondérée, on peut également, pour estimer la DSP, utiliser un périodogramme sur le signal pondéré :

$$
\widehat{S}_{x}(n)=\frac{1}{N} \left|TFD\left[x(k) w(k)\right]\right|^2
$$

où $w(k)$ représente la fenêtre de pondération choisie (voir chapitre sur la transformée de Fourier).