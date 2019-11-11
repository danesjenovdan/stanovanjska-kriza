<template>
  <div class="container">
    <Main></Main>
  </div>
</template>

<script>
  import Main from './components/Main.vue'
  import Vue from 'vue';
  import vuescroll from 'vuescroll';

  // You can set global config here.
  Vue.use(vuescroll, {
    ops: {
      // The global config
      vuescroll: {
        mode: 'native',
        sizeStrategy: 'percent',
        wheelDirectionReverse: true
      }
    }
  });

  export default {
    name: 'app',
    components: {
      Main
    }
  }

</script>

<style>

  body {
    margin: 0;
    overflow-y: hidden;
    background-color: #EFEFF0;
    font-family: neue-haas-grotesk-display, sans-serif;
  }

  #app {
    font-family: neue-haas-grotesk-display, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #000;
    letter-spacing: 1.1px;
  }

  .container {
    width: 100%;
    height:100vh;
    /*display: flex;*/
    /*padding-bottom: 5px;*/
  }

</style>
