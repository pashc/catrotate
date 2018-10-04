<template>
  <div id="app">
    <Content/>
    <a href="https://www.giphy.com">
      <img src="./assets/giphy_powered_by.png">
    </a>
  </div>
</template>

<script>
  import Content from './components/Content'

  export default {
    components: {
      Content
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
