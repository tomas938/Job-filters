<template>
	<div></div>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {
		// getRole() {},
	},
};
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
	bottom: 0;
	left: 0;
	right: 0;
	margin: auto;
	transform: translateY(50%);
	width: 90%;
	max-width: 120rem;
	padding: 2rem 3rem;
	box-shadow: 0px 5px 13px 0px $dark-grayish-cyan;
	border-radius: 0.5rem;
	background-color: $white;
	display: flex;
	justify-content: space-between;
	align-items: center;
	&__item {
		display: flex;
		align-items: center;
		cursor: pointer;
	}
	a {
		justify-self: flex-end;
		color: $dark-cyan;
		font-weight: $font-bold;
	}
	p {
		padding: 1rem;
		color: $dark-cyan;
		font-weight: $font-bold;
		background-color: $light-cyan-filter;
	}
	img {
		padding: 1rem;
		background: $dark-cyan;
		&:hover {
			transition: background-color 0.3s ease-in-out;
			background-color: $very-dark-grayish-cyan;
		}
	}
}
</style>
