<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import Exercice from './components/Exercice.vue'
// import TpDataBinding from './components/TpDataBinding.vue'
// import Counter from './components/Counter.vue'
// import TpEventBinding from './components/TpEventBinding.vue'
// import Bug from './components/Bug.vue'
// import TpReactivite from './components/TpReactivite.vue'
// import ExerciceDynamique from './components/ExerciceDynamique.vue'
// import ExerciceDynamiqueCss from './components/ExerciceDynamiqueCss.vue'
// import TpStyleDynamique from './components/TpStyleDynamique.vue'
import ExerciceWatchList from './components/ExerciceWatchList.vue'
</script>

<template>
  <div>
   <!-- <a href="https://vite.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>

    <h1>Bonjour depuis App.vue</h1>
    <Exercice/>

    <HelloWorld msg="Vite + Vue" />
    <TpDataBinding />
    <Counter/>
     <TpEventBinding />
     <Bug />
     <TpReactivite />
     <ExerciceDynamique />
     <ExerciceDynamiqueCss />
     <TpStyleDynamique />-->
     <ExerciceWatchList />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

