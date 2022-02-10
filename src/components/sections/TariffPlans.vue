<template>
    <section class="ms_main-point-slider">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <h3 class="ms_emphasize">Let's Dream Big Together</h3>
                    <p class="ms_font-up">Explore How can i help you</p>
                    <div class="ms_cards-container">
                        <div class="ms_card" v-for="(card, index) in filterCardList" :key="index">
                            <div class="ms_container-img">
                                <div class="ms_filter"></div>
                                <img :src="require(`../../assets/img/${card.img}.jpg`)" alt="">
                            </div>
                            <div class="ms_container-text">
                                <p class="ms_price">{{card.price}}</p>
                                <p class="ms_title">{{card.title}}</p>
                                <div class="ms_show-hover">
                                    <div class="ms_container-icons">
                                        <div class="ms_icon-box">
                                            <div>
                                                <i class="far fa-file-alt"></i>
                                            </div>
                                            <p>20 Lessons</p>
                                        </div>
                                        <div class="ms_icon-box">
                                            <div>
                                                <i class="far fa-user"></i>
                                            </div>
                                            <p>50 Studends</p>
                                        </div>
                                    </div>
                                    <p class="ms_description">{{card.description}}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="ms_link-container">
                        <p>Take the control of their life back and start doing things to make theri dream come true. <a href="#" @click.prevent="showMore = !showMore">{{setText}} &rarr;</a></p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import {plansArray} from '../../assets/data.js';

export default {
    name: 'TarriffPlans',
    data() {
        return {
            cardsList: plansArray,
            showMore: false,
        }
    },
    methods: {
    },
    computed: {
        filterCardList() {
            let filterArray = this.cardsList.slice(0, 4);
            if (this.showMore == true) {
                filterArray = this.cardsList;
            }
            return filterArray;
        },
        setText() {
            let text = 'View all courses'
            if (this.showMore == true) {
                text = 'Hide'
            }
            return text;
        }
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
        text-align: center;
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
            flex-wrap: wrap;
            margin-bottom: 30px;
            .ms_card {
                padding: 20px;
                border-radius: 10px;
                width: calc(100% / 4);
                position: relative;
                top: 0;
                left: 0;
                cursor: pointer;
                .ms_container-img {
                    width: 100%;
                    border-radius: 10px;
                    overflow: hidden;
                    position: relative;
                    top: 0;
                    left: 0;
                    .ms_filter {
                        position: absolute;
                        top: 0;
                        left: 0;
                        width: 100%;
                        height: 100%;
                        box-shadow: inset 0px -80px 100px 20px black;
                    }    
                    img {
                        width: 100%;
                    }
                }
                .ms_container-text {
                    width: 100%;
                    position: absolute;
                    bottom: 0;
                    left: 0;
                    z-index: 2;
                    text-align: left;
                    padding: 30px;
                    color: white;
                    display: flex;
                    flex-direction: column;
                    .ms_price {
                        color: $color-exalted;
                        font-size: 1.5rem;
                        font-weight: bold;
                    }
                    .ms_title {
                        font-size: 1.5rem;
                        font-weight: bold;
                    }
                    .ms_show-hover {
                        display: none;
                        .ms_container-icons {
                            display: flex;
                            .ms_icon-box {
                                display: flex;
                                div {
                                    margin-right: 6px;
                                }
                            }
                            & .ms_icon-box:first-child {
                                margin-right: 20px;
                            }
                        }
                        .ms_description {
                            display: -webkit-box;
                            -webkit-line-clamp: 3;
                            -webkit-box-orient: vertical;
                            overflow: hidden;
                            text-overflow: ellipsis;
                        }
                    }
                }
                &:hover .ms_container-text .ms_show-hover {
                    display:block;
                    
                }
                &:hover .ms_container-img .ms_filter {
                    background-color: rgba($color: black, $alpha: .5);   
                } 
            }
        }
        .ms_link-container {
            width: 30%;
            margin: 0 auto;
            p {
                color: $color-belittle;
                font-weight: 500;
                font-size: 1.2rem;
                a {
                    color: $color-main;
                    border-bottom:1px solid $color-belittle;
                    padding-bottom: 2px;
                }
            }
        }
    }
}            
</style>