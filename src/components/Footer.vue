<template>
  <v-footer class="footer">

    <div class="left">
      &copy; 2018 by Paul Werner
    </div>

    <div class="right">

      <a href="https://www.giphy.com">
        <img src="../assets/giphy_powered_by.png">
      </a>
    </div>

  </v-footer>
</template>

<script>
  export default {
    name: 'Footer',
    data () {
      return {
        state: {
          fixed: false,
          dialog: {
            disclaimer: false,
            privacy: false,
            legal: false
          }
        }
      }
    }
  }
</script>

<style scoped>

  .footer {
    color: #404040;
    padding: 5px;
    position: absolute;
    width: 100%;
    bottom: 0;
  }

  .left {
    display: block;
    float: left;
    padding-left: 15px;
  }

  .right {
    display: block;
    padding-right: 15px;
    float: right;
  }

</style>
