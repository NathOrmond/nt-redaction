<template>
	<div>
		<a>{{ data.pages.home.navigation.label }}</a>
	</div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'NavLogo',
  components: {
  },
  mounted() {

  },
	props: {
    // Not Used
	},
  data() {
    return {
      data: siteData
    };
  },
};
</script>

<style scoped>

</style>