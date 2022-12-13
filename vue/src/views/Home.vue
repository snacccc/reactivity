<template>

  <div class="home">
    <header class="header">
      A collection of all my Vue Projects (Currently WIP)
    </header>
  </div>

  <p>{{ testArray }}</p>

</template>

<script>

  import Button from '../components/Button.vue'
  import Test from '../components/Test.vue'

  export default  {
    name: 'home',
    components: {
      Button,
      Test,
    }
    }

</script>

<style scoped>

  .home {
    margin: 1rem;
    color: white;
  }

</style>