## Exercices

Les corrections se trouvent dans le poly d'exercices et problèmes résolus.

```{exercise} Cosinus mal échantillonné
:label: exercice1

On échantillonne le signal $x(t)=\cos \left( 2\pi f_{0}t\right)$ avec $f_{0}=5kHz$ à la fréquence d'échantillonnage $F_{e}=8kHz$. 

1. Déterminer la densité spectrale du signal échantillonné $x_{e}(t)$ et la représenter graphiquement pour $\left\vert f\right\vert <12kHz$.  

2. Quel signal obtient-on si on filtre le signal $x_{e}(t)$ précédent à l'aide d'un filtre passe-bas idéal de fréquence de coupure $F_{c}=4kHz$ ? Même question si on filtre le signal $x_{e}(t)$ à l'aide d'un filtre passe-bande idéal de bande passante $\left[ -6kHz,-4kHz\right] \cup \left[ 4kHz,6kHz\right]$.
```

```{exercise} Effet de l'échantillonnage
:label: exercice2  

Soit le signal suivant : $x(t)=\cos(2 \pi f_0 t),  \; f_0=10$ kHz.

1. Tracer la transformée de Fourier de $x(t)$: $X(f)$.

2. Est-il possible d'échantillonner $x(t)$ sans perte d'information ? Si oui à quelle condition ?
        
3. Tracer, entre $0$ et $F_e$, la transformée de Fourier de $x(t)$ échantillonné à $T_e=1/F_e$ quand : 

    a. $F_e=30$ kHz.
    
    b. $F_e=8$ kHz.
        
4. A partir des échantillons nous souhaitons reconstruire $x(t)$ par filtrage passe-bas à $F_e/2$. Quels seront les signaux obtenus pour chaque fréquence d'échantillonnage précédente ?
```
```{exercise} Echantillonnage d'un signal passe-bande
:label: exercice3  

On considère le signal $x(t)=x^+(t)+x^-(t)$, avec $x^+(t)=B\frac{sin(\pi Bt)}{\pi B t}e^{j 2 \pi f_0 t}$ et $x^-(t)=B\frac{sin(\pi Bt)}{\pi B t}e^{-j 2 \pi f_0 t}$, $f_0=8 kHz$ et $B=2 kHz$.

1. Déterminer la transformée de Fourier du signal $x(t)$ et la représenter graphiquement.

2. Comment s'écrit la condition de Shannon pour le signal $x(t)$ ?

3. On échantillonne le signal $x(t)$ à la fréquence $F_e=6 kHz$.
            
    a. Représenter graphiquement la transformée de Fourier du signal échantillonné $x_e(t)$ dans la bande $\left[- 9 kHz, 9 kHz\right].$  
            
    b. On désire restituer le signal $x(t)$ à partir de $x_e(t)$ par un filtrage de réponse en fréquence $H(f)$.  
    
    - $1^{ier}$ cas : $H(f)=\Pi_F(f)$ avec $F=6 kHz$. Quel sera le signal restitué par ce filtre ?
        
    - $2^{ème}$ cas : $H(f)=\Pi_B(f+f_0)+\Pi_B(f-f_0)$ avec $f_0=8 kHz$ et $B=2 kHz$. Quel sera le signal restitué par ce filtre ?
        
    - Conclusion ?
```
```{exercise} Echantillonneur moyenneur
:label: exercice4  
  
L'échantillonneur moyenneur est une méthode pratique d'échantillonnage qui consiste à calculer, toutes les $T_e$ secondes (période d'échantillonnage), la valeur moyenne du signal pendant un intervalle de temps $\theta $ ($\theta <<T$) et à affecter cette valeur moyenne à l'échantillon discrétisé :

$$\begin{align*}
y\left( kT_e\right) &=\frac{1}{\theta }\int_{kT_e-\theta }^{kT_e}x(u)du \\
x_{ech}(t) &=\sum_k y\left( kT_e\right) \delta \left( t-kT_e\right)
\end{align*}$$

1.  Démontrer que le signal échantillonné $x_{ech}(t)$ peut se mettre sous la forme :
        
    $$x_{ech}(t)=\frac{1}{\theta }\left[ \Pi _{\theta }\left( t\right) \ast x\left( t-\frac{\theta }{2}\right) \right] .\amalg \hspace{-0.3cm}\amalg_{T_e}\left( t\right)$$
        
    où $\Pi _{\theta }\left( t\right) $ et $\amalg \hspace{-0.3cm}\amalg_{T_e}\left( t\right) $ représentent respectivement la fenêtre rectangulaire de largeur $\theta $ et le peigne de Dirac de période $T_e$.
        
2. En déduire la transformée de Fourier correspondante $X_{ech}\left( f\right) $.
        
3. En considérant un signal à support spectral borné $2\Delta f$ et en prenant en compte que la fonction $sinc(\pi \theta f)$ peut être supposé constante sur l'intervalle $\left[ -\frac{1}{3\theta },\frac{1}{3\theta }\right]$, ie.
        
    $$sinc(\pi \theta f)=\frac{\sin (\pi \theta f)}{\pi \theta f}\approx 1\text{pour }f\in \left[ -\frac{1}{3\theta },\frac{1}{3\theta }\right]$$
        
    a. quelle(s) condition(s) doit vérifier $\theta $ pour que le signal $x(t)$ puisse être restitué par filtrage de $x_{ech}(t)$ ?
        
    b. Dans ces conditions peut-on échantillonner à la fréquence de Shannon ?
```        

