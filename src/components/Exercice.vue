

<template>
  <div>
    <h2>Mon nouveau composant</h2>
    <p>Ceci est mon premier composant perso.</p>
  </div>

<!-- Exemple d'utilisation de la TECHNIQUE DE TEXT INTERPOLATION -->
  <h1>Ici c'est Le Composant TEXT-INTERPOLATION.VUE</h1>
    <h2>{{ name }}</h2>
    <h3>{{ age }} ans</h3>
    
    <h4>Les passions de {{name}} : </h4>
    <p>{{passion}}</p>
    <h5>{{ passion.tv }} et {{ passion.sport }}</h5>

    <hr>
    <!-- Exemple d'execution de fonction dans le template -->
    <p>{{ superAffichage() }}</p>
<!-- Exemple de calcul directement dans le template -->
    <p>{{ 3000+2 }}</p>
    <!-- Exemple d'utilisation de condition ternaire dans le template -->
    <p>{{ name === 'Mathias' ? 'Mathias est un élève ringard' : 'Mathias est un élève cool' }}</p>
 <hr>
     <p>unLivre : {{ unLivre }}</p>
    <p>isOnline : {{ isOnline }}</p>
    <p>unNombre : {{ unNombre }}</p>
    <p>{{ unTableau }}</p>
    <p>{{ unObjet }}</p>
    <p>{{ fonctionTest() }}</p>
    <p>Texte avec HTML : {{ html }}</p>
    <hr>
    <p>{{ duHTMLTemplate }}</p>
    <!-- Ceci n'est pas interprété comme du HTML, c'est une chaîne de caractères a-->
    <!-- Pour interpréter du HTML, on peut utiliser v-html -->
    <p v-html="duHTMLTemplate"></p>
</template>



<script setup>
import { ref } from 'vue';
// On va déclarer des variables avec let et const
// Avec les {{ }} on peut afficher les variables dans le template
const name = 'Mathias';
let age = 19;
const passion = {
    tv: 'Joséphine Ange',
    sport:'Curling'
}
// On peut aussi faire des fonctions dans le composant
// Eventuellement on peut executer une fonction dans le template avec {{ superAffichage() }}
function superAffichage() {
    return 'La super phrase qui tue ! '
}
const unLivre = 'Les mémoires de Steven Seagal'
const isOnline = false
const unNombre = 1234567890
const unTableau = ['du texte', 99]
const unObjet = { name: 'COOL', tel: '12748312' }

function fonctionTest () {
  return 'Hello World'
}
const html = '<h1>Du HTML</h1>'
const duHTMLTemplate = ref('<h1>Du HTML</h1>');
</script>