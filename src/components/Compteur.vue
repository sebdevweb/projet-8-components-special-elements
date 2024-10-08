<template>
  <div class="container_count">
    <p>Nombre : {{ count }}</p>
    <button @click="count++">Incrémenter</button>
  </div>
</template>


<script setup>
  import { ref } from 'vue'

  const count = ref(0)
</script>

<style lang="scss">
  .container_count {
    display: flex;
    justify-content: center;
    gap: 12px;
    align-items: center;
    button {
      padding: 20px;
      font-size: 16px;
      border: none;
      border-radius: 5px;
      background-color: crimson;
      color: #fff;
      font-weight: 500;
      letter-spacing: 1px;
      cursor: pointer;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
      &:hover {
        background-color: rgb(198, 29, 63);
        box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
      }
    }
  }
</style>