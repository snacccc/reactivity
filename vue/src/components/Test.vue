<template>
  <button @click="addHeader(x)">Test</button>
</template>

<script>
  export default {
    name: "Test",
    methods: {
      addHeader(x) {
        this.$emit('addHeader', x)
      }
    }
  };
</script>