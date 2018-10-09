<template>
  <v-app id="app">
    <Toolbar/>
    <Content/>
    <Footer/>
  </v-app>
</template>

<script>
  import Content from './components/Content'
  import Footer from './components/Footer'
  import Toolbar from './components/Toolbar'

  export default {
    components: {
      Content,
      Footer,
      Toolbar
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    background-color: #898989;
  }

</style>
