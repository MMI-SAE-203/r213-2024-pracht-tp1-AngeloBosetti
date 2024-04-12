<script setup lang="ts">
  import { ref } from 'vue'
  const sectionOpen = ref(1)
</script>

<template>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = 1">bouton 1</button>
        <p v-show="sectionOpen === 1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ratione nobis accusamus esse, quaerat qui corporis similique rerum laborum quod, modi eos reprehenderit pariatur voluptates quia nostrum iusto! Molestiae, doloribus!</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = 2">bouton 2</button>
        <p v-show="sectionOpen === 2">Aliquid eum quod officiis ipsa quidem modi magni repudiandae consectetur veniam recusandae, est rem? Quibusdam ipsa voluptates illo at consequatur, accusantium assumenda odio est tempore optio reprehenderit ex. Exercitationem, consequuntur!</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = 3">bouton 3</button>
        <p v-show="sectionOpen === 3">Vel velit quod enim. Voluptatibus officiis aperiam non quaerat voluptates commodi, totam optio eligendi deserunt quae? Beatae quisquam fugit itaque velit asperiores officia, architecto nemo laborum dicta est quam ab?</p>
    </section>
</template>