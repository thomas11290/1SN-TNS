## Numérisation du signal : exemples sur une image
    
La figure {numref}`image1` présente une image de $512\times512$ pixels, codée sur $nb=8$ bits et sa version sous échantillonnée d'un facteur $4$ ($128\times128$ pixels). Cette image (Barbara) est très utilisée en traitement d'images. Elle permet ici de voir apparaitre le phénomène de Moiré : on voit apparaitre sur l'image sous échantillonnée des structures différentes de celles contenues dans l'image d'origine.
    
    
```{figure} ./img/images_ech.png
---
height: 10cm
name: image1
---
Image de départ (quantifiée sur $8$ bits, $512\times512$ pixels), Image sous échantillonnée d'un facteur $4$
```

La figure {numref}`image2` présente Barbara codée sur $nb=4$ bits et sur $nb=2$ bits. Dans le dernier cas, par exemple, on ne voit alors plus que $2^{nb}=2^2=4$ niveaux de gris (au lieu de $2^8=256$ allant du noir au blanc sur l'image de départ).


```{figure} ./img/Image_quant.png
---
height: 10cm
name: image2
---
Image quantifiée sur $nb=4$ bits, Image quantifiée sur $nb=2$ bits
```

