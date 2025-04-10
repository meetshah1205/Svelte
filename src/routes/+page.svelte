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
	<p>Step: {formState.step + 1}</p>
	{#if formState.error !== ''}
		<p style="color: red; font-family: sans-serif;">Error: {formState.error}</p>
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
</main>
