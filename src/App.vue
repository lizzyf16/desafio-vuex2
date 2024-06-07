<template>
  <nav>
    <h1 class="text-center">Tienda 32 Bits</h1>
  </nav>
  <TablaJuegos/>
</template>
<script>
import TablaJuegos from "./components/Tablajuegos.vue";
export default{
name: "App",
components:{
  TablaJuegos
}
}

</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
