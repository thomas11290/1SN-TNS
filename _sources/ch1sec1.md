## Numérisation du signal : échantillonnage

```{prf:definition}  

<span align="center" style="color:rgba(var(--pst-color-link),1)"> **Un signal échantillonné est un signal défini à des instants discrets** </span>
```

### Principe, impact

Nous considérons ici un échantillonnage idéal périodique et un signal à échantillonner, $x(t)$, déterministe. Si nous notons $T_e$ la <span style="color:rgba(var(--pst-color-link),1)"> ***période d'échantillonnage*** </span>, le signal $x(t)$ échantillonné de manière périodique à $T_e$ est constitué d'une succession d'élements prélevés tous les $T_e$ : $\left\{x(kT_e)\right\}$ avec $k \in \mathbb{Z}$. La figure {numref}`sinus_echant` présente un exemple d'échantillonnage d'une fonction sinusoïdale.

```{figure} ./img/sinus_echantillonne.PNG
---
height: 10cm
name: sinus_echant
---
Exemple de sinusoïde échantillonnée
```

 
Afin d'étudier l'effet de cet échantillonnage temporel, nous allons  associer à $\left\{x(kT_e)\right\}, \; k \in \mathbb{Z}$, le modèle à temps continu suivant :
 
$$x_e(t)=x(t)\amalg \hspace{-0.3cm}\amalg_{T_e}(t),$$ 
    
où $\amalg \hspace{-0.3cm}\amalg_{T_e}(t)$ représente le peigne de Dirac de largeur $T_e$.
 
Si $X(f)$ est la Transformée de Fourier de $x(t)$ alors la transformée de Fourier de $x_e(t)$ est donnée par :

$$X_e(f)=\frac{1}{T_e} X(f) \ast \delta(f-kF_e)=F_e\sum_n X(f-kF_e)$$     
    
où $F_e=\frac{1}{T_e}$ représente la ***fréquence d'échantillonnage*** (nombre d'échantillons prélevés par unité de temps).  La transformée de Fourier du signal $x(t)$ est donc périodisée tous les $F_e$ par l'opération d'échantillonnage. Afin d'éviter le recouvrement des périodisations (aliasing) la fréquence d'échantillonnage doit être choisie de manière à ce que l'on ait $F_{max}<F_e-F_{max}$,  si $F_{max}$ représente la fréquence maximale de $X(f)$.
   
```{prf:theorem} Théorème d'échantillonnage de Shannon
Afin de conserver la même information dans le signal échantillonné et dans le signal à temps continu, la fréquence d'échantillonnage $F_e$ doit être choisie de manière à respecter la condition suivante :
    
$$F_e>2F_{max},$$
    
si $F_{max}$ représente la fréquence maximale de la transformée de Fourier du signal. Cette condition s'appelle la condition de Shannon.
```
 
Claude Shannon est un ingénieur en génie électrique et un mathématicien né en $1916$ aux Etats Unis. Il est un des pères de la théorie de l'information. Il a montré en $1949$ que tout signal à temps continu dont le spectre est limité en bande pouvait être représenté, sans perte d'information, par une série d'échantillons du signal d'origine, à condition de correctement choisir la fréquence à laquelle on prélève ces échantillons.


### Restitution par filtrage
    
<span style="color:rgba(var(--pst-color-link),1)"> **Si la condition de Shannon est respectée** </span>, il est alors possible de reconstituer le signal $x(t)$, à partir de la suite des échantillons prélevés tous les $T_e$, en utilisant un filtre passe-bas de fréquence de coupure $f_c\in \left[F_{max} \;F_e-F_{max}\right]$. En notant $y(t)$ le signal reconstitué et $Y(f)$ sa transformée de Fourier, nous avons :
        
$$
Y(f)=H_{PB}(f)X_e(f)
$$

et donc :

$$
y(t)=h_{PB}(t)*x_e(t)=h_{PB}(t)*\sum_{k \in \mathbb{Z}} x(kT_e) \delta(t-kT_e)=\sum_{k \in \mathbb{Z}} x(kT_e) h_{PB}(t-kT_e)
$$

La reconstitution par filtrage est donc équivalente à une interpolation. Le signal est reconstruit en sommant les décalages, tous les $T_e$, de la fonction d'interpolation $h_{PB}(t)$ pondérée par les échantillons du signal. 


