|<template>
  <main>
    <Jumbotron/>
    <MainPoints/>
  </main>
</template>

<script>
import Jumbotron from '../sections/Jumbotron.vue';
import MainPoints from '../sections/MainPoints.vue';
export default {
  name: 'Main',
  components: { 
    Jumbotron, 
    MainPoints,
  }
}
</script>

<style lang="scss" scoped>
main > * {
  margin-bottom: 100px;
}

</style>