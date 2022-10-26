## Propriétés

```{prf:property} 

1. **Linéarité :**

    $$
    TZ\left[ax(n)+by(n)\right]=aTZ\left[x(n\right]+bTZ\left[y(n\right]
    $$

    Convergence : si $R^+=Min(R_x^+,R_y^+)$ et $R^-=Max(R_x^-,R_y^-)$ alors le domaine de convergence contient $]R^-, R^+[$.

2. **Décalage temporel :**

    $$
    TZ\left[x(n-n_0)\right]=z^{-n_0}TZ\left[x(n)\right]
    $$

    Même domaine de convergence que pour $X(z)=TZ\left[x(n\right)]$.

3. **Changement d'échelle :**

    $$
    TZ\left[a^nx(n)\right]=X\left(\frac{z}{a}\right)
    $$

    Convergence : $aR_x^- \leq |z|< aR_x^+$

4. **Dérivabilité :**

    La transformée en z définit une série de Laurent qui est indéfiniment dérivable terme à terme dans son domaine de convergence. On en déduit :

    $$
    TZ\left[nx(n)\right]=-z\frac{dX(z)}{dz}
    $$
    
    Même domaine de convergence que pour $X(z)=TZ\left[x(n\right)]$.

5. **Produit de convolution :**

    Le produit de convolution entre les suites $x(n)$ et $y(n)$ est défini par :
    
    $$
    x(n)\ast y(n)=\sum_{k=-\infty}^{+\infty}x(k)y(n-k)
    $$
    
    On a alors :
    
    $$
    TZ\left[x(n)\ast y(n)\right]=X(z)Y(z)
    $$
    
    et sa région de convergence peut être plus large que l'intersection des régions de convergence de $X(z)$ et $Y(z)$.
 
 ```