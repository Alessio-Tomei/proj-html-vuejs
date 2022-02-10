|<template>
  <main>
    <Jumbotron/>
    <MainPoints/>
    <MainPointsSlider/>
    <TariffPlans/>
  </main>
</template>

<script>
import Jumbotron from '../sections/Jumbotron.vue';
import MainPoints from '../sections/MainPoints.vue';
import MainPointsSlider from '../sections/MainPointsSlider.vue';
import TariffPlans from '../sections/TariffPlans.vue';
export default {
  name: 'Main',
  components: { 
    Jumbotron, 
    MainPoints,
    MainPointsSlider,
    TariffPlans,
  }
}
</script>

<style lang="scss" scoped>
main > * {
  margin-bottom: 100px;
}

</style>