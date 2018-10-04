<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <div class="picholder">
      <img class="overlay" :src=gifurl>
      <img style="position: relative;" src="./assets/stage_curtain.png">
    </div>

    <a href="https://www.giphy.com">
      <img src="./assets/giphy_powered_by.png">
    </a>
  </div>
</template>

<script>

  const CONFIG = require('./config/config.json')
  const giphy = require('giphy-api')(CONFIG.apikey)

  export default {
    name: 'app',
    data () {
      return {
        title: 'Cat Rotate',
        gifurl: '',
        timer: ''
      }
    },
    methods: {
      fetchGif () {
        giphy.random('cat', (err, res) => {
          if (err) {
            this.gifurl = require('./assets/error_page.png')
          } else {
            this.gifurl = res.data.fixed_height_downsampled_url
          }
        })
      }
    },
    created () {
      this.fetchGif()
      this.timer = setInterval(this.fetchGif, 6000)
    },
    destroyed () {
      clearInterval(this.timer)
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

  .picholder {
    position: relative;
  }

  .overlay {
    bottom: 0;
    left: 0;
    top: 100px;
    right: 0;
    margin: auto;
    position: absolute;
  }

</style>
