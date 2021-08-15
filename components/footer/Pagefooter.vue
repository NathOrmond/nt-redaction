<template>
  <div class="custom__footer__component">
    <footer class="custom__footer__component__inner__footer">
      
      <div class="component__item">
        <h3>{{ data.meta.title }}</h3>
        <p>{{ data.meta.sub_title }}</p>
      </div>
    
      <div class="component__item">
        <h3>Contributors</h3>
        <li v-for="(contributor, index) in data.meta.contributors" v-bind:key="index">
          {{ contributor }}
        </li>
      </div>
    
      <div class="component__item">
        <p>License Information</p>
        <a href="">{{ data.meta.license.name }}</a>
      </div>
    
    </footer>
  </div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'Test',
  components: { },
  mounted() {  },
  props: {  },
  data() {
    return {
      data: siteData
    };
  },
};
</script>

<style scoped>
.custom__footer__component { 
  background-color: lightgray;
  padding: 1px;
  margin: 1px;
}

.custom__footer__component__inner__footer{
  display: flex;
  padding: 1px;
  margin: 1px;
}

.component__item{
  flex-direction: row;
  flex-grow: 1;
  padding: 1px;
  margin: 1px;
}



</style>
