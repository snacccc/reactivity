<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        
        <Button v-if="gtChosen && btChosen && entered" @click="addItem('Milk Tea'); mtChosen = !mtChosen" class="input">Milk Tea</Button>
        <Button v-else class="input" disabled>Milk Tea</Button>
        <Button v-if="mtChosen && btChosen && entered" @click="addItem('Green Tea'); gtChosen = !gtChosen" class="input">Green Tea</Button>
        <Button v-else class="input" disabled>Green Tea</Button>
        <Button v-if="mtChosen && gtChosen && entered" @click="addItem('Black Tea'); btChosen = !btChosen" class="input">Black Tea</Button>
        <Button v-else class="input" disabled>Black Tea</Button>

      </div>

      <div class="row two">

        <Button v-if="hiChosen && liChosen && entered" @click="addItem('No Ice'); niChosen = !niChosen" class="input">No Ice</Button>
        <Button v-else class="input" disabled>No Ice</Button>
        <Button v-if="niChosen && liChosen && entered" @click="addItem('Half Ice'); hiChosen = !hiChosen" class="input">Half Ice</Button>
        <Button v-else class="input" disabled>Half Ice</Button>
        <Button v-if="niChosen && hiChosen && entered" @click="addItem('Less Ice'); liChosen = !liChosen" class="input">Less Ice</Button>
        <Button v-else class="input" disabled>Less Ice</Button>

      </div>

      <div class="row three">

        <Button v-if="lsChosen && esChosen && entered" @click="addItem('50% Sugar'); hsChosen = !hsChosen" class="input">50% Sugar</Button>
        <Button v-else class="input" disabled>50% Sugar</Button>
        <Button v-if="hsChosen && esChosen && entered" @click="addItem('75% Sugar'); lsChosen = !lsChosen" class="input">75% Sugar</Button>
        <Button v-else class="input" disabled>75% Sugar</Button>
        <Button v-if="hsChosen && lsChosen && entered" @click="addItem('125% Sugar'); esChosen = !esChosen" class="input">125% Sugar</Button>
        <Button v-else class="input" disabled>125% Sugar</Button>

      </div>

      <div class="row four">

        <Button v-if="entered" @click="clearChoices" class="input clear">Clear</Button>
        <Button v-else class="input clear" @click="entered = !entered">Cancel</Button>
        <Button v-if="entered" @click="addItem('Tapioca')" class="input">Tapioca</Button>
        <Button v-else class="input" disabled>Tapioca</Button>
        <Button v-if="entered" @click="entered = !entered" class="input enter">Enter</Button>
        <Button v-else-if="!entered && confirmed" class="input enter" @click="addItem('Order Confirmed!'); confirmed = !confirmed">Confirm Order</Button>
        <Button v-if="!confirmed" class="input enter" @click="clearChoices">Order Again</Button>

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
        mtChosen: true,
        gtChosen: true,
        btChosen: true,
        niChosen: true,
        hiChosen: true,
        liChosen: true,
        hsChosen: true,
        lsChosen: true,
        esChosen: true,
        entered: true,
        confirmed: true,
      }
    },
    methods: {
      addItem (choice) {
        const mtIndex = this.choices.indexOf(choice)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push(choice)
        }
      },
      clearChoices () {
        this.choices.splice(0);
        this.mtChosen = true;
        this.gtChosen = true;
        this.btChosen = true;
        this.niChosen = true;
        this.hiChosen = true;
        this.liChosen = true;
        this.hsChosen = true;
        this.lsChosen = true;
        this.esChosen = true;
        this.entered = true;
        this.confirmed = true;
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
    display: flex;
    justify-content: center;
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

  .enter:hover {
    background-color: var(--enterhover);
  }

  .enter:active {
    box-shadow: 0px 5px var(--entershadow);
  }

  .clear {
    background-color: var(--clearprimary);
    box-shadow: 0px 10px var(--clearshadow);
  }

  .clear:hover {
    background-color: var(--clearhover);
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