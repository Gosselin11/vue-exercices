<template>
  <div>
    <h1>TP: Conditional / List Rendering</h1>
    <h2>Ma liste de livres</h2>

    <input
      type="text"
      placeholder="Titre du livre"
      v-model="nouveauLivre"
    />
    <button @click="ajouterLivre">Ajouter à la liste</button>

    <button @click="toggleListe">
      {{ afficherListe ? 'Masquer Liste' : 'Afficher Liste' }}
    </button>
<div v-if="livres.length > 0" class="card">
    <ul v-if="afficherListe" class="book-list">
      <li
        v-for="(livre, index) in livres"
        :key="index"
        @click="supprimerLivre(index)"
      >
      <span class="badge">{{ index }}</span>
      <span class="title">{{ livre }}</span>
         
      </li>
    </ul>
    </div>
    <p v-else>Aucun livre pour le moment</p>
  </div>
  
</template>

<script setup>
import { ref } from 'vue'

const nouveauLivre = ref('')
const livres = ref([])          
const afficherListe = ref(true) 

function ajouterLivre () {
  const titre = nouveauLivre.value.trim()
  if (titre === '') return
  livres.value.push(titre)
  nouveauLivre.value = ''
}

function supprimerLivre (index) {
  livres.value.splice(index, 1)
}

function toggleListe () {
  afficherListe.value = !afficherListe.value
}
</script>


<style scoped>
.card {
  margin-top: 1rem;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  background-color: #f5f5ff;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08);
}

.book-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.book-list li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.4rem 0;
  cursor: pointer;
}

.book-list li:hover {
  background-color: #e4e4ff;
}

.badge {
  min-width: 24px;
  text-align: center;
  border-radius: 999px;
  background-color: #6366f1;
  color: white;
  font-size: 0.8rem;
  padding: 0.1rem 0.4rem;
}

.title {
  font-weight: 500;
}
</style>
