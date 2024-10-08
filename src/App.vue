<template>
  <h1>Démo de composants</h1>
  <p>
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Beatae et doloribus, sunt iusto minus similique, accusantium, dolores hic assumenda consequatur dolore? Natus velit unde consequatur tempora ut sapiente non, nisi ad sed minima quidem ducimus labore cumque obcaecati libero inventore reiciendis. Nulla dolorem ab officiis deleniti, unde vitae non quisquam.
  </p>
  <label>
    <input type="checkbox" v-model="showCount">
    Afficher le compteur
  </label>
  <template v-for="item of items">
    <li v-if="item % 2 === 0">
      {{ item }}
    </li>
</template>
</template>


<script setup>
  import { ref } from 'vue'
  import Compteur from './components/Compteur.vue';

  const items = ref([1, 2, 3, 4, 5])

</script>


<style lang="scss">
  body {
    background-color: #333;
    color: #fff;
    font-family: sans-serif;
  }
</style>
