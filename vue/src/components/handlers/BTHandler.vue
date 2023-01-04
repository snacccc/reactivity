<template>
  <Button>
    <slot>Button</slot>
  </Button>
</template>

<script>

  import Button from '../Button.vue';
  import btChosen from './handler-variables.js'

  export default {
    name: "BTHandler",
    props: ['choice', 'inputs'],  
    components: {
      Button,
    }, methods: {
      btHandler (choice) {
        btChosen = !btChosen
        const choiceIndex = this.choices.indexOf(choice)
        if (choiceIndex != -1) {
          this.choices.splice(choiceIndex, 1)
        } else {
          this.choices.push(choice)
      }
      }
    },
    mounted() {
      inputs.$on('input', this.btHandler)
    }
  }

</script>