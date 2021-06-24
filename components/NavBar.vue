<template>
  <nav class="nav">
    <div class="logo">
      <a href="#" class="logo_text">
        {{logoText}}
      </a>
      <span class="subheader">
        {{logoSubTitle}}
      </span>
    </div>
    <a href="about">
      About Project
    </a>
    <a href="calculator">
      Redaction Calculator
    </a>
  </nav>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return {
      logoTitle: 'NT Redaction Calculator',
      logoSubTitle: 'A Calculator for New Testament Studies',
    };
  },
});
</script>

<style scoped>

</style>
