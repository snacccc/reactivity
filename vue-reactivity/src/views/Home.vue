<template>

  <div class="home">
    <header class="header">
      A collection of all my Vue Projects (Currently WIP)
    </header>
  </div>

</template>

<script>

  import Button from '../components/Button.vue'

  export default  {
    name: 'home',
    components: {
      Button,
    }
    }

</script>

<style scoped>

  .home {
    margin: 1rem;
    color: white;
  }

</style>