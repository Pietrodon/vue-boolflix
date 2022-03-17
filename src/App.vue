<template>
  <div id="app">
    <InputComponent/>
  </div>
</template>

<script>
import InputComponent from "./components/InputComponent.vue";


export default {
  name: 'App',
  components: {
    InputComponent
    
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
  margin-top: 60px;
}
</style>
