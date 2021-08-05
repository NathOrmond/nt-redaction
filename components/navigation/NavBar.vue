<template>
  <div class="nav_container">
    <nav-logo
    :title="logo_title"
    :sub_title="logo_sub_title"
    />
    <nav class="nav">
      <nav-element 
      v-for="element in nav_elements" 
      :key="element"
      :label="element.label" 
      :link_url="element.link_url" />
    </nav>
  </div>
</template>

<script lang="ts">
import NavLogo from '@/components/navigation/NavLogo.vue'
import NavElement from '@/components/navigation/NavElement.vue'

export default {
  name: 'NavBar',
  components: {
    NavLogo,
    NavElement,
  },
  props: {
    logo_title: {type: String, required: true},
    logo_sub_title: {type: String, required:true},
    nav_elements: {type:Array, required: true}
  },
  data() {
    return {
    };
  },
};
</script>

<style scoped>

</style>
