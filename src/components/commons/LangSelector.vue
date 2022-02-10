<template>
    <div class="cs_lang-selector">
        <div class="cs_click-outside" v-if="selectOpen" @click="selectOpen = false"></div>
        <div class="cs_select">
            <div class="cs_flag-container">
                <img :src="require(`../../assets/img/${options[currentLang].img}.png`)" alt="">
            </div>
            <div class="cs_text-container" @click.prevent="selectOpen = !selectOpen">
                <span>
                    {{options[currentLang].lang}}
                </span>
                <div class="cs_chevron" :class="{'rotate' : selectOpen}">
                    <i class="fa-solid fa-chevron-down"></i>
                </div>
            </div>
            <ul class="cs_dropdown-menu" v-if="selectOpen">
                <li 
                v-for="(element, index) in options" 
                :key="index"
                @click="setCurrentLang(index)"
                :class="{'hover' : index == currentLang}"
                >
                    {{element.lang}}
                </li>
            </ul>
        </div>

    </div>
</template>

<script>
import {langOptions} from '../../assets/data.js';

export default {
    name: 'LangSelector',
    data() {
        return {
            options: langOptions,
            currentLang: 0,
            selectOpen: false,
        }
    },
    methods: {
        setCurrentLang: function (index) {
            this.currentLang = index;
            this.selectOpen= false;
        }
    },
    computed: {
        setFlag() {
            return this.options[this.currentLang].img;
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.cs_lang-selector {
    display: flex;
    width: 150px;
    max-width: 150px;
    .cs_click-outside {
        z-index: 1;
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
    }

    .cs_select {
        width: 100%;
        display: flex;
        position: relative;
        align-items: center;
        top: 0;
        left: 0;
        .cs_flag-container img {
            width: 32px;
            margin-right: 10px;
        }
        .cs_text-container {
            display: flex;
            width: calc(100% - 42px);
            cursor: pointer;
            span {
                text-transform: uppercase;
                font-weight: 500;
                text-overflow: ellipsis;
                overflow: hidden;
                white-space: nowrap;
                width: calc(100% - 17px);
            }
            .cs_chevron{
                margin-left: 5px;
                font-size: 12px;
                &.rotate {
                    transform: rotate(180deg);
                }
            }
        }
        .cs_dropdown-menu {
            z-index: 1;
            position: absolute;
            top: 30px;
            left: 50%;
            overflow: hidden;
            border: 1px solid $theme-logo-color;
            border-radius: 10px;
            background-color: white;
            min-width: 100px;
            width: max-content;
            max-width: 200px;
            display: flex;
            flex-direction: column;
            li {
                cursor: pointer;
                width: 100%;
                text-align: center;
                color: $theme-logo-color;
                display: block;
                width: 100%;
                padding: 5px 10px;
                &:hover {
                    box-shadow: inset 0px 0px 5px 5px rgba($color: $theme-logo-color, $alpha: .25);
                    background-color: rgba($color: $theme-logo-color, $alpha: .5);
                    color: white;
                }
                &.hover {
                    box-shadow: inset 0px 0px 5px 5px rgba($color: $theme-logo-color, $alpha: .25);
                    background-color: rgba($color: $theme-logo-color, $alpha: .5);
                    color: white;
                }
            }
        }
    }
}



</style>