<template>

  <div class="home">
    <header class="header">
      A collection of all my Vue Projects (Currently WIP)
    </header>
  </div>

  <Test @addHeader="tester('test')"/>
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
    }, data () {
      return {
        testArray: [],
      }
    }, methods: {
      tester (x) {
        this.testArray.push(x)
      }
    },
    }

</script>

<style scoped>

  .home {
    margin: 1rem;
    color: white;
  }

</style>