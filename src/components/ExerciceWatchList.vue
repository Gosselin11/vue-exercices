<template>
  <div>
    <h1>WatchList (Films à voir)</h1>

    <input
      type="text"
      placeholder="Nom du film"
      v-model="nomFilm"
    />
    <button @click="ajouterFilm">Ajouter à votre Liste</button>

    <h2 v-if="mesFilms.length !== 0">
      {{ nomFilm }}
    </h2>
    <p v-else>
      Pas encore de Films dans votre Liste
    </p>

    <ul>
      <li v-for="(film, index) in mesFilms" :key="index">
        {{ film }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const nomFilm = ref('')
const mesFilms = ref([])

function ajouterFilm () {
  if (nomFilm.value.trim() === '') {
    return
  }
  mesFilms.value.push(nomFilm.value.trim())
}
</script>
