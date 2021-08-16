<template>
	<header>
		<div class="filter-bar">
			<div class="filters">
				<div class="filter-wrapper">
					<div class="filter-item">
						<div class="property">Front end</div>
						<svg xmlns="http://www.w3.org/2000/svg" width="1366" height="156">
							<g fill="#63BABA" fill-rule="evenodd">
								<path
									d="M470.577 563.429c-51.432-51.425-51.438-134.806-.013-186.237l.013-.013L867.235-19.424c51.441-51.434 134.836-51.434 186.276 0 48.811 48.804 51.304 126.392 7.473 178.135l178.158-178.135c51.441-51.434 134.836-51.434 186.277 0 51.431 51.424 51.437 134.805.013 186.237-.005.004-.01.008-.013.013l-396.66 396.603c-51.44 51.433-134.834 51.433-186.275 0-48.812-48.805-51.304-126.394-7.471-178.138L656.853 563.43c-51.441 51.433-134.836 51.433-186.276 0zM342.268 45.605c-51.432-51.425-51.438-134.806-.013-186.237l.013-.013 396.658-396.603c51.441-51.434 134.836-51.434 186.277 0 51.431 51.424 51.437 134.805.013 186.237-.005.004-.01.008-.013.013L528.543 45.605c-51.44 51.433-134.834 51.433-186.275 0zm-444.692 71.824c-51.432-51.424-51.438-134.806-.013-186.237l.013-.013 396.658-396.603c51.441-51.434 134.836-51.434 186.277 0 51.431 51.424 51.437 134.805.013 186.237a80.86 80.86 0 01-.013.013L83.85 117.429c-51.44 51.433-134.834 51.433-186.275 0z"
								/>
							</g>
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
						</svg>
					</div>
				</div>
				<a href="#">Clear</a>
			</div>
		</div>
	</header>
	<main>
		<!-- <div class="card-image">
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
		</div> -->
	</main>
</template>

<script>
// @ is an alias to /src

export default {
	name: "Home",
	components: {},
};
</script>
