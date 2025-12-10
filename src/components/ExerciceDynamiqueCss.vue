<template>
  <div>
    <h1>Exercice : Style Dynamique (class CSS)</h1>

    <div
      class="card"
      :class="{ card1Active: selectCard1 }"
      @click="selectionCard(1)"
    >
      Card 1
    </div>

    <div
      class="card"
      :class="{ card2Active: selectCard2 }"
      @click="selectionCard(2)"
    >
      Card 2
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const selectCard1 = ref(false)
const selectCard2 = ref(false)

function selectionCard (num) {
  if (num === 1) {
    selectCard1.value = !selectCard1.value
  } else if (num === 2) {
    selectCard2.value = !selectCard2.value
  }
}
</script>

<style scoped>
.card {
 
  border-radius: 8px;
  border: 2px solid #ccc;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.card1Active {
  background-color: red;
  color: white;
}
.card2Active {
  background-color: green;
  color: white;
}
</style>
