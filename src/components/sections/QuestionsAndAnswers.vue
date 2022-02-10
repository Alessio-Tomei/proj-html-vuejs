<template>
    <section class="ms_q-and-a ">
        <div class="ms_backgroung">
            <img src="../../assets/img/maxcoach-shape-07.png" alt="">
            <div class="ms_container">
                <div class="row">
                    <div class="col">
                        <div class="ms_video-container">
                            <img class="ms_video" src="../../assets/img/home-business-video-poster-670x450.jpg" alt="">
                            <img class="ms_play" src="../../assets/img/icon-youtube-play.png" alt="">
                        </div>
                    </div>
                    <div class="col">
                        <div class="ms_text-box">
                            <h2>To Thrive In Business Today, You'll Need a Good Plan</h2>
                            <div class="ms_q-a-container">
                                <div class="ms_q-a-row" @click="setActive(1)" :class="{'ms_active' : active == 1}">
                                    <div class="ms_icon">
                                        <i class="fas fa-chevron-circle-down"></i>
                                    </div>
                                    <div class="ms_container-text">
                                        <p class="ms_question">How can we help?</p>
                                        <p class="ms_answer">Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci natus enim et dolor doloribus velit, numquam iure reprehenderit quod cum delectus exercitationem, eveniet sunt consequatur quaerat nam ut ipsam repudiandae!</p>
                                    </div>
                                </div>
                               <div class="ms_q-a-row" @click="setActive(2)" :class="{'ms_active' : active == 2}">
                                    <div class="ms_icon">
                                        <i class="fas fa-chevron-circle-down"></i>
                                    </div>
                                    <div class="ms_container-text">
                                        <p class="ms_question">How can we help?</p>
                                        <p class="ms_answer">Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci natus enim et dolor doloribus velit, numquam iure reprehenderit quod cum delectus exercitationem, eveniet sunt consequatur quaerat nam ut ipsam repudiandae!</p>
                                    </div>
                                </div>
                                <div class="ms_q-a-row" @click="setActive(3)" :class="{'ms_active' : active == 3}">
                                    <div class="ms_icon">
                                        <i class="fas fa-chevron-circle-down"></i>
                                    </div>
                                    <div class="ms_container-text">
                                        <p class="ms_question">How can we help?</p>
                                        <p class="ms_answer">Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci natus enim et dolor doloribus velit, numquam iure reprehenderit quod cum delectus exercitationem, eveniet sunt consequatur quaerat nam ut ipsam repudiandae!</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: 'QuestionsAndAnswers',
    data() {
        return {
            active: 1,
        }
    },
    methods: {
        setActive: function(num) {
            this.active = num;
            console.log(this.active);
        }
    },
    computed: {
        
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_q-and-a {
    width: 100%;
    background-color: #323043;
    .ms_backgroung {
        width: 100%;
        position: relative;
        top: 0;
        left: 0;
        padding: 100px 0px; 
        background-image: url("../../assets/img/background-map-dots-top-right-transparent.png");
        background-repeat: no-repeat;
        background-position-x: right;
        background-position-y: top;
        & > img {
            position: absolute;
            bottom: 20px;
            left: 100px;
            z-index: 0;
        }
        .ms_container {
            width: $container-w-large;
            height: 100%;
            margin: 0 auto;
            .row {
                height: 100%;
                padding: 0px 100px;
                align-items: center;
            }
        }    
        .ms_video-container {
            width: 600px;
            position: relative;
            top: 0;
            left: 0;
            border-radius: 10px;
            overflow: hidden;
            .ms_video {
                width: 100%;
                position: relative;
                top: 0;
                left: 0;
            }
            .ms_play {
                cursor: pointer;
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50% , -50%);
            }
        }
        .ms_text-box {
            color: white;
            width: 500px;
            & > h2 {
                font-size: 3rem;
            }
            .ms_q-a-row {
                display: flex;
                cursor: pointer;
                border-bottom: 1px solid gray;
                padding: 20px;
                .ms_icon {
                    height: 36px;
                    margin-right: 20px;
                    color: white;
                    vertical-align: middle;
                    line-height: 36px;
                }
                .ms_container-text {
                    .ms_question {
                        color: white;
                        font-size: 1.5rem;
                        margin: 0;
                    }
                    .ms_answer {
                        display: none;
                        margin: 0;
                    }
                }
                &.ms_active {
                    .ms_icon {
                    color: $color-exalted;
                    transform: rotate(180deg);
                    }
                    .ms_container-text {
                        .ms_question {
                            color: $color-exalted;
                        }
                        .ms_answer {
                            display: block;
                        }
                    }
                }
            }
            
        }
    }
}            
</style>