
# 1. Un mot sur le flux normal 
Le flux normal est défini par la spécification CSS 2.1. Elle explique comment les boîtes du flux normal s'inscrivent dans le contexte de formatage.  
Les boîtes peuvent être de bloc (block) ou en ligne (inline) mais pas les deux à la fois. 
*  __block__ les éléments se placent les uns au dessous des autres.
*  __inline__ les éléments se placent à l'horizontale de gauche à droite.  

[source mozilla](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Flow_Layout/Disposition_de_bloc_en_ligne_avec_flux_normal)  

# 2. Position static
C’est la position par défaut d’un objet dans du flux normal.
# 3. Position relative
Un élément en position relative peut être déplacé en utilisant ses propriétés css __left__ et __top__.
## Exemple 1 : 
3 rectangles sont alignés les uns au dessous des autres. Grâce à la position relative, le 1er est décalé en diagonale. 
> Toutefois il reste dans le flux normal, ce qui peut provoquer un espace vide non désirable.
```html
<div class="b1"></div>
<div class="b2"></div>
<div class="b3"></div>
```
```css
div{
  width: 150px;
  height: 100px;
}
.b1{ 
  background: red;  
  /* décalage du div rouge */
  position: relative; 
  left: 100px; top: 80px;
}
.b2{ background: green; }
.b3{ background: blue; }
```

## Exemple 2 :
Deux blocs utilisent la position relative pour intervertir leur position.
```html
<section>
<div class="b1">A</div>
<div class="b2">B</div>
<div class="b3">C</div>
</section>
```
```css
div{
  width: 150px; height: 80px; 
  position: relative; 
  text-align: center;
  color:white; 
  font-size: 70px;
}
.b1{ 
  background: red;  
  /* est déplacé à la position du vert*/
  top:160px;
}
.b2{ background: green; }
.b3{ 
  /* est déplacé à la position du rouge */
  background: blue; 
  top : -160px;
}
```
# 4. Position absolute
Un élement en position absolute est enlevé du flux normal. Sans autre indication, le  __body__ devient son parent direct.    
L’intérêt est aussi de pouvoir le placer n’importe en utilisant les prorpiétés __left, top, right, bottom__. 
## Exemple 1 : 
Une section rectangulaire contient un carré, lequel est en position absolute et ne s'affiche plus dans la section.      
Pour que le carré soit à nouveau relatif à son parent, le parent doit être en  __position relative__.
```html
<section>
  <div></div>
</section>
```
```css
section{
  /* position: relative; */
  margin: 100px 0 0 100px;
  width: 300px;  height: 200px;
  border:1px solid black;
}

div{
  width: 50px; height: 50px;
  position: absolute; top:0; left: 0;
  background: #000;
}
```
## Exemple 2 :
Le code suivant crée la face 3 d'un dé à jouer.
```html
<div class="de">
  <div class="p2"></div>
  <div class="p4"></div>
  <div class="p6"></div>
</div>
```
```css
 /* à faire en cours
```
# 5. Position fixed
Un élément fixe reste à sa place d’origine. L’exemple suivant montre  :
* comment fixer un menu. 
* comment fixer le background d’une section.
```html
<nav class="b1"><h1>Position fixed</h1></nav>
<div class="b2"></div>
<div class="b3"><p>Lorem ipsum dolor sit.</p></div>
<div class="b4"></div>
```
```css
*{ margin: 0; }
h1{ 
  width: 90%; 
  text-align:right; 
}

section{
  margin: 50px 0 0 100px;
  width: 300px; height: 200px;
  border:1px solid black;
}

div, nav{ width: 100%; }

.b1{ 
  position: fixed;
  padding: 10px;
  background: #333; 
  color:white;
}

.b2{ 
  background: darkOrange; 
  height: 500px;
}
.b3{ 
  height: 300px; width: 100%; 
  line-height: 300px;
  text-align: center;
  /* voir http://www.colorzilla.com/gradient-editor/ */
  background: linear-gradient(-45deg, #b4ddb4 0%,#83c783 11%,#52b152 21%,#008a00 31%,#008a00 31%,#008a00 38%,#008a00 58%,#005700 66%,#005700 100%) fixed;
}

.b3 p{ 
  margin: auto;  
  color:white; 
  font-size: 3rem; 
}

.b4{ 
  height: 500px;  
  background: orange; 
}
```