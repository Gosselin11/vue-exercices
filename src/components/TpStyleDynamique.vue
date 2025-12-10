<template>
  <div>
    <h1>TP : Dynamic Styling</h1>

    <!-- Input 1  -->
    <div>
      <input
        type="text"
        placeholder="Tape hello ou world"
        v-model="textClass"
      />

      <button @click="showFirst = !showFirst">
        {{ showFirst ? 'Cacher 1er titre' : 'Afficher 1er titre' }}
      </button>

      <!-- 1er titre  -->
      <h2
        v-if="showFirst"
        :class="firstTitleClass"
      >
        Hello World (class dynamique)
      </h2>
    </div>

    <hr />

    <!-- Input 2 -->
    <div>
      <input
        type="text"
        placeholder="Tape une couleur (red, green, yellow...)"
        v-model="bgColor"
      />

      <!-- 2e titre  -->
      <h2 :style="{ backgroundColor: bgColor }">
        Hello World (couleur dynamique)
      </h2>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const showFirst = ref(true)
const textClass = ref('')
const bgColor = ref('')

// Classe dynamique
const firstTitleClass = computed(() => {
  if (textClass.value === 'hello') {
    return 'maClasseHello'
  }
  if (textClass.value === 'world') {
    return 'maClasseWorld'
  }
  return ''
})
</script>

<style scoped>
.maClasseHello {
  color: white;
  background-color: dodgerblue;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}

.maClasseWorld {
  color: white;
  background-color: purple;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}
</style>
