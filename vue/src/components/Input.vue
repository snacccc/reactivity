<template>
  <Button>
    <slot>Button</slot>
  </Button>
</template>

<script>

  import Button from '../components/Button.vue';

  export default {
    name: "Input",
    props: ['choice', 'inputs'],  
    components: {
      Button,
    }, methods: {
      inputHandler (choice) {
        const choiceIndex = this.choices.indexOf(choice)
        if (choiceIndex != -1) {
          this.choices.splice(choiceIndex, 1)
        } else {
          this.choices.push(choice)
      }
      }
    },
    mounted() {
      inputs.$on('input', this.inputHandler)
    }
  }

</script>