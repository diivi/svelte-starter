<script>
	import { onMount } from 'svelte';
	import Navbar from '../components/Navbar.svelte';

	let ready = false;

	onMount(() => (ready = true));
</script>

{#if ready}
	<Navbar />
	<slot />
{/if}

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
	.wrapper {
		transition: 0.1s linear;
	}
	:global(html.dark) {
		color: white;
	}
	:global(html.dark) {
		background-color: black;
	}
	:global(html){
		transition: 0.1s linear;
	}
</style>
