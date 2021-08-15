<template>
  <div class="flex_container">
    <div class="container_navigation">
      <nav-bar />
    </div>
    <div class="container_body">
      <h1>{{ data.pages.home.heading }}</h1>
      <p>{{ data.pages.home.about}}</p>
    </div>
    <div class="container_footer">
      <footer />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '~/components/navigation/NavBar.vue';
import Footer from '~/components/footer/PageFooterComponent.vue'
import siteData from '~/resources/siteData.json';

export default Vue.extend({
  components: {
    NavBar,
    Footer
  },
  mounted(){ 
    // Not used for now
  },
  computed: {
    // Not used for now
  },
  data(){
    return{
      data: siteData
    }
  }
});
</script>

<style scoped>

.flex_container{ 
  border: 1px solid yellow;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1%;
  margin: 2%, 2%, 2%, 2%;
  width: 100%;
}

.container_navigation{
  border: 1px solid purple;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 5px;
  margin: 5px;
  width: 100%;
}

.container_body{
  border: 1px solid red;
  flex-direction: column;
  padding: 5px;
  margin: 5px;
  width: 100%;
}

.container_footer{
   border: 1px solid fuchsia;
  flex-direction: row;
  padding: 5px;
  margin: 5px;
  margin-top: auto;
  width: 100%;
}
</style>
