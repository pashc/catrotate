<template>
  <div id="app">
    <img src="https://i.giphy.com/vFKqnCdLPNOKc.gif">
    <h1>{{ msg }}</h1>
    <a href="https://www.giphy.com">
      <img src="./assets/giphy_powered_by.png">
    </a>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        msg: 'Welcome to Cat Rotate'
      }
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

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
