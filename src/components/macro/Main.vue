|<template>
  <main>
    <Jumbotron/>
    <MainPoints/>
    <MainPointsSlider/>
    <TariffPlans/>
    <QuestionsAndAnswers/>
    <UpcomingEvent/>
    <Review/>
  </main>
</template>

<script>
import Jumbotron from '../sections/Jumbotron.vue';
import MainPoints from '../sections/MainPoints.vue';
import MainPointsSlider from '../sections/MainPointsSlider.vue';
import QuestionsAndAnswers from '../sections/QuestionsAndAnswers.vue';
import Review from '../sections/Review.vue';
import TariffPlans from '../sections/TariffPlans.vue';
import UpcomingEvent from '../sections/UpcomingEvent.vue';

export default {
  name: 'Main',
  components: { 
    Jumbotron, 
    MainPoints,
    MainPointsSlider,
    TariffPlans,
    QuestionsAndAnswers,
    UpcomingEvent,
    Review,
  }
}
</script>

<style lang="scss" scoped>
main > * {
  margin-bottom: 100px;
}

</style>