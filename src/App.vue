<script setup lang="ts">
import { ref } from 'vue'
import { onErrorCaptured } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
const menuIsOpen = ref(false)
onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>
  <header>
    <button
    @pointerdown="menuIsOpen = !menuIsOpen"
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-full border-2 border-red-600 bg-red-300 px-2"
  >
    menu
  </button >
  <nav id="mainNav" :class="{ hidden: !menuIsOpen }">
    <ul>
      <li>
        <RouterLink to="/" class="text-red-500 underline"> Accueil </RouterLink>
      </li>
      <li>
        <RouterLink to="/accordeon" class="text-red-500 underline"> Accordéon </RouterLink>
      </li>
    </ul> 
  </nav>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
