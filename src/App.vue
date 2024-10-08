<template>
  <div class="container_app">
    <h1>Démo de composants</h1>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Beatae et doloribus, sunt iusto minus similique, accusantium, dolores hic assumenda consequatur dolore? Natus velit unde consequatur tempora ut sapiente non, nisi ad sed minima quidem ducimus labore cumque obcaecati libero inventore reiciendis. Nulla dolorem ab officiis deleniti, unde vitae non quisquam.
    </p>
    <label>
      <input type="checkbox" v-model="showCount">
      Afficher le compteur
    </label>
    <ul>
      <template v-for="item of items">
        <li v-if="item % 2 === 0">
          {{ item }}
        </li>
      </template>
    </ul>
    <KeepAlive>
      <component :is="componentToShow" />
    </KeepAlive>
  </div>

</template>


<script setup>
  import { ref, computed } from 'vue'
  import Compteur from './components/Compteur.vue';
  import Placeholder from './components/Placeholder.vue';

  const items = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
  const showCount = ref(false)
  const componentToShow = computed(() => {
    if(showCount.value) {
      return Compteur
    }
    return Placeholder
  })

</script>


<style lang="scss">
  body {
    background-color: #333;
    color: #fff;
    font-family: sans-serif;
    .container_app {
      h1 {
        text-align: center;
      }
      label {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 8px;
        input {
          width: 20px;
          height: 20px;
          display: block;
        }
      }
      ul {
        list-style: none;
        display: flex;
        gap: 8px;
        justify-content: center;
      }
    }
  }
</style>
