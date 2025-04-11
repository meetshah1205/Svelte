<script lang="ts">
	import Header from './Header.svelte';

	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ''
	});
</script>

<main>
	<Header name={formState.name}>
		<p>Hello</p>
		{#snippet secondChild(name)}
			<p>Second child {name}</p>
		{/snippet}
	</Header>
	<p>Step: {formState.step + 1}</p>

	{@render formStep({ question: "What's ur name?", id: 'name', type: 'text' })}
</main>

{#snippet formStep({ question, id, type }: { type: string; id: string; question: string })}
	<article>
		<div>
			<label for={id}>{question}</label>
			<input {type} {id} bind:value={formState[id]} />
		</div>
	</article>
{/snippet}

<style>
	.error {
		color: red;
		font-family: system-ui;
		/* font-weight: 500; */
		padding: 2px;
	}
</style>
