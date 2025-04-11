<script lang="ts">
	import type { Snippet } from 'svelte';

	// Used lang="ts" bcuz why not
	let {
		name,
		children,
		secondChild
	}: {
		name: string;
		children: Snippet;
		secondChild: Snippet;
	} = $props(); // Whatever variable we create in {} will have values passed from the usage
</script>

<div>
	{#if name}
		<h2>{name}'s Form</h2>
	{/if}
	{@render children()}

	<h3>{@render secondChild('scott')}</h3>
</div>

<style>
</style>
