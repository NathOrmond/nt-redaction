<template>
	<div>
		<nuxt-link to="">{{label}}</nuxt-link>
	</div>
</template>

<script lang="ts">
export default {
  name: 'NavElement',
  components: {
  },
	props: {
		label: { 
      type:String, 
      required: true
    },
		link_url: { 
      type: String, 
      required: false
    }
	},
  data() {
    return {
    };
  },
};
</script>

<style  scoped>

</style>
