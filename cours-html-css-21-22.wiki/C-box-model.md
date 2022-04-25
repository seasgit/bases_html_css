# 1. Introduction  
Une boîte possède des dimensions et peut apparaître sur la page comme une forme rectangulaire  
Un simple paragraphe peut être vu comme une « boîte », pour autant ce n’est pas un élément conteneur. 
# 2. Caractéristiques d'une boîte  :
* Elément de type block.   `display:block`
* possède une largeur et hauteur.   `width|height`
* peut avoir un espace interne tout autour.   `padding`
* peut avoir des marges externes.   `margin`
* peut avoir des bordures.   `border`
# 3. Ne sont pas des boîtes
les élements de type `inline`, comme :
* les hyperliens, appelées aussi ancres. `<a>` 
* les images. `<img />`
* les éléments relatifs aux paragraphes : `<span>, <em>, <strong>, ...` pour ne citer que ceux là. 
> __Démo :__ http://guyroutledge.github.io/box-model/
# 4. Exercice
Créer un document html relié avec un style css 
* balise `<style>` dans `<head>` 
* ou relié à un document css externe.  

Créer un div avec du contenu dans le corps du document html :
```html
<body>
    div>lorem100 <!-- tabuler -->
</body>
```  
Dans le style css ajouter la règle suivante : 
```css
div{
  width: 400px; height: 250px;
  /* marges externes */
  margin-left:80px;
  margin-top: 80px;
  /* espace interne --> dilate la boite */
  padding: 20px;
  /* bordure */
  border:10px solid #01579B;

  background:#00ACC1;
  color:white;  
  text-align: justify;
}
```
# 5. Syntaxe des marges ou padding
```css
/* Une marge gauche et haute de 50px. */
margin-left: 50px ;
margin-top: 50px ;
/* Le Racccourci : */ 
margin : 50px 0 0 50px;

/* Centrer horizontalement avec la valeur auto.*/
margin-left: auto ;
margin-top: auto ;
/* Le Racccourci : */ 
margin : 0 50px 0 50px; 
/* ou encore */ 
margin : 0 50px;
```
> __NB :__ Même principe pour les padding.

# 6. Syntaxe des bordures
Voici un lien vers une des nombreuses démos en ligne :  
Mozilla doc : https://developer.mozilla.org/fr/docs/Web/CSS/border

# 7. Padding et débordements
Le padding d’une boîte se traduit par une dilatation de celle-ci.  
Le padding peut nuire à une mise en page s'il est appliqué sans réelle 
étude du gabarit de page.  
CSS3 propose la propriété `box-sizing :border-box`.  
L’espace est recalculé afin de s’adapter au mieux aux dimensions d’origine du conteneur.
## Exercice
```html
 <section>
  <div class="bleu"></div>
  <div class="rouge"></div>
  texte pour voir le débordement des div
</section>
```
```css
* {
  margin: 0;  padding: 0;
    /* corrige le débordement */
    box-sizing: border-box;
}

section {
  width: 300px;  height: 200px;
  background: #29B6F6;
}

div{
  width: 300px;  height: 80px;
  padding: 0 10px;
}
.bleu { background: blue }
.rouge { background: red }