```{exercise} Echantillonneur bloqueur
:label: exercice5  

L'échantillonneur bloqueur est un échantillonneur réalisable en pratique qui consiste à acquérir un échantillon du signal, $x(t)$, toutes les $T_e$ secondes (période d'échantillonnage) et à le bloquer pendant $\tau$ secondes ($\tau<<T_e$).

1. Proposer une écriture du signal échantillonné de cette manière, $x_e(t)$, en fonction de l'expression du signal échantillonné de manière idéale : $x_{ei}(t)=\sum_{k\in \mathbb{Z}} x(kT_e) \delta(t-kT_e)$.

2. Calculer la transformée de Fourier du signal échantillonné à l'aide de cette méthode. L'écrire en fonction de la transformée de Fourier, $X(f)$, du signal de départ.

3. Est-il possible de dimensionner $\tau$ pour que l'échantillonnage par bloqueur se rapproche d'un échantillonnage idéal ?
```
```{exercise} Signal à spectre non borné - Recherche de la $F_e$
:label: exercice6  


Soit le signal $x(t)$ défini par :
    
\begin{equation} \label{eq_signal}
        x(t) = \left\{
            \begin{array}{rl}
                e^{-at} & \mbox{si } t\geq 0, a>0\\
                0 & \mbox{si } t<0. \\
            \end{array} \right. \;
\end{equation}
 
1. Déterminer la transformée de Fourier $X(f)$ du signal $x(t)$. Tracer $\left|X(f)\right|$.

2. En théorie le signal $x(t)$ est-il échantillonnable sans perte d'information ? Expliquez votre réponse.

3. En considérant la transformée de Fourier comme négligeable pour une atténuation minimale de $40$ dB par rapport à sa valeur maximum, dimensionner la fréquence d'échantillonnage, $F_e$, à utiliser.

4. Une fois $F_e$ déterminée, quel traitement doit-on appliquer au signal avant de l'échantillonner ?
```
```{exercise} Quantification d'un sinusoïde
:label: exercice7 

Soit un signal sinusoïdal $x(t)=A_{0} \sin \left( 2\pi f_0t+\phi\right)$, avec $f_{0}=50Hz$, $A_{0}=220\sqrt{2}V$ et $\phi$ une phase aléatoire uniformément répartie entre $0$ et $2 \pi$. On suppose que la quantification de cette sinusoïde est effectuée dans de bonnes conditions : pas d'écrétage du signal, pas de quantification $q=\frac{D}{2^{nb}}$ suffisament fin ($D$ représentant la dynamique du signal et $nb$ le nombre de bits de quantification). Elle est donc équivalente à l'ajout d'un bruit, $n_Q(t)$, sur le signal non quantifié de départ, bruit aléatoire, centré qui suit une loi uniforme sur $\left[-\frac{q}{2}, \; \frac{q}{2}\right]$. 

Déterminer le rapport signal à bruit de quantification en fonction de $nb$.
```  