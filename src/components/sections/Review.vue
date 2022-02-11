<template>
    <section class="ms_review">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <div class="ms_big-box">
                        <h3 class="ms_emphasize">People are praising Maxcoach</h3>
                        <p class="ms_font-up">What make they love us?</p>
                        <div class="ms_cards-container">
                            <div class="ms_card"  v-for="(cardIndex) in 3" :key="key(cardIndex - 1)">
                                <div class="ms_next-button-overlay" @click="next">
                                    <div class="ms_opacity"></div>
                                    <div class="ms_icon">
                                        <i class="fas fa-chevron-right"></i>
                                    </div>
                                </div>
                                <div class="ms_previous-button-overlay" @click="previous">
                                    <div class="ms_opacity"></div>
                                    <div class="ms_icon">
                                        <i class="fas fa-chevron-left"></i>
                                    </div>
                                </div>
                                <div class="ms_container-text">
                                    <h4 class="ms_sentence">{{cardsList[setIndex(cardIndex)].sentence}}</h4>
                                    <p class="ms_short-article">{{cardsList[setIndex(cardIndex)].article}}</p>
                                </div>
                                <div class="ms_reviewer-info">
                                    <div class="ms_container-img">
                                        <img :src="require(`../../assets/img/${cardsList[setIndex(cardIndex)].img}.jpg`)" alt="">
                                    </div>
                                    <div class="ms_info">
                                        <h5 class="ms_name">{{cardsList[setIndex(cardIndex)].name}}</h5>
                                        <p class="ms_profession">{{cardsList[setIndex(cardIndex)].profession}}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="ms_select-cards-container">
                            <div class="ms_dot" 
                            :class="{'ms_active' : multiplier == num - 1 }" 
                            @click="multiplier = num - 1 " v-for="num in 4" 
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
import {reviewArray} from '../../assets/data.js';

export default {
    name: 'Review',
    data() {
        return {
            cardsList: reviewArray,
            multiplier: 0,
        }
    },
    methods: {
        key: function(index) {
            return this.multiplier + index;
        },
        setIndex: function(number) {
            return (number + this.multiplier  - 1) % 4 
        },
        next: function() {
            if (this.multiplier < 3) {
                this.multiplier++;
            } else {
                this.multiplier = 0;
            }
        },
        previous: function() {
            if (this.multiplier > 0) {
                this.multiplier--;
            } else {
                this.multiplier = 3;
            }
        },
    },
    computed: {
    
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_review {
    width: 100%;
    background-color: #f8f8f8;
    .ms_container {
        width: $container-w-large;
        margin: 0 auto;
        .ms_big-box {
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
            .ms_cards-container {
                margin-top: 80px;
                width: 100%;
                display: flex;
                .ms_card {
                    border-radius: 10px;
                    width: calc(100% / 3);
                    padding: 20px;
                    display: flex;
                    flex-direction: column;
                    overflow: hidden;
                    position: relative;
                    top: 0;
                    left: 0;
                    .ms_next-button-overlay , 
                    .ms_previous-button-overlay {
                        .ms_opacity {
                            width: 100%;
                            height: 100%;
                            background-color: rgba($color: white, $alpha: .5);
                        }
                        .ms_icon {
                            position: absolute;
                            top: 50%;
                            left: 50%;
                            z-index: 2;
                            transform: translate(-50%, -50%);
                            font-size: 50px;
                            color: $theme-logo-color;
                            display: none;
                        }
                    }
                    &:hover  {
                        .ms_next-button-overlay, 
                        .ms_previous-button-overlay {
                            box-shadow: inset 0px 0px 12px 3px black;
                            .ms_icon {
                                display: block;
                            }
                        }
                    }
                    &:nth-child(1) {
                        transform: scale(.75);
                        .ms_previous-button-overlay {
                            position: absolute;
                            top: 0;
                            left: 0;
                            width: 100%;
                            height: 100%;
                            z-index: 1;
                            cursor: pointer;
                        }
                        .ms_next-button-overlay {
                            display: none;
                        } 
                    }
                    &:nth-child(2) {
                        border: 3px solid #eceeef;
                        .ms_previous-button-overlay,
                        .ms_next-button-overlay {
                            display: none;
                        } 
                    }
                    &:nth-child(3) {
                        transform: scale(.75);
                        .ms_next-button-overlay {
                            position: absolute;
                            top: 0;
                            left: 0;
                            width: 100%;
                            height: 100%;
                            z-index: 1;
                            cursor: pointer;
                        }
                        .ms_previous-button-overlay {
                            display: none;
                        } 
                    }
                    .ms_container-text {
                        width: calc(100% - 80px);
                        margin-bottom: 30px;
                        line-height: 2rem;
                        .ms_sentence {
                            font-size: 1.2rem;
                            font-weight: 600;
                            color: $theme-logo-color;
                            margin-bottom: 20px;
                        }
                        .ms_short-article {
                            font-weight: 500;
                            color: $color-belittle;
                            display: -webkit-box;
                            -webkit-line-clamp: 3;
                            -webkit-box-orient: vertical;
                            overflow: hidden;
                            text-overflow: ellipsis;
                        }

                    }
                    .ms_reviewer-info {
                        display: flex;
                        .ms_container-img {
                            width: 60px;
                            height: 60px;
                            border-radius: 50%;
                            overflow: hidden;
                            margin-right: 20px;
                            img {
                                width: 100%;
                            }
                        }
                        .ms_info {
                            .ms_name {
                                font-size: 1.2rem;
                                font-weight: 600;
                                color: $theme-logo-color;
                            }
                            .ms_profession {
                                font-size: 0.8rem;
                                color: $color-belittle;
                            }
                        }
                    }
                }
            }
            .ms_select-cards-container {
                margin-top: 30px;
                width: 100%;
                display: flex;
                justify-content: center;
                align-items: center;
                .ms_dot {
                    margin: 10px;
                    width: 10px;
                    height: 10px;
                    border-radius: 50%;
                    background-color: rgba($color: $theme-logo-color, $alpha: .5);
                    cursor: pointer;
                    &.ms_active {
                        width: 15px;
                        height: 15px;
                        background-color: $theme-logo-color;
                    }
                }
            }
        }
    }
}            
</style>