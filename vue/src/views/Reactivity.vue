<template>
  <div class="reactivity">
    <div class="inputs">
      
      <div class="row one">

        <Button v-if="gtChosen && btChosen" @click="addMT(); mtChosen = !mtChosen" class="input mt">Milk Tea</Button>
        <Button v-if="mtChosen && btChosen" @click="addGT(); gtChosen = !gtChosen" class="input gt">Green Tea</Button>
        <Button v-if="mtChosen && gtChosen" @click="addBT(); btChosen = !btChosen" class="input bt">Black Tea</Button>

      </div>

      <div class="row two">

        <Button v-if="hiChosen && liChosen" @click="addNI(); niChosen = !niChosen" class="input">No Ice</Button>
        <Button v-if="niChosen && liChosen" @click="addHI(); hiChosen = !hiChosen" class="input">Half Ice</Button>
        <Button v-if="niChosen && hiChosen" @click="addLI(); liChosen = !liChosen" class="input">Less Ice</Button>

      </div>

      <div class="row three">

        <Button v-if="lsChosen && esChosen" @click="add50S(); hsChosen = !hsChosen" class="input">50% Sugar</Button>
        <Button v-if="hsChosen && esChosen" @click="add75(); lsChosen = !lsChosen" class="input">75% Sugar</Button>
        <Button v-if="hsChosen && lsChosen" @click="add125(); esChosen = !esChosen" class="input">125% Sugar</Button>

      </div>

      <div class="row four">

        <Button @click="clearChoices" class="input clear">Clear</Button>
        <Button @click="addTap" class="input">Tapioca</Button>
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
        mtChosen: true,
        gtChosen: true,
        btChosen: true,
        niChosen: true,
        hiChosen: true,
        liChosen: true,
        hsChosen: true,
        lsChosen: true,
        esChosen: true,
      }
    },
    methods: {
      addMT () {
        const mtIndex = this.choices.indexOf('Milk Tea')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Milk Tea')
        }
      },
      addGT () {
        const mtIndex = this.choices.indexOf('Green Tea')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Green Tea')
        }
      },
      addBT () {
        const mtIndex = this.choices.indexOf('Black Tea')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Black Tea')
        }
      },
      addNI () {
        const mtIndex = this.choices.indexOf('No Ice')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('No Ice')
        }
      },
      addHI () {
        const mtIndex = this.choices.indexOf('Half Ice')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Half Ice')
        }
      },
      addLI () {
        const mtIndex = this.choices.indexOf('Less Ice')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Less Ice')
        }
      },
      add50 () {
        const mtIndex = this.choices.indexOf('50% Sugar')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('50% Sugar')
        }
      },
      add75 () {
        const mtIndex = this.choices.indexOf('75% Sugar')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('75% Sugar')
        }
      },
      add125 () {
        const mtIndex = this.choices.indexOf('125% Sugar')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('125% Sugar')
        }
      },
      addTap () {
        const mtIndex = this.choices.indexOf('Tapioca')
        console.log(mtIndex)
        if (mtIndex != -1) {
          this.choices.splice(mtIndex, 1)
        } else {
          this.choices.push('Tapioca')
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
      },
      enterChoices () {
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