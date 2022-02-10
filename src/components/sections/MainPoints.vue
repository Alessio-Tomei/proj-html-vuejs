<template> 
    <section class="ms_main-points">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <div class="ms_container-small">
                        <h3 class="ms_emphasize">Let's Dream Big Together</h3>
                        <p class="ms_font-up">We are pioneers of the digital approach, using leading-edge technology to simplify procedures and apply executive coaching in the new age of digitalization</p>
                        <div class="ms_boxs-container">
                            <div class="ms_box" v-for="(box, index) in boxsList" :key="index">
                                <div class="ms_container-icons">
                                    <i :class="box.icon"></i>
                                </div>
                                <div class="ms_container-text">
                                    <h4>{{box.title}}</h4>
                                    <p class="ms_belittle">{{box.paragraph}}</p>
                                </div>
                            </div>
                        </div>
                        <div class="ms_buttons-container">
                            <button class="ms_light-button">Learn more</button>
                            <button>Get started today</button>
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
    name: 'MainPoints',
    data() {
        return {
            boxsList: mainPointsArray,
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_main-points {
    width: 100%;
    .ms_container {
        width: 90%;
        margin: 0 auto;
        .ms_container-small {
            width: $container-w-small;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            & > * {
                margin-bottom: 50px;
            }
            .ms_emphasize {
                color: $color-exalted;
                font-size: 1.5rem;
                font-weight: 400;
            }
            .ms_font-up {
                font-size: 2.5rem;
                font-weight: bold;
                text-align: center;
                padding: 0px 80px;
            }
            .ms_boxs-container {
                width: 100%;
                display: flex;
                flex-wrap: wrap;
                .ms_box {
                    width: calc(100% / 3);
                    padding: 20px;
                    display: flex;
                    .ms_container-icons {
                        width: 70px;
                        margin-right: 10px;
                        font-size: 30px;
                    }
                    .ms_container-text {
                        width: calc(100% - 80px);
                        .ms_belittle {
                            color: $color-belittle;
                            max-width: 400px;
                        }
                    }
                }
            }
            .ms_buttons-container {
                display: flex;
                & button:first-child {
                    margin-right: 30px;
                }
            }
        }
    }
}
</style>