<template>
  <div>
    <h1>v-on + fonctions (PB ?)</h1>

    <button @click="decrement">-</button>
    <span>{{ count }}</span>
    <button @click="increment">+</button>

    <div>
      <input
        type="text"
        placeholder="Tape ton nom"
        v-model="userName"
      />
    </div>

    <p>{{ bugUserName() }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const count = ref(0)
const userName = ref('')

function increment () {
  count.value++
}

function decrement () {
  count.value--
}

function bugUserName () {
  console.log('fonction exécutée')
  return userName.value === '' ? 'test' : 'un autre test'
}
</script>
