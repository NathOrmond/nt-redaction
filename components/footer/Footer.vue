<template>
	<div class="footer">
		<!-- TODO Footer with relevant info -->
    <p>TODO: Footer stuff goes here</p>
	</div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'Footer',
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
.footer{
    border: 1px solid orange;
    flex-direction: row;
}
</style>