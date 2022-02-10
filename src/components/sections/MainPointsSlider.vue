<template>
    <section class="ms_main-point-slider">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <div class="ms_container-small">
                        <h3 class="ms_emphasize">Let's Dream Big Together</h3>
                        <p class="ms_font-up">Explore How can i help you</p>
                        <div class="ms_cards-container">
                            <div class="ms_card" v-for="(cardIndex) in 3" :key="key(cardIndex - 1)">
                                <div class="ms_container-img">
                                    <img :src="require(`../../assets/img/${cardsList[setIndex(cardIndex)].img}.jpg`)" alt="">
                                </div>
                                <div class="ms_container-text">
                                    <h4>{{cardsList[setIndex(cardIndex)].title}}</h4>
                                    <p class="ms_belittle">{{cardsList[setIndex(cardIndex)].paragraph}}</p>
                                </div>
                                <div class="ms_button-container">
                                    <button class="ms_light-button">Discover Now &rarr;</button>
                                </div>
                            </div>
                        </div>
                        <div class="ms_select-cards-container">
                            <div class="ms_dot" 
                            :class="{'ms_active' : gruop == num - 1 }" 
                            @click="gruop = num - 1 " v-for="num in 3" 
                            :key="num - 1"
                            >
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import {mainSliderArray} from '../../assets/data.js';

export default {
    name: 'MainPointSlider',
    data() {
        return {
            cardsList: mainSliderArray,
            gruop: 0,
        }
    },
    methods: {
        key: function(index) {
            return this.gruop + index;
        },
        setIndex: function(number) {
            return number + this.gruop * 3 - 1 
        },
    },
    computed: {
    
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_main-point-slider {
    width: 100%;
    background-color: #f8f8f8;
    .ms_container {
        width: $container-w-large;
        margin: 0 auto;
        .ms_container-small {
            width: $container-w-small;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            & > * {
                margin-bottom: 30px;
            }
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
            .ms_cards-container {
                width: 100%;
                display: flex;
                .ms_card {
                    box-shadow: 0px 18px 15px 20px #eceeef;
                    margin: 20px;
                    border-radius: 10px;
                    width: calc(100% / 3);
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    overflow: hidden;
                    .ms_container-img {
                        width: 100%;
                        margin-bottom: 30px;
                        img {
                            width: 100%;
                        }
                    }
                    .ms_container-text {
                        width: calc(100% - 80px);
                        text-align: center;
                        margin-bottom: 30px;
                        .ms_belittle {
                            color: $color-belittle;
                            max-width: 400px;
                            overflow: scroll;
                            &::-webkit-scrollbar {
                                display: none;
                            }
                        }
                    }
                    .ms_button-container {
                        width: 100%;
                        button {
                            width: 100%;
                            border: none;
                            border-top: 1px solid #eceeef;
                            &:hover {
                                color: white;
                                background-color: $color-exalted;
                            }
                        }
                    }
                }
            }
            .ms_select-cards-container {
                width: 100%;
                display: flex;
                justify-content: center;
                align-items: center;
                .ms_dot {
                    margin: 10px;
                    width: 10px;
                    height: 10px;
                    border-radius: 50%;
                    background-color: #bcbcbc;
                    cursor: pointer;
                    &.ms_active {
                        width: 15px;
                        height: 15px;
                        background-color: $color-main;
                    }
                }
            }
        }
    }
}            
</style>