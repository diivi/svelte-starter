<script>
	import { onMount } from 'svelte';
	import Navbar from '../components/Navbar.svelte';

	let ready = false;

	onMount(() => (ready = true));
</script>

{#if ready}
	<div class="dark:bg-black bg-white min-h-screen h-full wrapper">
		<Navbar />
		<slot  />
	</div>
{/if}

<style >
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
	.wrapper {
		transition: 0.1s linear;
	}
	:global(html.dark){
		color:white
	}
</style>
