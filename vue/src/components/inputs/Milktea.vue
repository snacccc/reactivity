<template>
  <Button @click="add('Milk Tea'), mtChosen = !mtChosen">Milk Tea</Button>
</template>

<script>

  import Button from '../Button.vue';

  export default {
    name: "MilkTea",
    components: {
      Button,
    }, methods: {
      add(x) {
        this.$emit("addItem", x)
      }
    },
  }

</script>