<template>
	<div>
		<a>{{title}}</a>
	</div>
</template>

<script lang="ts">
export default {
  name: 'NavLogo',
  components: {
  },
	props: {
		title: { type:String, required: true},
		sub_title: { type: String, required: true}
	},
  data() {
    return {
    };
  },
};
</script>

<style lang="scss" scoped>

</style>