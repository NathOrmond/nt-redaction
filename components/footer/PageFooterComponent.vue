<template>
	<div class="footer">
		
    

	</div>
</template>

<script lang="ts">
import siteData from '~/resources/siteData.json';

export default {
  name: 'PageFooterComponent',
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