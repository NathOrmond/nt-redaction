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
      textBody: 'Lorem Ipsum Id Quo Nihil Maius Cogitari Potest Et Hoc Omnes Intelligent Deum Amor Vincit Omnia Et Nos Cedamus Amori'
    }
  }
});
</script>

<style scoped>

</style>
