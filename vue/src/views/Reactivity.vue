<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        <Input v-if="!gtChosen && !btChosen && !entered" :choice="'Milk Tea'" :inputs="inputs" @click="mtChosen = !mtChosen" class="input">Milk Tea</Input>
        <Button v-else class="input" disabled>Milk Tea</Button>
        <Input v-if="!mtChosen && !btChosen && !entered" @addItem="inputHandler('Green Tea')" @click="gtChosen = !gtChosen" class="input">Green Tea</Input>
        <Button v-else class="input" disabled>Green Tea</Button>
        <Input v-if="!mtChosen && !gtChosen && !entered" @addItem="inputHandler('Black Tea')" @click="btChosen = !btChosen" class="input">Black Tea</Input>
        <Button v-else class="input" disabled>Black Tea</Button>

      </div>

      <div class="row two">

        <Input v-if="!hiChosen && !liChosen && !entered" @addItem="inputHandler('No Ice')" @click="niChosen = !niChosen" class="input">No Ice</Input>
        <Button v-else class="input" disabled>No Ice</Button>
        <Input v-if="!niChosen && !liChosen && !entered" @addItem="inputHandler('Half Ice')" @click="hiChosen = !hiChosen" class="input">Half Ice</Input>
        <Button v-else class="input" disabled>Half Ice</Button>
        <Input v-if="!niChosen && !hiChosen && !entered" @addItem="inputHandler('Less Ice')" @click="liChosen = !liChosen" class="input">Less Ice</Input>
        <Button v-else class="input" disabled>Less Ice</Button>

      </div>

      <div class="row three">

        <Input v-if="!lsChosen && !esChosen && !entered" @addItem="inputHandler('50% Sugar')" @click="hsChosen = !hsChosen" class="input">50% Sugar</Input>
        <Button v-else class="input" disabled>50% Sugar</Button>
        <Button v-if="!hsChosen && !esChosen && !entered" @addItem="inputHandler('75% Sugar')" @click="lsChosen = !lsChosen" class="input">75% Sugar</Button>
        <Button v-else class="input" disabled>75% Sugar</Button>
        <Button v-if="!hsChosen && !lsChosen && !entered" @addItem="inputHandler('125% Sugar')" @click="esChosen = !esChosen" class="input">125% Sugar</Button>
        <Button v-else class="input" disabled>125% Sugar</Button>

      </div>

      <div class="row four">

        <Button v-if="!entered" @click="clearChoices" class="input clear">Clear</Button> 
        <Button v-else-if="confirmed" class="input clear" disabled>Cancel</Button> 
        <Button v-else class="input clear" @click="entered = !entered">Cancel</Button> 
        <Button v-if="!entered" @click="addItem('Tapioca'); tapioca = !tapioca" class="input">Tapioca</Button>
        <Button v-else class="input" disabled>Tapioca</Button>
        <Button v-if="(mtChosen && !entered) || (gtChosen && !entered) || (btChosen && !entered)" @click="entered = !entered" class="input enter">Enter</Button>
        <Button v-else-if="entered && !confirmed" class="input enter" @click="addItem('Order Confirmed!'); confirmed = !confirmed">Confirm Order</Button>
        <Button v-else-if="!confirmed" class="input enter" disabled>Enter</Button>
        <Button v-if="confirmed" class="input enter" @click="clearChoices">Order Again</Button>

      </div>

    </div>

    <div class="output">
        <header v-for="choice in choices"> {{ choice }} </header>
    </div>

    <img src="../img/bubblemilktea.png" v-if="(confirmed && mtChosen && tapioca)" class="image">
    <img src="../img/bubblegreentea.png" v-if="(confirmed && gtChosen && tapioca)" class="image">
    <img src="../img/bubbleblacktea.png" v-if="(confirmed && btChosen && tapioca)" class="image">
    <img src="../img/milktea.png" v-if="(confirmed && mtChosen && !tapioca)" class="image">
    <img src="../img/greentea.png" v-if="(confirmed && gtChosen && !tapioca)" class="image">
    <img src="../img/blacktea.png" v-if="(confirmed && btChosen && !tapioca)" class="image">

  </div>
</template>

<script>

  import Button from '../components/Button.vue'
  import Input from '../components/Input.vue'

  export default {
    name: 'reactivity',
    components: {
      Button,
      Input,
    },
    data() {
      return {
        choices: [],
        mtChosen: false,
        gtChosen: false,
        btChosen: false,
        niChosen: false,
        hiChosen: false,
        liChosen: false,
        hsChosen: false,
        lsChosen: false,
        esChosen: false,
        tapioca: false,
        entered: false,
        confirmed: false,
      }
    },
    methods: {
      inputHandler () {
        this.inputs.$emit('input')
    },
      clearChoices () {
        this.choices.splice(0);
        this.mtChosen = false;
        this.gtChosen = false;
        this.btChosen = false;
        this.niChosen = false;
        this.hiChosen = false;
        this.liChosen = false;
        this.hsChosen = false;
        this.lsChosen = false;
        this.esChosen = false;
        this.tapioca = false;
        this.entered = false;
        this.confirmed = false;
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

  .image {
    height: 24rem;
    border: 0.4rem solid;
    border-color: var(--accent);
  }

</style>