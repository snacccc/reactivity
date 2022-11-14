<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        <Button @click="addMT" class="input mt">Milk Tea</Button>
        <Button @click="addGT" class="input gt">Green Tea</Button>
        <Button @click="addBT" class="input bt">Black Tea</Button>

      </div>

      <div class="row two">

        <Button @click="" class="input">4</Button>
        <Button @click="" class="input">5</Button>
        <Button @click="" class="input">6</Button>

      </div>

      <div class="row three">

        <Button @click="" class="input">1</Button>
        <Button @click="" class="input">2</Button>
        <Button @click="" class="input">3</Button>

      </div>

      <div class="row four">

        <Button @click="clearChoices" class="input clear">Clear</Button>
        <Button @click="" class="input">Add Another</Button>
        <Button @click="enterChoices" class="input enter">Enter</Button>

      </div>

    </div>

    <div class="output">
        <header v-for="choice in choices"> {{ choice }}</header>
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
        choices: [],
      }
    },
    methods: {
      addMT () {
        this.choices.push('Milk Tea')
      },
      addGT () {
        this.choices.push('Green Tea')
      },
      addBT () {
        this.choices.push('Black Tea')
      },
      clearChoices () {
        this.choices.splice(0);
      },
      enterChoices () {
        console.log(this.choices)
      },
    }
  }

</script>

<style scoped>
  .reactivity {
    display: flex;
    flex-direction: row;
    margin: 1rem;
  }

  .row {
    margin: 0.5rem;
  }

  .input {
    margin: 0.5rem;
    width: 5.5rem;
    height: 4.5rem;
    box-shadow: 0px 10px gray;
  }

  .input:active {
    transform: translateY(5px);
    box-shadow: 0px 5px gray
  }

  .enter {
    background-color: var(--enterprimary);
    box-shadow: 0px 10px var(--entershadow);
  }

  .enter:active {
    box-shadow: 0px 5px var(--entershadow);
  }

  .clear {
    background-color: var(--clearprimary);
    box-shadow: 0px 10px var(--clearshadow);
  }

  .clear:active {
    box-shadow: 0px 5px var(--clearshadow);
  }

  .output {
    display: flex;
    flex-direction: column;
    font-size: 1.5rem;
    color: white;
    margin: 1rem;
  }

</style>