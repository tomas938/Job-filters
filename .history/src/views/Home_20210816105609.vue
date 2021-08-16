<template>
	<header>
		<transition name="fade">
			<div class="filter" v-if="roles.length > 0">
				<div class="filter__wrapper">
					<div class="filter__item" v-for="(role, index) in roles" :key="index">
						<p class="filter__property">{{ role }}</p>
						<img
							src="../assets/images/icon-remove.svg"
							alt=""
							@click="removeElement(index)"
						/>
					</div>
				</div>
				<a href="#" @click="removeAllElements()">Clear</a>
			</div>
		</transition>
	</header>
	<transition-group name="list" tag="main" appear>
		<div v-for="card in filterData" :key="card.id" class="card">
			<span v-if="card.new && card.featured"></span>
			<div class="card-image">
				<img :src="require(`../assets${card.logo}`)" alt="" />
			</div>
			<div class="card-information">
				<div class="left">
					<div class="company">
						{{ card.company }}
						<div class="detail-information">
							<div class="new" v-if="card.new">New!</div>
							<div class="featured" v-if="card.featured">Featured</div>
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
					<div class="filter" @click="addFilter(card.role)">
						{{ card.role }}
					</div>
					<div class="filter" @click="addFilter(card.level)">
						{{ card.level }}
					</div>
					<div
						v-for="(lang, index) in card.languages"
						:key="index"
						class="filter"
						@click="addFilter(lang)"
					>
						{{ lang }}
					</div>
				</div>
			</div>
		</div>
	</transition-group>
</template>

<script>
import data from "../../../job-filter/data.json";
export default {
	name: "Home",
	data() {
		return {
			show: false,
			data,
			filter: "",
			roles: [],
		};
	},
	methods: {
		removeElement(index) {
			this.roles.splice(index, 1);
		},
		removeAllElements() {
			this.roles = [];
		},
		addFilter(filter) {
			if (this.roles.some((e) => e === filter)) return;
			this.roles.push(filter);
		},
	},

	computed: {
		filterData() {
			if (this.roles.length === 0) {
				return this.data;
			} else {
				return this.data.filter((jobData) => {
					let jobCategories = [
						jobData.role,
						jobData.level,
						...jobData.languages,
					];
					return this.roles.every((filter) => jobCategories.includes(filter));
				});
			}
		},
	},
};
</script>
<style lang="scss" scoped>
@import "../scss/main.scss";
h1 {
	font-size: 30rem;
}
main {
	padding: 10rem 0rem;
	display: flex;
	align-items: center;
	flex-direction: column;
	gap: 2.5rem;
	@media only screen and (max-width: 1000px) {
		gap: 5rem;
		padding: 14rem 0rem;
	}
	.card {
		width: 90%;
		max-width: 120rem;
		display: flex;
		gap: 1.5rem;
		padding: 2rem 3rem;
		box-shadow: 0px 5px 13px 0px $dark-grayish-cyan;
		border-radius: 0.5rem;
		background-color: $white;
		@media only screen and (max-width: 1000px) {
			flex-direction: column;
			max-width: 80rem;
			padding: 4rem 4rem 3rem 4rem;
		}
		@media only screen and (max-width: 400px) {
			padding: 4rem 3rem;
		}
	}
	span {
		// content: "";

		height: 100%;
		width: 0.5rem;
		background-color: $dark-cyan;
	}
	.card-image {
		@media only screen and (max-width: 1000px) {
			position: absolute;
			top: -29px;
			left: 33px;
			@media only screen and (max-width: 360px) {
				left: 23px;
			}
			img {
				width: 65%;
				@media only screen and (max-width: 400px) {
					width: 55%;
				}
			}
		}
	}
	.card-information {
		width: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
		@media only screen and (max-width: 1000px) {
			flex-direction: column;
			align-items: flex-start;
			gap: 2rem;
		}
	}
	.left,
	.right {
		display: flex;
	}
	.left {
		@media only screen and (max-width: 1000px) {
			width: 100%;
			border-bottom: 1px solid #c0c2c1;
		}
		flex-direction: column;
		grid-gap: 1rem;
	}
	.right {
		grid-gap: 1.5rem;
		flex-direction: row;
		align-items: center;
		flex-wrap: wrap;
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
		@media only screen and (max-width: 1000px) {
			padding-bottom: 2rem;
		}
		@media only screen and (max-width: 415px) {
			font-size: 1.3rem;
		}
	}
	.company {
		color: $dark-cyan;
		font-weight: $font-bold;
		display: flex;
		align-items: center;
		grid-gap: 2rem;
	}
	.detail-information {
		@media only screen and (max-width: 415px) {
			font-size: 1rem;
		}
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
		&__wrapper {
			display: flex;
			flex-wrap: wrap;
			gap: 2rem;
			@media only screen and (max-width: 500px) {
				gap: 1rem;
			}
		}
		&__item {
			display: flex;
			align-items: center;
			cursor: pointer;
		}
		a {
			margin-left: 1rem;
			justify-self: flex-end;
			color: $dark-cyan;
			font-weight: $font-bold;
		}
		p {
			padding: 1rem;
			@media only screen and (max-width: 500px) {
				padding: 0.7rem;
			}
			color: $dark-cyan;
			font-weight: $font-bold;
			background-color: $light-cyan-filter;
		}
		img {
			height: 100%;
			padding: 1rem;
			@media only screen and (max-width: 500px) {
				padding: 0.7rem;
			}
			background: $dark-cyan;
			&:hover {
				transition: background-color 0.3s ease-in-out;
				background-color: $very-dark-grayish-cyan;
			}
		}
	}
}

/// TRANSITIONS ///

// ** FILTER ** ///
.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
.fade-enter-active {
	transition: all 0.3s ease-out;
}

.fade-leave-active {
	transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

// ** CARD ** ///

.list-enter-active {
	transition: all 1s ease;
}
.list {
	display: inline-block;
}
.list-leave-active {
	transition: all 1s ease;
	position: absolute;
}
.list-enter-from,
.list-leave-to {
	opacity: 0;
	transform: translateY(30px);
}
.list-move {
	transition: transform 0.5s ease;
}
</style>
