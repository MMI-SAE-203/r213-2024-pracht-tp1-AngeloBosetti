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
  <header class="bg-stone-300">
    <button
    @pointerdown="menuIsOpen = !menuIsOpen"
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-full border-2 border-red-600 bg-red-300 px-2"
  >
    menu
  </button >
    <Transition
      class="transition-transform duration-800"
      enter-from-class="-translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="-translate-x-full"
    >
      <nav class="bg-stone-300 w-12" v-show="menuIsOpen">
        <ul>
          <li>
            <RouterLink to="/" class="text-zinc-800 font-semibold"> Accueil </RouterLink>
          </li>
          <li>
            <RouterLink to="/accordeon" class="text-zinc-800 font-semibold"> Accordéon </RouterLink>
          </li>
          <li>
            <RouterLink to="/bouclesurdonnees" class="text-zinc-800 font-semibold"> Boucle sur données </RouterLink>
          </li>
        </ul> 
      </nav>
    </Transition>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
