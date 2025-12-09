<template>
    <div>
        <h1>EventBinding (gérer les event)</h1>

        <button @click="decrement">-</button>
        <span>le nombre : {{ count }}</span>
        <button @click="increment">+</button>
    </div>
</template>

<script setup>
import {ref} from 'vue'

const count = ref(0)

function decrement () {
    count.value--
}
function increment (){
    count.value++
}
</script>