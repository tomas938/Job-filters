<template>
	<header>
		<div class="filter">
			<div class="filter__property">Frontend</div>
			<img src="../assets/images/icon-remove.svg" alt="" />
		</div>
		<a href="#">clear</a>
	</header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";

header {
	background-image: url(../assets/images/bg-header-desktop.svg);
	background-repeat: no-repeat;
	background-size: cover;
	background-color: $dark-cyan;
	height: 15vh;
}
</style>
