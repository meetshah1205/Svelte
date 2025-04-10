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
	:global(div:hover){
		background-color: red;  
		border: 2px solid black;
		border-radius: 8px;
		padding: 20px;
		transition: all ease-in-out 2s;
		font-family: cursive;	
	}

	h2:hover{ 
		font-size: 26; /* Same, h2 in +page.svelte won't be affected by this */
		font-family: cursive;
		transition: all ease-in 5s;
	}
</style>
