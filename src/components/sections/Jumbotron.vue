<template>
  <section class="ms_jumbotron">
        <div class="ms_container">
            <div class="row">
                <div class="col">
                    <div class="ms_backgroung">
                        <div class="ms_container-small">
                            <div class="ms_text-container">
                                <p class="ms_emphasize">New Challenges, New Skills</p>
                                <p class="ms_font-up">Build your own life coaching business</p>
                                <p class="ms_belittle">Whole-Life Business Coaching for committed entrepreneurs</p>
                                <button>Get started today</button>
                            </div>
                            <div class="ms_container-img">
                                <img src="../../assets/img/home-business-hero-avatar.png" alt="">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="ms_mini-buttons">
            <div>
                <i class="fa-solid fa-ruler"></i>
            </div>
            <div>
                <i class="fa-regular fa-life-ring"></i>
            </div>
            <div>
                <i class="fa-solid fa-book"></i>
            </div>
            <div>
                <i class="fa-solid fa-cart-shopping"></i>
            </div>
        </div>
  </section>
</template>

<script>
export default {
    name:'Jumbotron',
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

$padding-jumbotron: 80px;

.ms_jumbotron {
    background-color: $bg-color-jumbotron;
    padding-bottom: $padding-jumbotron;
    position: relative;
    top: 0;
    left: 0;
    z-index: 0;
    .ms_mini-buttons {
        position: absolute;
        top: 200px;
        right: 0;
        background-color: white;
        border-radius: 5px;
        & > div {
            padding: 10px;
            cursor: pointer;
            &:hover {
                &:hover {
                    box-shadow: inset 0px 0px 5px 5px rgba($color: $theme-logo-color, $alpha: .25);
                    background-color: rgba($color: $theme-logo-color, $alpha: .5);
                    color: white;
                }
            }
        }
    }
    .ms_container{
        width: $container-w-large;
        margin: 0 auto;
    }
    .ms_backgroung {
        height: 750px;
        position: relative;
        top: 0;
        left: 0;
        background-image: url("../../assets/img/home-business-hero-global-image.png");
        background-repeat: no-repeat;
        background-position: right;
        background-size: contain;
    }
}

.ms_container-small {
    position: relative;
    top: 80px;
    width: $container-w-small;
    margin: 0 auto;
    height: 750px;
    display: flex;
    .ms_container-img {
        width: 40%;
        img {
            height: 100%;
        }
    }
    .ms_text-container {
        width: 60%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        p {
            max-width: 500px;
            line-height: initial;
        }
        .ms_emphasize {
            color: $color-exalted;
            font-size: 1.5rem;
            font-weight: 500;

        }
        .ms_font-up {
            font-size: 4rem;
            font-weight: bold;
        }
        .ms_belittle {
            color: $color-belittle;
            max-width: 400px;
            font-weight: 500;
        }
    }
}

</style>