<template>
  <div class="flex_container">

    <div class="container_navigation">
      <nav-bar />
    </div>
    <div class="container_body">
      <h1>Levenshtein Distance Calculator Page</h1>
      <p>Under Construction...</p>
    </div>
    <div class="container_footer">
      <pagefooter />
    </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '~/components/navigation/NavBar.vue';
import Pagefooter from '~/components/footer/Pagefooter.vue';

export default Vue.extend({
  components: {
    NavBar,
    Pagefooter
  },
  data(){
    return{  }
  },
  methods: {  }
});
</script>

<style scoped>
.flex_container{ 
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1px;
  margin: 1px;
  width: 100%;
}

.container_navigation{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 1px;
  margin: 1px;
  width: 100%;
}

.container_body{
  flex-direction: column;
  padding: 2%;
  margin: auto;
  width: 100%;
}

.container_footer{
  flex-direction: row;
  padding: 1px;
  margin: 1px;
  width: 100%;
}
</style>