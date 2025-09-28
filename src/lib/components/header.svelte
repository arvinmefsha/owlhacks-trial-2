<script lang="ts">
	// export let title: string = "TITLE";
</script>

<header class="header">
	<div class="corner-cube"></div>
	<a href="/"><h1 class="title"><b>OWL DASH</b></h1></a>
	<div class="corner-cube"></div>
</header>

<style>
	.header {
		height: 64px;

		background-color: var(--temple-red);

		margin: 0px;
		padding: 4px;

		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}

	.corner-cube {
		background-color: rgba(0, 0, 0, 0.301);
		aspect-ratio: 1;

		height: 100%;
	}

	.title {
		font-size: 30px;
		color: var(--font-color-white);
	}
</style>
