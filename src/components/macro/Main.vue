|<template>
  <main>
    <Jumbotron/>
    <MainPoints/>
    <MainPointsSlider/>
    <TariffPlans/>
    <QuestionsAndAnswers/>
  </main>
</template>

<script>
import Jumbotron from '../sections/Jumbotron.vue';
import MainPoints from '../sections/MainPoints.vue';
import MainPointsSlider from '../sections/MainPointsSlider.vue';
import QuestionsAndAnswers from '../sections/QuestionsAndAnswers.vue';
import TariffPlans from '../sections/TariffPlans.vue';
export default {
  name: 'Main',
  components: { 
    Jumbotron, 
    MainPoints,
    MainPointsSlider,
    TariffPlans,
    QuestionsAndAnswers,
  }
}
</script>

<style lang="scss" scoped>
main > * {
  margin-bottom: 100px;
}

</style>