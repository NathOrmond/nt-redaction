<template>
	<div>
		<a>{{label}}</a>
	</div>
</template>

<script lang="ts">
export default {
  name: 'NavElement',
  components: {
  },
	props: {
		label: { type:String, required: true},
		link_url: { type: String, required: false}
	},
  data() {
    return {
    };
  },
};
</script>

<style lang="scss" scoped>

</style>
