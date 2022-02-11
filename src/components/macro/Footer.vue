<template>
  <footer>
    <div class="ms_up" @click="setScroll">
      <i class="fas fa-chevron-circle-up"></i>
    </div>
  </footer>
</template>

<script>
export default {
    name: 'Footer',
    methods: {
      setScroll: function() {
        window.scroll(0, 0)
      }
    }
}
</script>

<style lang="scss" scoped>

footer {
  display: flex;
  justify-content: center;
  .ms_up {
    font-size: 60px;
    color: #20ad96;
    cursor: pointer;
  }  
}

</style>