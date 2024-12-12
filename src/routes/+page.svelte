<script>
	// @ts-nocheck

	const imageModules = import.meta.glob('$lib/imageDumps/jeannette/*.jpg', {
		eager: true,
		query: {
			enhanced: true
		}
	});
</script>

<div class="container">
	{#each Object.entries(imageModules) as [_path, module]}
		<enhanced:img src={module.default} alt="some alt text" class="enhanced" />
	{/each}
</div>

<style>
	.enhanced {
		width: 100%;
		height: auto;
		margin-block: 2rem;
	}
	.container {
		width: 90%;
		margin-inline: auto;
	}
</style>
