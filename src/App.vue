<template>
  <v-app id="app">
    <Content/>
    <Footer/>
  </v-app>
</template>

<script>
  import Content from './components/Content'
  import Footer from './components/Footer'

  export default {
    components: {
      Content,
      Footer
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
  }

  body {
    background-color: #c6c6c6;
  }

</style>
