<template>
  <div class="card">
    <h1>Tp-Databinding : Profil utilisateur (interpolation + v-bind)</h1>

   
    <img
      :src="userImage"
      :alt="userName"
      class="avatar"
    />

    <h2>{{ userName }}</h2>
    <input type="text" :value="userName" />

    <p>Âge : {{ age }} ans</p>

    <p>Âge + 10 : {{ augmenterAge() }} ans</p>

    <p>NB fétiche : {{ numberRandom() }}</p>

    <p>Texte avec du HTML non interprété : {{ htmlProfil }}</p>
    <p v-html="htmlProfil"></p>
  </div>
</template>

<script setup>
import { ref } from 'vue'


const userImage = ref('https://via.placeholder.com/150') 
const userName = ref('Dr Mario')
const age = ref(30)

function augmenterAge () {
  return age.value + 10
}

function numberRandom () {
  return Math.random()
}

const htmlProfil = ref('<strong>Profil utilisateur stylé en HTML</strong>')
</script>
