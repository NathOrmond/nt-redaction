<template>
  <div class="container">
		<h2 class="heading__2">{{title}}</h2>
		<h3 class="heading__3">{{sub_title}}</h3>
		<p class="text">{{body}}</p>
  </div>
</template>

<script lang="ts">
export default {
  name: 'TextArea',
  components: {
  },
  props: {
    title: {
			type: String, 
			default: undefined,
			required: false
		},
    sub_title: {
			type: String, 
			default: undefined,
			required: false
		},
    body: {
			type: String, 
			required: true
		}
  },
  data() {
    return {
    };
  },
};
</script>

<style scoped>
</style>
