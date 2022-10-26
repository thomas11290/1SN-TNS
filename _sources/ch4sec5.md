## Exemple sur une ligne d'image SAR

La figure {numref}`SAR1` trace la DSP théorique d'une ligne d'image SAR  (Synthese Aperture Radar) et la compare aux estimations par périodogramme, par corrélogramme biaisé et corrélogramme non biaisé. On constate effectivement que le périodogramme et le corrélogramme biaisé sont identiques et plus proches de la DSP théorique que le corrélogramme non biaisé.

```{figure} ./img/sar_DSP.png
---
height: 10cm
name: SAR1
---
Calcul de la DSP sur une ligne d'image SAR
```

La figure {numref}`SAR2` trace la DSP théorique d'une ligne d'image SAR et son estimation par périodogramme cumulé. On peut effectivement constater que la variance d'estimation a réduit du fait du cumul.

```{figure} ./img/sar_DSP_period_cumule.png
---
height: 10cm
name: SAR2
---
Calcul de la DSP sur une ligne d'image SAR en utilisant un périodogramme cumulé
```
