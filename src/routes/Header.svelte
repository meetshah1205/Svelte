<script lang="ts">
	// Used lang="ts" bcuz why not
	let {
		name,
	}: {
		name: string;
	} = $props(); // Whatever variable we create in {} will have values passed from the usage
</script>

<div>
	{#if name}
	<h2>{name}'s Form</h2>
	{/if}
</div>

<style>
</style>
