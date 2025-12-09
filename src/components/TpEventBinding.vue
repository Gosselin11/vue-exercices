<template>
  <div class="tp-event">
    <h1>TP EventBinding</h1>

    <section>
      <h2>v-on : keyup</h2>
      <input
        type="text"
        placeholder="Saisissez du texte"
        @keyup="onKeyupInput"
      />
      <p>Le contenu de l'input est : {{ textKeyup }}</p>
    </section>

    <section>
      <h2>Modificateur d'événement (@keyup.esc)</h2>
      <input
        type="text"
        placeholder="Saisissez du texte et appuyez sur 'Échap'"
        @keyup.esc="onEscValidate"
      />
      <p>La valeur confirmée par 'Échap' est : {{ textEsc }}</p>
    </section>

    <section>
      <h2>Événement @click</h2>
      <button @click="showAlert">
        Afficher une alerte
      </button>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const textKeyup = ref('')
const textEsc = ref('')

function onKeyupInput (event) {
  textKeyup.value = event.target.value
}

function onEscValidate (event) {
  textEsc.value = event.target.value
}

function showAlert () {
  alert('ALERTE GENERALE')
}
</script>
