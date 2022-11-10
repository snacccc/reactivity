<template>
  <button class="button">
    <slot>Button</slot>
  </button>
</template>

<script>
  export default {
    name:"Button",
  };
</script>

<style scoped>
  .button {
      width: 4rem;
      height: 3rem;
      cursor: pointer;
      border: none;
      border-radius: 1rem;
      box-shadow: 0px 8px gray;
   }
  .button:active {
      transform: translateY(4px);
      box-shadow: 0px 4px gray;
   }
</style>