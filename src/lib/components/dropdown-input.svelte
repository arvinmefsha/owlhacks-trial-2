<script lang="ts">
	import { createEventDispatcher } from "svelte";

	export let options: string[] = [];
	export let placeholder = "Search...";

	let search = "";
	let showOptions = false;
	let selected = null;

	const dispatch = createEventDispatcher();

	$: filtered = options.filter((o) => o.toLowerCase().includes(search.toLowerCase()));

	function selectOption(option: string) {
		selected = option;
		search = option;
		showOptions = false;

		// Dispatch event to parent
		dispatch("select", { value: option });
	}
</script>

<div class="dropdown">
	<input type="text" bind:value={search} {placeholder} on:focus={() => (showOptions = true)} on:input={() => (showOptions = true)} />

	{#if showOptions && filtered.length > 0}
		<ul class="options">
			{#each filtered as option}
				<li on:click={() => selectOption(option)}>
					{option}
				</li>
			{/each}
		</ul>
	{/if}
</div>

<style>
	.dropdown {
		position: relative;
		width: 200px;
	}

	input {
		width: 100%;
		padding: 6px;
		box-sizing: border-box;
	}

	.options {
		position: absolute;
		top: 100%;
		left: 0;
		right: 0;
		border: 1px solid #ccc;
		background: white;
		max-height: 150px;
		overflow-y: auto;
		margin: 0;
		padding: 0;
		list-style: none;
	}

	.options li {
		padding: 6px;
		cursor: pointer;
	}

	.options li:hover {
		background: #eee;
	}
</style>
