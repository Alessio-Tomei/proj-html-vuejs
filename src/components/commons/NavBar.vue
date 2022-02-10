<template>
    <div class="cs_navbar">
        <nav>
            <ul>
                <li class="cs_click-outside" v-if="currentMenuOpen != null" @click="currentMenuOpen = null"></li>
                <li 
                v-for="(item, index) in navItems" 
                :key="index">
                    <a href="#" @click.prevent="openDropDown(index)">
                        {{item.name}}
                        <div class="cs_chevron-container" v-if="item.dropDownItems.length > 0">
                            <div class="cs_chevron" :class="{'rotate' : currentMenuOpen == index}">
                                <i class="fa-solid fa-chevron-down"></i>
                            </div>
                        </div>
                    </a>
                    <ul class="cs_dropdown-menu" v-if="item.dropDownItems.length > 0 && currentMenuOpen == index">
                        <li v-for="(dDitem, index) in item.dropDownItems" :key="index">
                            <a href="">{{dDitem}}</a>
                        </li>
                    </ul>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
import {navigationItems} from '../../assets/data.js';

export default {
    name: 'NavBar',
    data() {
        return {
            navItems: navigationItems,
            currentMenuOpen: null,
        };
    },
    methods: {
        openDropDown: function (index) {
            if(this.currentMenuOpen != index) {
                this.currentMenuOpen = index;
            } else {
                this.currentMenuOpen = null;
            }
        },
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.cs_navbar {
    width: 100%;
    nav {
        & > ul {
            li.cs_click-outside {
                z-index: 1;
                position: fixed;
                top: 0;
                left: 0;
                width: 100vw;
                height: 100vh;
            }
            display: flex;
            align-content: center;
            & > li {
                position: relative;
                top: 0;
                left: 0;
                width: calc(100% / 6);
                & > a {
                    font-weight: 500;
                    color: $theme-logo-color;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    .cs_chevron-container {
                        margin-left: 10px;
                        font-size: 0.5rem;
                    }     
                    .cs_chevron.rotate {
                        transform: rotate(180deg);
                    }
                    &:hover {
                        text-decoration: underline;
                    }
                }
                .cs_dropdown-menu {
                    z-index: 1;
                    overflow: hidden;
                    border: 1px solid $theme-logo-color;
                    border-radius: 10px;
                    background-color: white;
                    min-width: 100px;
                    width: max-content;
                    max-width: 200px;
                    position: absolute;
                    top: 30px;
                    left: 30%;
                    display: flex;
                    flex-direction: column;
                    li {
                        width: 100%;
                        a {
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
                        }
                    }
                }
            }
        }
    }    
}

</style>