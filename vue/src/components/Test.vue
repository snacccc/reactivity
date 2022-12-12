<template>
  <button @click="$emit('testEvent', addHeader(x))">Test</button>
</template>

<script>
  export default {
    name: "Test",
    data() {
      return {
        testArray: [],
      }
    },
    methods: {
      addHeader(x) {
        this.testArray.push(x)
      }
    }
  };
</script>