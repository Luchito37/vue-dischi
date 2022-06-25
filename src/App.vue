<template>
  <div id="app">
    <HeaderPart></HeaderPart>

    <DiscList></DiscList>
  </div>
</template>

<script>
import HeaderPart from './components/HeaderPart.vue'
import DiscList from './components/DiscList.vue'

export default {
  name: 'App',
  components: {
    HeaderPart,
    DiscList
  }
}
</script>

<style lang="scss">

@import "~bootstrap/scss/bootstrap";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: linear-gradient(0deg, rgb(54 54 54) 0%, rgb(0 0 0) 100%);
}
</style>
