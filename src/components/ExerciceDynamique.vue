<template>
  <div>
    <h1>Exercice : Style Dynamique (inline)</h1>

    <div
      class="card"
      @click="selectionCard(1)"
      :style="{ backgroundColor: selectCard1 ? 'red' : 'blue' }"
    >
      Card 1
    </div>

    <div
      class="card"
      @click="selectionCard(2)"
      :style="{ backgroundColor: selectCard2 ? 'green' : 'violet' }"
    >
      Card 2
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const selectCard1 = ref(false)
const selectCard2 = ref(false)

function selectionCard (uneCard) {
  if (uneCard === 1) {
    selectCard1.value = !selectCard1.value   // bonus : toggle
  }
  if (uneCard === 2) {
    selectCard2.value = !selectCard2.value   // bonus : toggle
  }
}
</script>

<style scoped>
.card {
  width: 200px;
  height: 100px;
  margin: 1rem;
  border-radius: 8px;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
</style>
