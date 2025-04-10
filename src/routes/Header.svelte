<script lang="ts">
	// Used lang="ts" bcuz why not
	let {
		name,
		fake_name = null // Put null as value if not using TS
	}: {
		name: string;
		fake_name?: string | null; // Optional prop
	} = $props(); // Whatever variable we create in {} will have values passed from the usage
</script>

<h2>{name.replaceAll('o', 'x')}</h2>
{fake_name}

<style>
</style>
