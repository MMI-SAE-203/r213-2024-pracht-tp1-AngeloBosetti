<script setup lang="ts">
  import { ref } from 'vue'
  const maVar = ref(true)
  const maVar2 = ref(1)
</script>

<template>
    <h1>ici page de l'Accordéon</h1>
    <button ></button>
    <button @click="maVar2 = 1">Section 1</button>
        <h2 v-show="maVar2 === 1" class="text-2xl">Lien de page 1</h2>
    <button @click="maVar2 = 2">Section 2</button>
        <h2 v-show="maVar2 === 2" class="text-2xl">Lien de page 1</h2>
    <button @click="maVar2 = 3">3</button>
        <h2 v-show="maVar2 === 3" class="text-2xl">ca vaut 3</h2>
    <button @click="maVar2 =  4">4</button>
        <h2 v-show="maVar2 === 4" class="text-2xl">ca vaut 4</h2>
</template>