# 1. Element <img>
Un élément `<img>` est un contenu de page web, et à ce titre peut être référencé et peut être remplacé par du texte.
## Image élatique
On peut placer un élément `<img>` dans un bloc conteneur et l'étirer sur la largeur __ou__ sur la hauteur. 

```html
<figure>
  <img src="https://images.pexels.com/photos/354984/pexels-photo-354984.jpeg?w=1260&h=750&auto=compress&cs=tinysrgb" alt="">
  <figcaption>Funny day</figcaption>
</figure>
```
```css
figure{
  width: 600px;
  height:300px;
  border:1px solid black;
}

figure img {
  width:100%;
  height : auto; /* la hauteur s'adapte automatiquement */
}
```
## Image aux dimensions de son conteneur parent
Un élément `<img>` peut être adapté aux dimensions du bloc conteneur avec un propriété de CSS3 : `object-fit`.  
On garde ici le même conteneur, la même image, et on change le css.
```css

figure img {
  width: 600px;
  height:300px;
  object-fit:cover;
  object-position:top; /* essayer bottom , center */
}
```
# 2. Background Images
L'image est gérée par css. A l'origine, le background image était utilisé pour créer des fonds décoratifs à thème.
Aujourd'hui un background image peut être utilisé comme alternative aux éléments `<img>`, à ceci près que les images ne sont pas référencées et n'ont pas de texte alternatif. 

```html
<div class='container'></div>
``` 
```css
.container{
  width: 300px;
  height: 300px;
  background-image:url(https://images.pexels.com/photos/354984/pexels-photo-354984.jpeg?w=1260&h=750&auto=compress&cs=tinysrgb);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center right;
  
}
```

# 3. Background image fixe
Très utilisée dans des modèles one Page.
```html
<section class="s1">
  <h1>WEBDESIGN</h1>
</section>
<section class="s2">
    <h1>SERVICES</h1>
</section>
<section class="s3">
  <h1>ABOUT US</h1>
</section>
<section class="s4">
  <h1>CONTACT</h1>
</section>
```
```css
*{ margin: 0; }
section {  height: 100vh; display:flex; }
section h1{
  margin:auto; 
  color:white;
  font-weight: 400;
  letter-spacing: 5px;
  font-size: 3rem;
}

.s1{  background:#64B5F6;}

.s2 {
  height: 300px;
  background:url(https://images.pexels.com/photos/248797/pexels-photo-248797.jpeg?w=940&h=650&auto=compress&cs=tinysrgb) no-repeat fixed center center;
  background-size: cover;
}

.s3 {  background: #66BB6A;}
.s4{   background: pink;}

```
