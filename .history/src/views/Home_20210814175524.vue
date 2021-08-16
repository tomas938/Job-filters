<template>
	<header>
		<div class="filter-bar">
			<div class="filters">
				<div class="filter-wrapper">
					<div class="filter-item">
						<div class="property">Front end</div>
						<!-- <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14">
							<path
								fill="#fff"
								fill-rule="evenodd"
								d="M11.314 0l2.121 2.121-4.596 4.596 4.596 4.597-2.121 2.121-4.597-4.596-4.596 4.596L0 11.314l4.596-4.597L0 2.121 2.121 0l4.596 4.596L11.314 0z"
							/>
						</svg>
					</div>
					<div class="filter-item">
						<div class="property">Front end</div>
						<svg xmlns="http://www.w3.org/2000/svg" width="14" height="14">
							<path
								fill="#fff"
								fill-rule="evenodd"
								d="M11.314 0l2.121 2.121-4.596 4.596 4.596 4.597-2.121 2.121-4.597-4.596-4.596 4.596L0 11.314l4.596-4.597L0 2.121 2.121 0l4.596 4.596L11.314 0z"
							/>
						</svg> -->
					</div>
				</div>
				<a href="#">Clear</a>
			</div>
		</div>
	</header>
	<main>
		<div class="card-image">
			<img src="${item.logo}" alt="" />
		</div>
		<div class="card-information">
			<div class="left">
				<div class="company">
					${item.company}
					<div class="detail-information">
						<div class="new">New!</div>
						<div class="featured">Featured</div>
					</div>
				</div>
				<div class="role">${item.position}</div>
				<ul class="information">
					<li>${item.postedAt}</li>
					<li>${item.contract}</li>
					<li>${item.location}</li>
				</ul>
			</div>
			${item.languages ? lang(item.languages, item.role, item.level) : ""}
		</div>
	</main>
</template>

<script>
// @ is an alias to /src

export default {
	name: "Home",
	components: {},
};
</script>
