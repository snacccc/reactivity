<template>
  <Button>
    <slot>Button</slot>
  </Button>
</template>

<script>

  import Button from '../Button.vue';
  import mtChosen from './handler-variables.js'

  export default {
    name: "MTHandler",
    props: ['choice', 'inputs'],  
    components: {
      Button,
    }, methods: {
      mtHandler (choice) {
        mtChosen = !mtChosen
        const choiceIndex = this.choices.indexOf(choice)
        if (choiceIndex != -1) {
          this.choices.splice(choiceIndex, 1)
        } else {
          this.choices.push(choice)
      }
      }
    },
    mounted() {
      inputs.$on('input', this.mtHandler)
    }
  }

</script>