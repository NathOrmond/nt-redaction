<template>
  <div class="nav_container">
    <nuxt-link class="nav_element" to="">{{data.pages.home.navigation.label}}</nuxt-link>
    <nuxt-link class="nav_element" to="">{{data.pages.leventshine_calculator.navigation.label}}</nuxt-link>
    <nuxt-link class="nav_element" to="">{{data.pages.gospel_parallels.navigation.label}}</nuxt-link>
  </div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'NavBar',
  components: {
    // Not used
  },
  mounted() {
    console.log("Nav bar mounted")
    console.log(this.data)
  },
  props: {
    // Not Used
  },
  data() {
    return {
      data: siteData
    };
  },
};
</script>

<style scoped>
.nav_container { 
  border: 1px solid green;
  display: flex;
  padding: 5px;
  margin: 5px;
}
.nav_element{ 
  border: 1px solid blue;
  flex-direction: row;
  white-space: nowrap;
  overflow: hidden;
  padding: 5px;
  margin: 5px;
}
</style>