```{prf:theorem} Formule de reconstitution de Shannon

Lorsque $F_e=2F_{max}$ (limite de Shannon), un seul filtre permet de reconstituer le signal de départ à partir des échantillons prélevés tous les $T_e$ : c'est un filtre passe-bas idéal de réponse en fréquence $H_{PB}(f)=\Pi_{F_e}(f)$, avec $F_e=\frac{1}{T_e}$ et $\Pi_{F_e}(f)=1$ pour $f \in \left[-\frac{F_e}{2}, \frac{F_e}{2}\right]$. Sa réponse impulsionnelle est donc $h_{PB}(t)=F_e sinc\left(\pi F_e t\right)$ et le signal restitué s'écrit alors :

$$
y(t)=F_e\sum_{k \in \mathbb{Z}} x(kT_e) sinc\left(\pi F_e (t-kT_e)\right)
$$

Cette expression est appelée formule de reconstitution de Shannon. 
```

La formule de reconstitution de Shannon permet de voir l'échantillonnage idéal d'une autre manière : comme étant la décomposition du signal sur la base orthogonale des fonctions $sinc\left(\pi F_e (t-kT_e)\right)$, $k \in \mathbb{Z}$.

<span align="center" style="color:rgba(var(--pst-color-link),1)"> **Si, par contre, la condition de Shannon n'est pas respectée**</span>, il n'est alors plus possible de reconstituer le signal $x(t)$, à partir de la suite des échantillons prélevés tous les $T_e$, car les périodisations de $X(f)$ tous les $F_e$ vont venir se superposer à $X(f)$. On parle de repliement ou d'aliasing (voir {numref}`exercice2`.**

On verra néanmoins dans l'{numref}`exercice3` que pour certains signaux, présentant des propriétés particulières, il est possible d'échantillonner sans perte d'information en ne respectant pas la condition de Shannon.

```{prf:remark}
        
- Lorsque le signal $x(t)$ a un spectre de type passe-bande, il est possible de ne pas respecter la condition de Shannon tout en étant capable de reconstituer le signal de départ. La condition est alors que, par un choix astucieux de $F_e$, les repliements puissent se faire dans les trous du spectre de départ (voir  {numref}`exercice2`).
        
- L'échantillonnage présenté plus haut est un échantillonnage idéal. En pratique, il est impossible de prélever un échantillon de signal toutes les $T_e$ secondes. On pourra, par exemple,
            
    - Utiliser un filtre, mais qui ne sera pas un filtre idéal. Il est alors nécessaire de surcéhantilloner par rapport à la limite de Shannon.
            
    - Procéder par extrapolation : $x(kT_e+\tau)=x(kT_e)$ pour $0\leq \tau \leq T_e$ (bloqueur d'ordre $0$) ou $x(kT_e+\tau)=x(kT_e)+\frac{\tau}{T_e}\left(x(kT_e)-x((k-1)T_e)\right)$ pour $0\leq \tau \leq T_e$ (bloqueur d'ordre $1$ ou extrapolateur linéaire)
            
    - Procéder par interpolation : par exemple $x(kT_e+\tau)=x(kT_e)+\frac{\tau}{T_e}\left(x((k+1)T_e)-x(kT_e)\right)$, $0\leq \tau \leq T_e$, pour un interpolateur d'ordre $1$ (causal à un retard près)...
                     
    Les {numref}`exercice3` et {numref}`exercice4` étudient deux méthodes "pratiques" d'échantillonnage.

- Lorsque le signal $x(t)$ ne présente pas de fréquence maximale $F_{max}$ mais que son spectre décroit quand la fréquence augmente, il est alors possible de réaliser une opération d'échantillonnage avec une réversibilité acceptable. On se définit alors une fréquence maximale, correspondant à l'atténuation minimale souhaitée par rapport à la valeur maximale du spectre, on positionne un filtre dit filtre anti-repliement, qui va couper le spectre au delà de la fréquence maximale choisie, puis on échantillonne (voir {numref}`exercice5).
       
- On définit en numérique des fréquences normalisées : $\widetilde{f}=\frac{f}{F_e}$ qui sont donc sans dimension et qui permettent de s'affranchir de la connaissance de la valeur de $F_e$ dans les traitements à réaliser sur le signal.
```
