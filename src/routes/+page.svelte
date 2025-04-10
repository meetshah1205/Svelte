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
	<Header name={formState.name}></Header>
	<p>Step: {formState.step + 1}</p>
	{#if formState.error !== ''}
		<p class="error">Error: {formState.error}</p>
	{/if}

	{#if formState.step === 0}
		<div>
			<label for="name">Your Name</label>
			<input type="text" id="name" bind:value={formState.name} />
		</div>
		<button
			onclick={() => {
				if (formState.name !== '') {
					formState.step++;
					formState.error = '';
				} else {
					formState.error = 'Ur name is empty. Provide a name';
				}
			}}>Next</button
		>
	{:else if formState.step === 1}
		<div>
			<label for="birthday">Your Birthday</label>
			<input type="date" id="bday" bind:value={formState.birthday} />
		</div>
		<button
			onclick={() => {
				if (formState.birthday !== '') {
					formState.step++;
					formState.error = '';
				} else {
					formState.error = 'Ur birthday is empty. Provide a birthday';
				}
			}}>Next</button
		>
	{/if}

	<h2> Hover me </h2>
</main>


<style>
	h2 {
		color: red;
		font-family: system-ui;
		/* font-weight: 500; */
		padding: 2px;
	}
</style>