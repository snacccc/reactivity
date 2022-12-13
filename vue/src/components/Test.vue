<template>
  <button @click="addHeader(test)">Test</button>
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