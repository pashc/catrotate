<template>
  <v-content id="content">
    <div class="pic-holder">
      <img class="curtain" src="../assets/stage_curtain.jpg">
      <img class="overlay" :src=gifurl>
    </div>
    <div>
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
    width: 60%;
    -webkit-box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
    -moz-box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
    box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
  }

  .overlay {
    bottom: 0;
    left: 0;
    top: 15%;
    right: 0;
    border: solid 2px;
    margin: auto;
    position: absolute;
    width: 20%;
  }

</style>
