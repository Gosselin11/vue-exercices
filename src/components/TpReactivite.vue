<template>
  <div>
    <h1>TP : Le Numéro Gagnant</h1>

   <p>le nombre : {{ nombreMystere }} = {{ messageMystere }}</p>

    <button @click="ajouter1">+1</button>
    <button @click="ajouter5">+5</button>
  </div>
</template>

<script setup>
import { ref, counter, watch } from 'vue'

const nombreMystere = ref(0)

function ajouter1 () {
  nombreMystere.value += 1
}

function ajouter5 () {
  nombreMystere.value += 5
}

const messageMystere = counter(() => {
  if (nombreMystere.value < 7) {
    return 'ESSAIE ENCORE'
  } else if (nombreMystere.value === 7) {
    return nombreMystere.value
  } else {
    return 'Tu as dépassé le Nb Mystère'
  }
})

watch(nombreMystere, (newValue) => {
  if (newValue > 30) {
    setTimeout(() => {
      nombreMystere.value = 0
    }, 3000)
  }
})
</script>

