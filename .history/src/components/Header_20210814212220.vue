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
	height: 13rem;
	display: flex;
	position: relative;
}
.filter {
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, 50%);
	width: 90%;
	max-width: 120rem;
	padding: 2rem 3rem;
	box-shadow: 0px 5px 13px 0px $dark-grayish-cyan;
	border-radius: 0.5rem;
	background-color: $white;
}
</style>
