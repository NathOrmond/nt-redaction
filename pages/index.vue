<template>
  <div class="container">
    <div class="container__nav">
      <nav-bar />
    </div>
    <div class="container__textarea">
      <text-area 
      :title="textTitle" 
      :sub_title="textSubTitle" 
      :body="textBody" 
      />
    </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '@/components/navigation/NavBar.vue';
import TextArea from '@/components/text/TextArea.vue';
import textData from '../resources/text.json';

export default Vue.extend({
  components: {
    NavBar,
    TextArea
  },
  data(){
    return{
      logoTitle: '',
      logoSubTitle: '',
      navElements: [],
      textTitle: 'Title',
      textSubTitle: 'SubTitle Goes Here',
      textBody: '',
      data: textData
    }
  }
});
</script>

<style scoped>

</style>
