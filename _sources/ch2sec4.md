## Exercices

Les corrections se trouvent dans le poly d'exercices.

```{exercise} Etude de la TFD d'un signal à spectre continu : effet de la limitation de la durée du signal.
 :label: exercice2.1        

\begin{equation}
    x(t) = \left\{
    \begin{array}{rl}
    e^{-at} & \mbox{si } t\geq 0, a>0\\
    0 & \mbox{si } t<0. \\
    \end{array} \right. \;
\end{equation}

On observe le signal sur une durée limitée $L$.

1.  Montrer que la transformée de Fourier du signal observé sur une durée $\left[0, L\right]$ s'écrit $X_L(f)=X(f)G(f,L)$.

2. Déterminer le module de $G(f,L)$.

3. Montrer que $\left|G(f,L)\right|$ est compris entre $1-e^{-aL}$  et $1+e^{-aL}$.

4. Chiffrer ces bornes pour $L=\frac{4}{a}$.

5. Déterminer la phase de $G(f,L)$.

6. En utilisant les développements limités dans le cas où $L>>\frac{1}{a}$, montrer qu'on peut arriver à la valeur approchée de la phase suivante :

    $$Arg\left[G(f,L)\right] \simeq e^{-aL} \sin(2 \pi f L)$$

7. Borner la valeur approchée de la phase et la chiffrer pour $L=\frac{4}{a}$.

8. Quelle conclusion peut-on tirer de ces calculs sur l'effet de la troncature du signal x(t) ?

```
```{exercice} Etude de la TFD d'un signal à spectre continu : effet de l'échantillonnage du signal

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

3. En considérant la transformée de Fourier comme négligeable pour une atténuation minimale de $40$ dB par rapport à sa valeur maximum, dimensionner la fréquence d'échantillonnage à utiliser $F_e$.

4. Donner l'expression de la transformée de Fourier d'un signal $x(t)$ échantillonné à $T_e$, c'est-à-dire la transformée de Fourier de   $\left\{x(kT_e)\right\}$ pour $k=-\infty, ...,+\infty$. On la notera $X_e(f)$.

5.Déterminer $X_e(f)$ pour le signal donné par (\ref{eq_signal}). Vérifier qu'elle est périodique de période $F_e$ . La comparer à $X(f)$.
```

```{exercise}  Etude de la TFD d'un signal à spectre continu : échantillonnage et limitation de la durée du signal

Soit le signal $x(t)$ défini par :

\begin{equation} \label{eq_signal1}
x(t) = \left\{
    \begin{array}{rl}
    e^{-at} & \mbox{si } t\geq 0, a>0\\
    0 & \mbox{si } t<0. \\
    \end{array} \right. \;
\end{equation}

1.  Donner l'expression de la transformée de Fourier d'un signal $x(t)$ échantillonné à $T_e$ et limité à $N$ points, c'est-à-dire la transformée de Fourier de  $\left\{x(kT_e)\right\}$ pour $k=0, ...,N-1$. On la notera $X_D(f)$.

2. Déterminer $X_D(f)$ pour le signal donné par (\ref{eq_signal1}). La comparer à $X(f)$.
```

```{exercise} Etude de la TFD d'un signal à spectre discontinu : calcul d'un nombre fini de points du spectre

Soit le signal $x(t)$ défini par :

\begin{equation} \label{eq_signal3}
x(t) = A e^{j(2 \pi f_0 t + \phi)}, \; t\in \mathbb{R}, \; \phi=constante
\end{equation}


1. Déterminer la transformée de Fourier $X(f)$ du signal $x(t)$.

2. Déterminer la transformée de Fourier du signal observé sur une durée limitée $\left[0, L\right]$. On la note $X_L(f)$.

3. Déterminer la transformée de Fourier du signal échantillonné à $T_e$ et observé sur $N$ points. On la note $X_D(f)$.

4. La transformée de Fourier numérique (spectre du signal) ne sera calculée que pour un nombre fini, $N$, de points : $X_D(f) \rightarrow \left\{X_D(n \frac{F_e}{N})\right\}$ pour $n=0, ...,N-1$. Dans le cas où $f_0=\frac{n_0}{N}F_e$, avec $n_0$ entier, déterminer $X_D(n)$ (notation pour $X_D(n \frac{F_e}{N})$) puis tracer $\left|X_D(n)\right|$ pour $n=0, ...,N-1$. Que constate t-on ?

5. Tracer $\left|X_D(n)\right|$, pour $n=0, ...,N-1$, dans le cas où $f_0=\frac{n_0+\epsilon}{N}F_e$, $n_0$ entier et $0<\epsilon<1$. Ce résultat est-il satisfaisant (permet-il une analyse spectrale correcte) ?

6. Quelle méthode peut-on utiliser pour améliorer la visualisation de la transformée de Fourier numérique (et donc le résultat de l'analyse spectrale) ?
