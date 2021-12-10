<script>
	import { page } from '$app/stores';
	import ThemeToggler from './ThemeToggler.svelte';
</script>

<nav class="flex justify-evenly items-center">
	<img src="/icon.png" alt="Logo" width="81" height="100" />
	<a
		class="transition-colors hover:text-blue-900  dark:text-white dark:hover:text-blue-900 text-xl"
		class:active={$page.path == '/'}
		href="/">Home</a
	>
	<a
		class="transition-colors hover:text-blue-900  dark:text-white dark:hover:text-blue-900 text-xl "
		class:active={$page.path == '/services'}
		href="/services">Services</a
	>
	<a
		class="transition-colors hover:text-blue-900  dark:text-white dark:hover:text-blue-900 text-xl "
		class:active={$page.path == '/about'}
		href="/about">About</a
	>
	<a
		class="transition-colors hover:text-blue-900  dark:text-white dark:hover:text-blue-900 text-xl "
		class:active={$page.path == '/contact'}
		href="/contact">Contact</a
	>
	<a
		class="transition-colors hover:text-blue-900  dark:text-white dark:hover:text-blue-900 text-xl "
		class:active={$page.path == '/login'}
		href="/login">Login</a
	>
    <ThemeToggler />
</nav>

<style lang="scss">
	.active {
		color: blue!important;
	}
</style>
