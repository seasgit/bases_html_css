
# 1. Quelques unités dans les propriétés css
|Unités| infos |
|:---:|:---|
| px | Taille absolue exprimée en pixel. |
| % | Pourcentage de largeur ou hauteur de l'élément parent. Utilisé avec les largeurs de blocs, d'images |
| rem |	Unité relative à la taille par défaut du corps.|
| vw / vh |	Unité relative à l’écran. (v comme viewport) |

# 2. Unités en pixel
Simple à l'utilisation, mais pas du tout adaptée à des agrandissements de texte à la volée.
```html
    <p class="p1">LOREM <span>IPSUM</span></p>
```
```css
/* 16px taille par défaut dans les navigateurs */
body{ font-size: 16px; font-family: sans-serif; }

.p1{ font-size: 16px;}
 /* on veut une taille du span à 140% de son parent => petit calcul (16*140/100) */
.p1 span { font-size: 22.4px;} 

```
Testez avec l'inspecteur. Changer la font-size du body, et constatez ! ... Aucun changement !  
De plus, si je décide que le paragraphe a une taille de 18 pixel, je dois recalculer la taille de son span pour qu'il reste à 140%.  
Pas très pratique !
# 3. Les unités relatives __rem__
Unité adaptée à des agrandissements simple d'utilisation.  
La proportionalité se fait à partir de la taille par défaut du navigateur.
```html
    <p class="p1">LOREM <span>IPSUM</span></p>
```
```css
html,
body{ font-size: 1rem;  font-family: sans-serif; }

/* p1 à 1rem = 16px */  
.p1{ font-size: 1rem;}
/* span de p1 à 140% */
.p1 span { font-size: 1.4rem;}
```

Utiliser ce site pour faire quelques conversions :
https://www.jarrige.fr/pixelrem/

# 4. Un mot sur les unités viewport
Ce système d'unité est plus récent. Les valeurs sont relatives à la largeur ou la hauteur de l'écran.
- 10vh  =  10% de la hauteur du viewport.    
- 10vw  =  10% de la largeur du viewport.    
- 10vmin = 10% de la dimension la plus petite de la fenêtre.  

__A noter__ qu'elles sont de plus en plus utilisées, d'autant plus avec les besoins liés au reponsive web design. 

