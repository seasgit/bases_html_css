
# 1. Autour de display
La propriété display permet de définir le type d'alignement d'élements dans une page ou dans une boîte. 
> Avec __display__, il est en fait question de gabarits de pages. 

Il n'y a pas si longtemps, les techniques employées demandaient du temps des efforts et de l'astuce pour obtenir le résultat désiré.    
Aujourd"hui le W3C offre deux modules CSS qui révolutionnent l'art et la manière de concevoir et intégrer des pages web.  
1. Flexbox
2. Grid Layout.

Ce cours de niveau 1 s'interesse surtout à __Flexbox__.  
Avant de l'aborder, voyons quelques cas d'utilisation classique de display. 

## display non déclarée
Un élément tel que le _div_ a par défaut la propriété `display:block`.  
Un élément tel que le _span_ a par défaut la propriété `display:inline`.  
On peut voir dans l'exemple suivant le résultat.  
  (_Enlevez dans un 2ème temps les commentaires et constatez le changement._)
### Le code HTML
```html
<div class="container">
    <div class="d rouge">Block</div>
    <div class="d bleu">Block</div>

</div>
<div class="container">
    <span class="s rouge">Inline</span>
    <span class="s bleu">Inline</span>
</div>
```
### le code CSS
```css
.container {
    width: 600px; height: auto;
    margin: 0 auto 20px;
    background: #999; color:white;
}

.d { 
	width: 150px;  height: 100px;
/* 	display: inline;  */
}
.s { 
	padding: 10px; 
/* 	display: block;  */
}

.rouge { background: red; }
.bleu { background: blue; }

```
## display: inline-block  
Les éléments sont placés horizontalement mais restent des éléments de type block. Si la place manque à droite, l’élement courant est placé à gauche à la verticale.
### Le code HTML
```html
<div class="container">
    <div class="box">A</div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</div>
```
### le code CSS
```css
.container {
/* 		display: table; */
    width: 490px;
    margin: 0 auto;
    padding-bottom: 10px;
    background: #999;
}

.box {
    width: 150px; height: 100px;
    margin: 10px 0 0 10px;
    display: inline-block;
    vertical-align: top;
    background: red;
}

```
__NB :__   
On remarque dans notre exemple un problème d'espacement entre les boîtes. Le conteneur est de type block, et il n'offre pas un contexte d'affichage suffisant pour aligner correctement ses enfants.  
Raphael Goetter en parle dans un des ses articles [ici](https://www.alsacreations.com/astuce/lire/1543-le-contexte-de-formatage-block-en-css.html)   
Pour remédier à notre problème, on va donc ajouter `display:table` à l'élément de classe constainer.

## display: none vs visiblity: hidden
Quand on veut masquer un élément de la page il y a deux possibilités : 
Avec `display:none` la place est récupérée par le navigateur. Cela peut créer un décalage.    
Dans certains cas il vaudra mieux utiliser `visibility: hidden`.  
```html
<h3>Element rouge avec display none </h3>
<div class="container c1">
    <div class="d rouge">ROUGE</div>
    <div class="d bleu">BLEU</div>
</div>
<h3>Element rouge avec visibility hidden </h3>
  <div class="container c2">
    <div class="d rouge">ROUGE</div>
    <div class="d bleu">BLEU</div>
</div>
```

```css
.container {
    width: 600px; height: auto;
    background: #999; color:white;
}

.d {
  width: 150px;  height: 100px; 
  display: inline-block;
}


.rouge { background: red; }
.bleu { background: blue; }

.c1 .rouge { display: none; }
.c2 .rouge { visibility :hidden ;}
``` 

# 2. Flexbox  ou "_CSS Flexible Box Layout Module_". 
Le W3C offre plus de simplicité et d'efficacité de mise en page avec le module CSS Flexbox.
Flexbox permet entre autres :  
* de répartir des éléments dans un conteneur selon plusieurs critères.
* de redimensionner des élements de manière intelligente.
* de réordonner ou intervertir des éléments plus simplement.
> __NB :__  
	Un conteneur de type flex aligne ses enfants __directs__.  
	Un élément enfant d’un conteneur flex peut gérer son propre alignement.  
## Apprendre Flexbox.  
Il existe beaucoup de tutoriels et quelques jeux pour apprendre Flexbox.  
Notre objectif en deux points : 
- Expérimenter Flexbox grâce à tous ces supports.
- Choisir un modèle de page existant à intégrer en Flexbox.
### Tutoriels  
https://css-tricks.com/snippets/css/a-guide-to-flexbox/    
https://codepen.io/enxaneta/full/adLPwv/   
https://www.youtube.com/watch?v=Y8zMYaD1bz0&list=PL4cUxeGkcC9i3FXJSUfmsNOx8E7u6UuhG  

### Jeux
http://flexboxfroggy.com/    
http://www.flexboxdefense.com/  
