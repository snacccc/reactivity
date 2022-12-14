<template>
  <button @click="addHeader(x)">Test</button>
</template>

<script>
  export default {
    name: "Test",
    data() {
      },
    methods: {
      addHeader(x) {
        this.$emit('addHeader', x)
      }
    }
  };
</script>