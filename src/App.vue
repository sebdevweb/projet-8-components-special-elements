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
  <footer>
    <p>Lorem ipsum dolor sit amet consectetur.</p>
  </footer>

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
      p {
        max-width: 700px;
        margin: 30px auto;
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
        background-color: burlywood;
        padding: 20px;
        max-width: 300px;
        margin: 0 auto;
        margin-top: 20px;
        border-radius: 10px;
        li {
          font-size: 20px;
          font-weight: bold;
        }
      }
    }
    footer {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      dialog {
      background: rgba(0, 0, 0, 0.3);
      padding: 30px;
      margin-top: 20px;
      max-width: 600px;
      border-radius: 10px;
      border: 2px dashed #fff;
      color: #fff;
      font-size: 20px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
    }
    }
  }
</style>
