<template>
	<router-view />
</template>

<style lang="scss">
@import "./scss/main";
main {
	padding: 10rem 0rem;
	display: flex;
	align-items: center;
	flex-direction: column;
	grid-gap: 2.5rem;
	.card {
		width: 90%;
		max-width: 120rem;
		display: flex;
		position: relative;
		grid-gap: 1.5rem;
		padding: 1rem 3rem;
		box-shadow: 0px 5px 13px 0px $dark-grayish-cyan;
		border-radius: 0.5rem;
		background-color: $white;
		&::after {
			content: "";
			position: absolute;
			top: 0;
			left: 0;
			height: 100%;
			width: 0.5rem;
			background-color: $dark-cyan;
		}
	}
	.card-information {
		width: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.left,
	.right {
		display: flex;
	}
	.left {
		flex-direction: column;
		grid-gap: 1rem;
	}
	.right {
		grid-gap: 1.5rem;
		flex-direction: row;
		align-items: center;
		color: $dark-cyan;
		font-weight: $font-bold;
		.filter {
			background-color: $light-cyan-filter;
			padding: 1rem;
			cursor: pointer;
			&:hover {
				transition: all 0.3s ease-in-out;
				background-color: $dark-cyan;
				color: $white;
			}
		}
	}
	.information {
		display: flex;
	}
	.company {
		color: $dark-cyan;
		font-weight: $font-bold;
		display: flex;
		align-items: center;
		grid-gap: 2rem;
	}
	.detail-information {
		display: flex;
		grid-gap: 1rem;
		color: $white;
	}
	.featured,
	.new {
		padding: 0.5rem 1rem;
		border-radius: 2rem;
	}
	.new {
		background-color: $dark-cyan;
	}
	.featured {
		background-color: $very-dark-grayish-cyan;
	}
	.role {
		font-weight: $font-bold;
	}
	.information {
		display: flex;
		grid-gap: 3rem;
		font-weight: $font-medium;
		color: $dark-grayish-cyan;
	}
	li:first-child {
		list-style: none;
	}
}
//
header {
	height: 10vh;
	background-color: $dark-cyan;
	background-image: url(./assets/img/bg-header-desktop.svg);
	background-repeat: no-repeat;
	background-position: center;
	background-size: cover;
	position: relative;
}

.filter-bar {
	position: absolute;
	bottom: 0;
	margin-left: auto;
	margin-right: auto;
	left: 0;
	right: 0;
	text-align: center;
	transform: translateY(50%);
	width: 90%;
	margin: auto;
	max-width: 120rem;
	grid-gap: 1.5rem;
	padding: 1rem 3rem;
	box-shadow: 0px 5px 13px 0px $dark-grayish-cyan;
	border-radius: 0.5rem;
	background-color: $white;
}
.filters {
	display: flex;
	justify-content: space-between;
	align-items: center;
	color: $dark-cyan;
}
a {
	color: $dark-cyan;
	font-weight: $font-bold;
}
.filter-wrapper {
	display: flex;
	grid-gap: 1rem;
	background-color: $white;
	font-weight: $font-bold;
	padding: 1rem;
	cursor: pointer;
}
.filter-item {
	background-color: #eef6f6;
	display: flex;
	justify-content: center;
	grid-gap: 1rem;
	.property {
		padding: 1rem;
	}
	svg {
		height: 100%;
		width: 3.4rem;
		background-color: $dark-cyan;
		&:hover {
			transition: all 0.3s ease-in-out;
			background-color: $very-dark-grayish-cyan;
		}
	}
}
</style>
