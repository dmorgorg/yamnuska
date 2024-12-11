<script>
	// @ts-nocheck

	// import MyImage from '$lib/imageDump/2008-07-01-170627.jpg?enhanced';

	const imageModules = import.meta.glob('$lib/imageDump/*.jpg', {
		eager: true,
		query: {
			enhanced: true
		}
	});
</script>

<h1>Images galore?</h1>

<div class="container">
	<!-- <enhanced:img src={MyImage} alt="some alt text" class="enhanced" /> -->
	{#each Object.entries(imageModules) as [_path, module]}
		<enhanced:img src={module.default} alt="some alt text" class="enhanced" />
	{/each}
</div>

<style>
	.enhanced {
		width: 100%;
		height: auto;
	}
	.container {
		width: 90%;
		margin-inline: auto;
	}
</style>
