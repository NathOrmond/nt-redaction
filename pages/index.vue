<template>
  <div class="container">
    <nav-bar />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '@/components/navigation/NavBar.vue';

export default Vue.extend({
  components: {
    NavBar,
  },
  data(){
    return{
      logoTitle: '',
      logoSubTitle: '',
      navElements: []
    }
  }
});
</script>

<style lang="scss">
.container{
  // TODO
}
</style>
