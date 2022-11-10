<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        <Button @click="add7" class="numpad">7</Button>
        <Button @click="add8" class="numpad">8</Button>
        <Button @click="add9" class="numpad">9</Button>

      </div>

      <div class="row two">

        <Button @click="add4" class="numpad">4</Button>
        <Button @click="add5" class="numpad">5</Button>
        <Button @click="add6" class="numpad">6</Button>

      </div>

      <div class="row three">

        <Button @click="add1" class="numpad">1</Button>
        <Button @click="add2" class="numpad">2</Button>
        <Button @click="add3" class="numpad">3</Button>

      </div>

      <div class="row four">

        <Button @click="clearNums" class="numpad clear">Clear</Button>
        <Button @click="add0" class="numpad">0</Button>
        <Button @click="enterNums" class="numpad enter">Enter</Button>

      </div>

    </div>

    <div class="output">
        <header v-for="number in numbers"> {{ number.value }}</header>
      </div>

  </div>
</template>

<script>

  import Button from '../components/Button.vue'

  export default {
    name: 'reactivity',
    components: {
      Button,
    },
    data() {
      return {
        numbers: [],
      }
    },
    methods: {
      add0 () {
        this.numbers.push({value: '0'})
      },
      add1 () {
        this.numbers.push({value: '1'})
      },
      add2 () {
        this.numbers.push({value: '2'})
      },
      add3 () {
        this.numbers.push({value: '3'})
      },
      add4 () {
        this.numbers.push({value: '4'})
      },
      add5 () {
        this.numbers.push({value: '5'})
      },
      add6 () {
        this.numbers.push({value: '6'})
      },
      add7 () {
        this.numbers.push({value: '7'})
      },
      add8 () {
        this.numbers.push({value: '8'})
      },
      add9 () {
        this.numbers.push({value: '9'})
      },
      clearNums () {
        this.numbers.splice(0);
      },
      enterNums () {
        console.log(this.numbers)
      },
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

  .output {
    display: flex;
    flex-direction: row;
    font-size: 1.5rem;
    color: white;
    margin: 1rem;
  }

</style>