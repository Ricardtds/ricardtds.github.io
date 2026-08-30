<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<meta name="theme-color" content="#121212" />
</svelte:head>

<div class="min-h-screen">
	<Header />
	<main class="w-full">{@render children?.()}</main>
	<Footer />
</div>
