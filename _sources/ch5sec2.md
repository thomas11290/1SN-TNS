## Convergence

La région de convergence est l'ensemble des nombres complexes $z$ tels que la série $X(z)$ converge. On utilisera le critère de Cauchy :

$$
\lim_{n\rightarrow \infty} \sqrt[n]{|v(n)|}< 1 \quad \Rightarrow \quad \sum_{n=0}^{\infty} v(n) \quad \text{converge}
$$

pour avoir une condition suffisante de convergence :

$$
X(z)= \sum_{n=0}^{+\infty} x(n) z^{-n} + \sum_{n=1}^{+\infty} x(-n) z^{n} \; \text{converge} \; \text{pour} \; 0\leq R_x^- \leq |z|< R_x^+ < \infty
$$

avec 

$$R_x^- = \lim_{n\rightarrow \infty} \sqrt[n]{|x(n)|}$$ 

et 

$$R_x^+ = \frac{1}{\lim_{n\rightarrow \infty} \sqrt[n]{|x(-n)|}}$$

```{prf:example}

$$
X(z)=\sum_{n=0}^{+\infty} z^{-n} \quad converge \; pour \; |z|>1 \; : \; R_x^-=1 \; and \; R_x^+=\infty
$$

```