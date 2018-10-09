<template>
  <v-content id="content">
    <div class="pic-holder">
      <img class="overlay" :src=gifurl>
      <img class="curtain" src="../assets/stage_curtain.png">
    </div>
    <div class="pic-holder">
      <button @click="startAutoReload()">
        <img class="button" src="../assets/play-button.png" alt="play">
      </button>
      <button @click="stopAutoReload()">
        <img class="button" src="../assets/pause-button.png" alt="pause">
      </button>
      <button @click="nextGif()">
        <img class="button" src="../assets/next-button.png" alt="next">
      </button>
    </div>
  </v-content>
</template>

<script>

  import CONFIG from '../config/config.json'
  import GphApiClient from 'giphy-js-sdk-core'
  import error_gif from '../assets/cat_error.gif'

  const giphy = GphApiClient(CONFIG.apikey)

  export default {
    name: 'Content',
    data () {
      return {
        gifurl: '',
        timer: ''
      }
    },
    methods: {
      fetchGif () {
        giphy.random('gifs', {tag: 'cat', rating: 'g', fmt: 'json'})
          .then((res) => {
            this.gifurl = res.data.images.original.gif_url
          })
          .catch((err) => {
            this.gifurl = error_gif
          })
      },
      startAutoReload () {
        this.timer = setInterval(this.fetchGif, 6000)
      },
      stopAutoReload () {
        clearInterval(this.timer)
      },
      nextGif () {
        this.stopAutoReload()
        this.fetchGif()
        this.startAutoReload()
      }
    },
    created () {
      if (this.gifurl === '') {
        this.fetchGif()
        this.startAutoReload()
      }
    },
    destroyed () {
      this.stopAutoReload()
    }
  }

</script>

<style scoped>

  button:focus {
    cursor: pointer;
    outline: none;
  }

  img.button {
    height: 60px;
  }

  .pic-holder {
    margin-top: 80px;
    margin-bottom: 30px;
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
    width: 320px;
  }

</style>
