<template>
  <div id="app">
    <app-main></app-main>
  </div>
</template>

<script>
    import main from './components/main'
export default {
  name: 'app',
    components: {
      'AppMain': main
    },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">
    @import url('https://fonts.googleapis.com/css?family=Open+Sans:300,300i,400,400i,600,600i,700,700i,800,800i');
    body{
        margin:0;
    }
    #app {
      width: 100vw;
        height: 100vh;
        margin:0;
        padding: 0;
        font-family: 'Open Sans', sans-serif;
        overflow: hidden;
    }
    .row, .col {
        padding: 0;
        margin:0;
    }
</style>
