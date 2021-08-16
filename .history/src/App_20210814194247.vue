<template>
	<router-view />
</template>
<script>
import Home from "./views/Home.vue";
export default {
	components: {
		Home,
	},
};
</script>
<style lang="scss">
@import "./scss/main";
</style>
