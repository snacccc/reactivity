<template>

    <div class="app">
      <RouterLink class="router home" to="/">Home</RouterLink>
      <header>|</header>
      <RouterLink class="router test" to="/test">Test</RouterLink>
    </div>

    <RouterView/>
</template>

<style scoped>

  @import 'components/variables.css';
  
  .app {
    display: flex;
    flex-direction: row;
    background-color: var(--primarydark);
    color: white;
    font-size: 2rem;
    height: 5rem;
    align-items: center;
    margin-bottom: 2rem;
  }

  a {
    text-decoration: none;
    color: inherit;
  }


  .router {
    margin: 0 3rem;
  }

  .router:hover {
    text-decoration: underline;
  }

  .router:active {
    color: blue;
  }

</style>