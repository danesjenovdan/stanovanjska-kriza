<template>
  <div class="container">
    <div id="intro-overlay" :class="{hidden: shouldBeHidden}">
      <h1>{{ question.q }}</h1>
      <button
        class="intro-button"
        ref="theButton"
        @mouseenter="moveTheButton"
        @touchstart="moveTheButton"
      >{{ question.f }}</button>
      <button
        class="intro-button"
        @click="shouldBeHidden = true"
      >{{ question.a }}</button>
    </div>
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
    },
    data: () => {
      return {
        shouldBeHidden: false,
        questions: [
          {
            q: 'Se ti maje streha nad glavo?',
            a: 'Ja',
            f: 'Ne',
          },
          {
            q: 'Se vaši otroci lahko preselijo na svoje?',
            a: 'Ne',
            f: 'Ja',
          },
          {
            q: 'Si lahko privoščiš prvo stanovanje?',
            a: 'Ne',
            f: 'Ja',
          },
          {
            q: 'Tudi tvoja plača raste počasneje kot najemnina?',
            a: 'Ja',
            f: 'Ne',
          },
          {
            q: 'Še vedno čakaš na posteljo v študentskem domu?',
            a: 'Ja',
            f: 'Ne',
          },
        ],
      }
    },
    computed: {
      question() {
        return this.questions[Math.floor(Math.random() * this.questions.length)];
      },
    },
    methods: {
      moveTheButton() {
        const randX = 20 + Math.floor(Math.random() * (window.innerWidth/3));
        const randY = 20 + Math.floor(Math.random() * (window.innerHeight/3));
        this.$refs.theButton.style.top = `${randY}px`;
        this.$refs.theButton.style.left = `${randX}px`;
      },
    },
  }

</script>

<style lang="scss">

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

  #intro-overlay {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: #EFEFF0;
    color: #62667a;
    z-index: 100;

    padding: 40px;

    &.hidden {
      display: none;
    }

    h1 {
      font-size: 100px;
      @media (max-width: 762px) {
        font-size: 48px;
      }
    }

    .intro-button {
      border-radius: 0;
      border: 3px solid #62667a;
      background-color: #EFEFF0;
      color: #62667a;
      font-size: 48px;
      font-family: neue-haas-grotesk-display, sans-serif;
      position: relative;
      width: 200px;
      margin: 20px;
    }
  }

</style>
