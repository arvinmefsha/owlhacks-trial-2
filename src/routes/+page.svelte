<script lang="ts">
	import SiteHeader from "$lib/components/header.svelte";
	import DropdownInput from "$lib/components/dropdown-input.svelte";

	function handleSelect(event: any) {
		console.log("Selected:", event.detail.value);
	}
</script>

<!-- header -->

<SiteHeader />

<!-- main body -->

<body class="main-body">
	<!-- <a href="/login">login here</a> -->

	<div class="place-input">
		<p class="text-align-center">Location</p>
		<DropdownInput options={["aw", "awa", "awf", "atwe", "gsdsgfd"]} on:select={handleSelect} />
	</div>
</body>

<style>
	.main-body {
		display: flex;
		flex-direction: column;
	}

	.place-input {
		display: flex;
		flex-direction: column;
		flex-grow: 1;

		background-color: var(--grey);
		/* height: 100px; */

		margin: 16px;
		padding: 8px;
	}

	.place-input-box {
		flex: auto;
		background-color: var(--color-white);

		padding-inline: 8px;
		padding-block: 4px;
	}
</style>
