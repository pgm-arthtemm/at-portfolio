<script>
	let techArray = ['Svelte', 'Tailwind', 'ReactJS', 'Sass', 'Bootstrap', 'GSAP'];
</script>

<div class="tech">
	<h3 class="text-3xl text-center">
		My favorite <span class="text-red-700">tools:</span>
	</h3>
	<ul class="flex-container">
		{#each techArray as item}
			<li class="w-1/4 m-2 pt-8">
				<img class="m-auto w-16" src={`/${item}.png`} alt={item} />
				<h4 class="text-lg xl:text-2xl xl:mt-2 text-center transition duration-300 ease-in-out">
					{item}
				</h4>
			</li>
		{/each}
	</ul>
	<h3 class="text-xl mt-12 text-center pb-24 leading-8">
		<a href="https://github.com/pgm-arthtemm/at-portfolio" target="_blank">This website</a> was made
		with
		<span class="text-red-700">Sveltekit</span> and <span class="text-red-700">Tailwind</span>
	</h3>
</div>

<style>
	ul {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
	}

	li:hover {
		cursor: pointer;
	}

	li:hover h4 {
		color: rgba(185, 28, 28);
	}

	a {
		text-decoration: underline 4px solid rgba(185, 28, 28);
		transition: all 0.3s;
	}

	a:hover {
		color: rgba(185, 28, 28);
	}

	@media (min-width: 1279px) {
		.tech {
			position: absolute;
			top: 0;
			right: 0;
			width: 40%;
			height: 90%;
		}
	}
</style>
