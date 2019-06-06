<template>
  <div id="app">
    <Header />
    <SimonSays />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import SimonSays from './components/SimonSays.vue';

export default {
  name: 'app',
  components: {
    Header,
    SimonSays
  }
}
</script>

<style lang="scss">

@import "@/styles/_variables.scss"; 

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* color: $red; */

}
</style>
