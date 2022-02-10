<template> 
    <section class="ms_upcoming-event">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <div class="ms_container-small">
                        <h3 class="ms_emphasize">Wonna transform your life?</h3>
                        <p class="ms_font-up">Upcoming Events</p>
                        <div class="ms_boxs-container">
                            <div class="ms_box" v-for="(box, index) in boxsList" :key="index">
                                <div class="ms_container-text">
                                    <div class="ms_container-address">
                                        <div class="ms_icon">
                                            <i class="fas fa-map-marker-alt"></i>
                                        </div>
                                        <p>Texas, US</p>
                                    </div>
                                    <p class="ms_event-title">StoryTelling Workshop</p>
                                </div>
                                <div class="ms_calendar">
                                    <span class="ms_day">22</span>
                                    <span class="ms_month">NOV</span>
                                    <button>Get ticket</button>
                                </div>
                            </div>
                        </div>
                        <div class="ms_link-container">
                            <p>Excited about our event? <a href="#">View all events &rarr;</a></p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import {mainPointsArray} from '../../assets/data.js';

export default {
    name: 'UpcomingEvent',
    data() {
        return {
            boxsList: mainPointsArray,
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_upcoming-event {
    width: 100%;
    .ms_container {
        width: $container-w-large;
        margin: 0 auto;
        .ms_container-small {
            width: $container-w-small;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            .ms_emphasize {
                color: $color-exalted;
                font-size: 1.5rem;
                font-weight: 400;
            }
            .ms_font-up {
                font-size: 3rem;
                font-weight: bold;
                text-align: center;
                padding: 0px 80px;
            }
            .ms_boxs-container {
                margin-top: 50px;
                width: 100%;
                display: flex;
                flex-wrap: wrap;
                .ms_box {
                    width: calc(100% / 2);
                    display: flex;
                    border-radius: 10px;
                    .ms_container-text {
                        width: calc(100% - 200px);
                        padding: 25px;

                        .ms_container-address {

                            display: flex;
                            color: $color-belittle;
                            .ms_icon {
                                margin-right: 10px;
                            }
                            p {
                                margin: 0;
                            }
                        }
                        .ms_event-title {
                            font-size: 1.2rem;
                            font-weight: 600;
                        }
                    }    
                    .ms_calendar {
                        font-weight: 500;
                        width: 200px;
                        padding: 25px;
                        display: flex;
                        flex-direction: column;
                        align-items: center;
                        .ms_day{
                            font-size: 2.5rem;
                            line-height: 2.5rem;

                        }
                        .ms_month {

                        }
                        button {
                            padding: 5px 30px;
                        }
                    }
                    &:hover {
                        box-shadow: 3px 0px 12px 3px #eceeef;
                        border-left: 1px solid $color-exalted;
                    }   
                }
            }
            .ms_link-container {
                margin-top: 50px;
                font-size: 1.5rem;
                p {
                    color: $color-belittle;
                    a { 
                        color: $color-exalted;
                        padding-bottom: 2px;
                        border-bottom:1px solid $color-belittle; 
                    }
                }
            }
        }
    }
}
</style>