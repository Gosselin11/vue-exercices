<template>
    <div>
        <h1>Tp-Databinding : Profil utilisateur (interpolation + v-bind)</h1>
        <img src="imageProfil" alt="name">
        <h2>{{ name }}</h2>
        <input type="text" :value="name">
    </div>
</template>