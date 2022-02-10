|<template>
  <main>
    <Jumbotron/>
    <MainPoints/>
    <MainPointsSlider/>
  </main>
</template>

<script>
import Jumbotron from '../sections/Jumbotron.vue';
import MainPoints from '../sections/MainPoints.vue';
import MainPointsSlider from '../sections/MainPointsSlider.vue';
export default {
  name: 'Main',
  components: { 
    Jumbotron, 
    MainPoints,
    MainPointsSlider,
  }
}
</script>

<style lang="scss" scoped>
main > * {
  margin-bottom: 100px;
}

</style>