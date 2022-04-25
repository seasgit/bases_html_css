# 1. Introduction
Il existe plusieurs façons de relier un élement HTML à son style CSS. Tout passe par des __sélecteurs.__
Ce chapitre montre quelques manières. Les exercices permettront d'aller plus loin et comprendre l'intérêt de bien sélectionner 

# 2. Sélecteur naturel simple
On sélectionne un élément en reprenant le terme html.  
Cet exemple montre une sélection descendante. C’est à dire d’un parent vers un enfant.
```html
<section>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing.</p>
</section>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing.</p>
```
```css
 /*   toutes les sections  */
section {
    width: 400px; height: auto;
    border-left:1px solid black;
    border-bottom:1px solid black;
    padding: 10px;
}

/* tous les p de body */
body p {  color:#444;}

/* les p enfants direct de body */
body > p { font-size: 24px;}

/*   tous les p des section     */
section p {
    font-family: sans-serif;
}
```
> __A noter :__ l’importance de l’opérateur > pour la sélection d’enfants directs.
# 3. Sélecteur par classes (.nom_classe)
Les sélecteurs classe, permettent de créer des catégories de règles css applicables à plusieurs éléments de même nature, ou ayant des rôles similaires.    
Exemples avec des éléments d’apparence bouton. 
## Exemple avec une seule classe

```html
<div class="btn-valider">valider</div>
```
```css
.btn-valider {
    width: 100px;  height: 40px; line-height: 40px;
    background: #4ca750; color:white; text-align: center;
    border-radius: 10px;
}
```
## Exemple avec des classes multiples
```html
<div class="btn btn-success">Confirmer</div>
<div class="btn btn-alert">Annuler</div>
```
```css
.btn {
    width: 100px;   height: 40px;  line-height: 40px;
    text-align: center;
    border-radius: 10px;
    font-family: Roboto;
}

.btn-success {
  background:#2196F3;  color:white;
}

.btn-alert {  background: #FBC02D;  }
```
# 4. Sélection par id
Un élément html identifié doit être unique dans une page. 
```html
<h3 id="titre-page">
    ZEN GARDEN
</h3>
```
```css
#titre-page{
  font-size: 40px;
  letter-spacing: 3px;
  font-family: sans-serif;
  font-weight: 400;
  color: #00BCD4;
}
```
Donner un attribut id est indispensable quand on doit naviguer au sein d’une même page.
## Navigation interne  
L'exemple suivant propose un code pour se déplacer de section en section au sein d'une même page.  
Pour cela il faut une correspondance entre le contenu d'un attribut href et celui d'un attribut id.

```html
<a href='#s1'>Section 2</a>
<a href='#s2'>Section 2</a>
<a href='#s3'>Section 3</a>
<hr>
<section id='s1'></section>
<section id='s2'></section>
<section id='s3'></section>
```
On donne aux sections un hauteur suffisante et une couleur différente
```css
section {
  width:100%;
  height:700px;
}
#s1 { background:orange; }
#s2 { background:palegreen; }
#s3 { background:cyan; }
```

# 5. Pseudo classes
## Créer un survol avec __:hover__
```html
<h1>:hover</h1>
<div class="b1"></div>
```
```css
div{ 
  width: 100px; height: 100px; line-height: 100px;
  text-align: center; font-family: sans-serif;
}

.b1{ background:orange ; }
/* change de couleur au survol */
.b1:hover { background:red; }
```
## Cibler un ou plusieurs éléments avec __:nth-of-type__

```html
<!-- Cibler le nième élément de type span -->
<section class="s2">
  <h1>:nth-of-type</h1>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
</section>
```
```css
div, span{ 
  width: 50px; height: 50px; 
  border-radius: 100%;
  display: inline-block;
}

/* Nième élément de type span*/
.s2 span:nth-of-type(even){  background: pink; }
.s2 span:nth-of-type(odd){ background: yellow; }
```
# 6. Pseudo-sélecteurs
## Ajouter dynamiquement du contenu après avec :after
```html
<div class="b2"></div>
```
```css
div{ 
  width: 100px; height: 100px; line-height: 100px;
  text-align: center; font-family: sans-serif;
}
.b2{ background: #1E88E5 ; }
.b2:after {
  content:"HTML5";
  color : white;
}
```
## Ajouter dynamiquement du contenu au survol
```html
<div class="b3"></div>
```
```css
div { /* même code  */}
.b3{ background: #CE93D8 ; }
.b3:hover{ background: #DEA3DD ; }
.b3:hover:after {
  content:"CSS";
  color : white;
}
```

### Autres ressources
    https://css-tricks.com/examples/nth-child-tester/
    http://nthmaster.com/  


# 7. Sélecteur :root
Utile par exemple pour créer des variables afin d'enregistrer des valeurs récurrentes d'une page web.
- Exp : couleurs, ombres, bordures, etc ...
Ci-dessous, une variable contient une couleur, l'autre les valeurs pour une ombre diffuse.
```css
:root {
  --color-primary: #eb2f64;
  --shadow-dark: 0 2rem 6rem rgba(0, 0, 0, .3); }
```
__NB__  :  une variable est appelée ensuite comme ceci : 
```css
.unebox {
  background-color: var(--color-primary);
}
```

# 8. Le poid des sélecteurs
## Premier exemple 
On a un paragraphe. On prévoit un identifiant et une class.
```html
<p class="p1" id="p1">HTML5 CSS</p>
```
Pour réaliser cet exercice :
- commencer par appliquer une couleur en utilisant le sélecteur naturel..
- puis en utilisant le sélecteur class..
- puis le sélecteur id.
- Et constatez à chaque fois les changements de couleur.
```css
p{
  font-size: 2rem;
  color :darkcyan
}
.p1 { color: green; }
#p1 {  color:orange }
```
Ajouter le style en ligne et constater
```html
<p class="p1" id="p1" style='color:red'>HTML5 CSS</p>
```
Enfin, modifier le sélecteur naturel comme ceci :
```css
p{
  font-size: 2rem!important;
  color :darkcyan
}
```
# Autre exemple:
On a un conteneeur identifié __mainbox__ qui contient 2 ou trois div de classe __box__
```html
<div id="mainbox">
	<div class="box"></div>
	<div class="box"></div>
	<div class="box"></div>
</div>
```
Donnons le style css suivant :
```css
#mainbox .box{
	width: 100px;
	height: 60px;
	margin-bottom: 10px;
	background: #000;
}

```
Maintenant, si nous voulons modifier la couleur de la 2ème boîte comme ceci : 
```css
.box:nth-of-type(2) {
	background: blue;
}

```
Nous constatons que cela n'est pas pris en compte..
En effet, le premier code css est plus précis que le second en mentionant le parent.
Donc, nous devons corriger comme ceci : 
```css
#mainbox  .box:nth-of-type(2) {
	background: blue;
}

```