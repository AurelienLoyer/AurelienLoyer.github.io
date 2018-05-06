<template>
  <div id="app">
    <v-header></v-header>
    <v-home></v-home>
    <v-about></v-about>
    <v-dates></v-dates>
    <v-footer></v-footer>
  </div>
</template>

<script>

  import Header from './components/Header.vue'
  import Home from './components/Home.vue'
  import About from './components/About.vue'
  import Dates from './components/Dates.vue'
  import Footer from './components/Footer.vue'

  export default {
    name: 'app',
    components: {
      'v-header': Header,
      'v-home': Home,
      'v-about': About,
      'v-dates': Dates,
      'v-footer': Footer
    }
  }
</script>

<style lang="scss">
  html {
    background: black;
  }

  html,
  body {
    margin: 0;
    padding: 0;
    height: 100%;
  }

  body {
    font-size: 100%;
    margin: 0;
    padding: 0;
    font-family: 'Open Sans', sans-serif;
    color: white;
    background-color: white;
    overflow-x: hidden;
    -webkit-transition: all 0.5s;
    -moz-transition: all 0.5s;
    -o-transition: all 0.5s;
    transition: all 0.5s;
  }

  body.menu-open {
    margin-left: -50%;
    overflow: hidden;
    width: 100%;
  }

  a,
  a:hover {
    text-decoration: none;
  }

  body h1,
  body h2,
  body h3 {
    padding: 0;
    margin: 0;
    display: inline-block;
    color: white;
  }

  p {
    margin: 0;
    padding: 0;
  }

  section {
    -webkit-transition: all 0.5s;
    -moz-transition: all 0.5s;
    -o-transition: all 0.5s;
    transition: all 0.5s;
  }

  .trans05 {
    -webkit-transition: all 0.5s;
    -moz-transition: all 0.5s;
    -o-transition: all 0.5s;
    transition: all 0.5s;
  }

  .trans02 {
    -webkit-transition: all 0.2s;
    -moz-transition: all 0.2s;
    -o-transition: all 0.2s;
    transition: all 0.2s;
  }

  .animate {
    opacity: 0;
    -webkit-transform: translateX(100px) translateY(50px);
    -moz-transform: translateX(100px) translateY(50px);
    transform: translateX(100px) translateY(50px);
  }
</style>
