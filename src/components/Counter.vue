<template>
    <div>
        <h1>EventBinding (gérer les event)</h1>

        <button @click.left="decrement">-</button>
        <span>le nombre : {{ count }}</span>
        <button @click.right="increment">+</button>
    </div>
</template>

<script setup>
import {ref} from 'vue'

const count = ref(0)

function decrement () {
    count.value = count.value - 20
}
function increment (){
    count.value = count.value + 11
}
</script>