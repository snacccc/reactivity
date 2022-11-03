<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="rowOne">

        <Button>7</Button>
        <Button>8</Button>
        <Button>9</Button>

      </div>

      <div class="rowTwo">

        <Button>4</Button>
        <Button>5</Button>
        <Button>6</Button>

      </div>

      <div class="rowThree">

        <Button>1</Button>
        <Button>2</Button>
        <Button>3</Button>

      </div>

      <div class="rowFour">

        <Button>X</Button>
        <Button>0</Button>
        <Button>Enter</Button>

      </div>

    </div>

    <div class="output">
        <p>Tester</p>
      </div>

  </div>
</template>

<script>

  import Button from '../components/Button.vue'

  export default {
    name: 'reactivity',
    components: {
      Button,
    }
  }

</script>

<style scoped>

  .test {
    margin: 1rem;
    display: flex;
    flex-direction: row;
  }

  .inputs {
    display: flex;
    flex-direction: column;
    margin: 1rem;
  }

</style>