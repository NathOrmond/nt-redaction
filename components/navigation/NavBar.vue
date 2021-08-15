<template>
  <div class="nav_container">
    <nuxt-link class="nav_element" to="/">{{data.pages.home.navigation.label}}</nuxt-link>
    <nuxt-link class="nav_element" to="/levenshtein_calculator">{{data.pages.levenshtein_calculator.navigation.label}}</nuxt-link>
    <nuxt-link class="nav_element" to="/gospel_parallels">{{data.pages.gospel_parallels.navigation.label}}</nuxt-link>
  </div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'NavBar',
  components: {  },
  mounted() {
    console.log("Nav bar mounted")
    console.log(this.data)
  },
  props: {  },
  data() {
    return {
      data: siteData
    };
  },
};
</script>

<style scoped>
.nav_container { 
  background: green;
  display: flex;
  padding: 5px;
  margin: 5px;
}
.nav_element{
  background: green; 
  color: white;
  flex-direction: row;
  white-space: nowrap;
  overflow: hidden;
  padding: 5px;
  margin: 5px;
}

.nav_element:hover{
  background: mediumseagreen;
}
</style>
