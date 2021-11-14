<template>
  <div class="flex_container">
    
    <div class="container_navigation">
      <nav-bar />
    </div>
    
    <div 
    class="container_body">
      <h1>{{ data.pages.home.heading }}</h1>
      <p>{{ data.pages.home.about}}</p>
    </div>

    <div class="container_footer">
      <pagefooter />
    </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '~/components/navigation/NavBar.vue';
import siteData from '~/resources/siteData.json';
import Pagefooter from '~/components/footer/Pagefooter.vue';

export default Vue.extend({
  layout: 'default',
  components: {
    NavBar,
    Pagefooter
  },
  mounted(){   },
  computed: {  },
  data(){
    return{
      data: siteData
    }
  }
});
</script>

<style scoped>
.flex_container{ 
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center stretch;
  align-content: stretch;
  padding: 0px;
  margin: 0px;
  width: 100%;
  height: 100%;
}

.container_navigation{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 0px;
  margin: 0px;
  width: 100%;
}

.container_body{
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 2%;
  margin: auto;
  width: 100%;
}

.container_footer{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 1px;
  margin: 1px;
  width: 100%;
}
</style>
