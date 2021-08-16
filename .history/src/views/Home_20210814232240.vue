<template>
	<header>
		<div class="filter">
			<div class="filter__item">
				<p class="filter__property">Frontend</p>
				<img src="../assets/images/icon-remove.svg" alt="" />
			</div>
			<a href="#">Clear</a>
		</div>
	</header>
	<main>
		<div v-for="card in data" :key="card.id" class="card">
			<div class="card-image">
				<img :src="require(`../assets${card.logo}`)" alt="" />
			</div>
			<div class="card-information">
				<div class="left">
					<div class="company">
						{{ card.company }}
						<div class="detail-information">
							<div class="new">New!</div>
							<div class="featured">Featured</div>
						</div>
					</div>
					<div class="role">{{ card.position }}</div>
					<ul class="information">
						<li>{{ card.postedAt }}</li>
						<li>{{ card.contract }}</li>
						<li>{{ card.location }}</li>
					</ul>
				</div>
				<div class="right">
					<!-- @click="this.$refs.Header.getRole('papap') -->
					<div class="filter" @click="log()">
						{{ card.role }}
					</div>
					<div class="filter">{{ card.level }}</div>
					<div
						v-for="(lang, index) in card.languages"
						:key="index"
						class="filter"
					>
						{{ lang }}
					</div>
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import data from "../../../job-filter/data.json";
export default {
	name: "Home",
	data() {
		return {
			data,
			filters: document.querySelectorAll("filter"),
		};
	},
	methods: {
		log() {
			console.log(this.filters);
		},
	},
};
</script>
<style lang="scss" scoped>
@import "../scss/main.scss";

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
		padding: 2rem 3rem;
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
// HEADER//@
///////////
header {
	background-image: url(../assets/images/bg-header-desktop.svg);
	background-repeat: no-repeat;
	background-size: cover;
	background-color: $dark-cyan;
	height: 13rem;
	display: flex;
	position: relative;
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
}
</style>
