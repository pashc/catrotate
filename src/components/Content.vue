<template>
  <div id="content">
    <h1>{{ title }}</h1>
    <div class="picholder">
      <img class="overlay" :src=gifurl>
      <img class="curtain" src="../assets/stage_curtain.png">
    </div>
  </div>
</template>

<script>

  import CONFIG from '../config/config.json'
  import giphy_api from 'giphy-api'

  const giphy = giphy_api(CONFIG.apikey)

  export default {
    name: 'Content',
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
            this.gifurl = require('../assets/error_page.png')
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

  .picholder {
    position: relative;
  }

  .curtain {
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
