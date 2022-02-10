<template>
<div class="cs_search-bar">
    <input type="text" 
    v-model="inputSearch" 
    @keyup.enter="$emit('searchUp', inputSearch); reset()"
    @keyup="activate"
    placeholder="Search..."
    >
    <div class="cs_button" @click="$emit('searchUp', inputSearch); reset(); activate()" v-if="active">
        <i class="fas fa-search"></i>
    </div>
</div>
</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return {
            inputSearch: '',
            active: false,
        }
    },
    methods: {
        reset: function() {
            this.inputSearch = '';
        },
        activate: function() {
            if (this.inputSearch != '') {
                this.active = true;
            }else {
                this.active = false;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.cs_search-bar {
    display: flex;
    input {
        width: calc(100% - 36px);
        padding: 0px 20px;
        border-radius: 5px;
        border: none;
        outline: none;
    }
    .cs_button {
        cursor: pointer;
        padding: 5px;
        border-radius: 5px;
        margin-left: 10px;
    }
}
</style>