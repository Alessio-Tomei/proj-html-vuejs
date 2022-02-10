// Struttura base per progetti con bootstrap e fontawesom già installati

<template>
  <div id="app">
    <Header/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Footer from './components/macro/Footer.vue'
import Header from './components/macro/Header.vue'
import Main from './components/macro/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  }
}
</script>

<style lang="scss">
@import "./assets/style/globals.scss";

</style>
