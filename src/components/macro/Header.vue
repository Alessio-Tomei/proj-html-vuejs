<template>
  <header>
    <div class="container-fluids">
      <div class="row row-cols-3 align-items-center">
        <div class="col">
          <div class="ms_logo-container">
            <div class="ms_logo">
              <img src="../../assets/img/dark-logo.png" alt="">
            </div>
          </div>
        </div>
        <div class="col">
          <NavBar/>
        </div>
        <div class="col">
          <div class="ms_lang-selector-searchbar-container">
            <div class="ms_lang-container">
              <LangSelector/>
            </div>
            <div class="ms_user">
              <i class="far fa-user-circle"></i>
            </div>
            <div class="ms_search-bar">
              <div>
                <SearchBar @searchUp="doStuff"/>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

  </header>
</template>

<script>
import LangSelector from '../commons/LangSelector.vue';
import NavBar from '../commons/NavBar.vue';
import SearchBar from '../commons/SearchBar.vue';
export default {
    name: 'Header',
    components: { 
      NavBar,
      LangSelector,
      SearchBar,
    },
    methods: {
      doStuff(textUp) {
        console.log(textUp);
      }
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/variables.scss';

.ms_logo-container {
  padding-left: 200px;
  .ms_logo {
    width: 100%;
    img {
      cursor: pointer;
      width: 50%;
    }
  }
}

.ms_lang-selector-searchbar-container {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding-right: 20px;
  .ms_lang-container {
    margin-right: 10px;
  }
  .ms_user {
    margin-right: 10px;
    cursor: pointer;
  }
  .ms_search-bar {
    height: 80px;
    width: 150px;
    border-left: 1px solid $bg-color-jumbotron;
    display: flex;
    align-items: center;
  }
}

</style>