<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>
<div class="flex h-lvh w-lvw flex-col font-[Mignon]">
	<Header />

	<main class="w-full flex-1 overflow-y-auto text-white">
		{@render children?.()}
	</main>

	<Footer />
</div>

