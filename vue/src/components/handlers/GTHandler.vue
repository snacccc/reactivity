<template>
  <Button>
    <slot>Button</slot>
  </Button>
</template>

<script>

  import Button from '../Button.vue';
  import gtChosen from './handler-variables.js'

  export default {
    name: "GTHandler",
    props: ['choice', 'inputs'],  
    components: {
      Button,
    }, methods: {
      gtHandler (choice) {
        gtChosen = !gtChosen
        const choiceIndex = this.choices.indexOf(choice)
        if (choiceIndex != -1) {
          this.choices.splice(choiceIndex, 1)
        } else {
          this.choices.push(choice)
      }
      }
    },
    mounted() {
      inputs.$on('input', this.gtHandler)
    }
  }

</script>