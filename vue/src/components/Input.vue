<template>
  <Button @click="add(x)">
    <slot>Button</slot>
  </Button>
</template>

<script>

  import Button from '../components/Button.vue';

  export default {
    name: "Input",
    components: {
      Button,
    }, methods: {
      add(x) {
        this.$emit("addItem", x)
      }
    },
  }

</script>