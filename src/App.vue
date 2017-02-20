<template>
  <div id="app">
    <v-header></v-header>
    <v-home></v-home>
    <v-about></v-about>
    <v-works></v-works>
    <v-maps></v-maps>
    <v-contact></v-contact>
    <v-footer></v-footer>
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Works from './components/Works.vue'
import Maps from './components/Maps.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    'v-header': Header,
    'v-home': Home,
    'v-about': About,
    'v-works': Works,
    'v-maps': Maps,
    'v-contact': Contact,
    'v-footer': Footer
  }
}
</script>

<style lang="scss">



</style>
