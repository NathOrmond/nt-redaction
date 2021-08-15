<template>
  <div class="container">
    <h1>TEST</h1>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  components: {
  },
  data(){
    return{
      id: this.$route.params.redactioncalculator,
      calculated: false
    }
  },
  methods: {
    isCalculated(): boolean{ 
      return this.calculated;
    },
    setCalculated(newValue: boolean): void { 
      this.calculated = newValue;
    }
  }
});
</script>

<style scoped>

</style>