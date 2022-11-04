<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        <Button class="numpad">7</Button>
        <Button class="numpad">8</Button>
        <Button class="numpad">9</Button>

      </div>

      <div class="row two">

        <Button class="numpad">4</Button>
        <Button class="numpad">5</Button>
        <Button class="numpad">6</Button>

      </div>

      <div class="row three">

        <Button class="numpad">1</Button>
        <Button class="numpad">2</Button>
        <Button class="numpad">3</Button>

      </div>

      <div class="row four">

        <Button class="numpad clear">X</Button>
        <Button class="numpad">0</Button>
        <Button class="numpad enter">Enter</Button>

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
  .reactivity {
    display: flex;
    flex-direction: column;
    margin: 1rem;
  }

  .row {
    margin: 0.5rem;
  }

  .numpad {
    margin: 0.5rem;
  }

  .enter {
    background-color: var(--enterprimary);
    box-shadow: 0px 8px var(--entershadow);
  }

  .enter:active {
    box-shadow: 0px 4px var(--entershadow);
  }

  .clear {
    background-color: var(--clearprimary);
    box-shadow: 0px 8px var(--clearshadow);
  }

  .clear:active {
    box-shadow: 0px 4px var(--clearshadow);
  }

</style>