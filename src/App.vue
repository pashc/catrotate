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
    color: #2c3e50;
    margin-top: 60px;
  }

  body {
    background-color: #c6c6c6;
  }

</style>
