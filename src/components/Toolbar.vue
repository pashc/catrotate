<template>
  <v-toolbar
    light
    app
    fixed
    class="nav">

    <v-spacer></v-spacer>
    <v-toolbar-title class="font" v-text="state.title"/>
    <v-spacer></v-spacer>

  </v-toolbar>
</template>

<script>

  export default {
    name: 'ToolBar',
    data () {
      return {
        state: {
          title: 'Cat Roulette'
        },
        index_lnk: 'http://blog.paulwerner.org',
        mail_lnk: 'mailto:paulwerner@protonmail.com',
        github_lnk: 'https://github.com/pashc',
        xing_lnk: 'https://www.xing.com/profile/Paul_Werner23',
        linkedin_lnk: 'https://de.linkedin.com/in/paul-werner'
      }
    }
  }

</script>

<style scoped>

  img {
    height: 60px;
    margin: 10px;
    float: left;
  }

  .font {
    font-weight: bold;
    font-size: 30px;
  }

  .nav {
    margin-bottom: 20px;
  }

</style>
