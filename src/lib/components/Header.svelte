<script lang="ts">
	import { fly } from 'svelte/transition';

	let menuOpen = false;
	let scrollY = 0;
	$: scrolled = scrollY > 20;

	const navigation = [
		['#projetos', 'Projetos'],
		['#atuacao', 'Atuação'],
		['#sobre', 'Sobre'],
		['#contato', 'Contato']
	];
</script>

<svelte:window bind:scrollY />

<header
	class={`fixed inset-x-0 top-0 z-50 border-b transition-all duration-300 ${
		scrolled || menuOpen
			? 'border-white/10 bg-[#121212]/96 shadow-lg backdrop-blur-xl'
			: 'border-transparent bg-[#121212]'
	}`}
>
	<div class="section-shell flex h-20 items-center justify-between">
		<a href="#inicio" class="group flex items-center gap-3" aria-label="Ir para o início">
			<span
				class="grid size-10 place-items-center rounded-full border border-white/40 font-mono text-xs font-black tracking-[-0.08em] text-white transition group-hover:border-[#e8a537] group-hover:text-[#e8a537]"
				>RT</span
			>
			<span class="hidden text-xs font-semibold tracking-[0.08em] text-white sm:block"
				>RICARDO TEIXEIRA</span
			>
		</a>

		<nav class="hidden items-center gap-8 md:flex" aria-label="Navegação principal">
			{#each navigation as [href, label] (href)}
				<a
					{href}
					class="text-[0.68rem] font-semibold tracking-[0.08em] text-white/55 uppercase transition hover:text-[#4fd0c5]"
					>{label}</a
				>
			{/each}
			<a
				href="https://github.com/Ricardtds"
				target="_blank"
				rel="noopener noreferrer"
				class="border border-white/20 px-4 py-2 text-[0.68rem] font-semibold text-white transition hover:border-[#e8a537] hover:text-[#e8a537]"
				>GitHub ↗</a
			>
		</nav>

		<button
			type="button"
			class="grid size-10 place-items-center border border-white/20 text-white md:hidden"
			onclick={() => (menuOpen = !menuOpen)}
			aria-label={menuOpen ? 'Fechar menu' : 'Abrir menu'}
			aria-expanded={menuOpen}
		>
			<svg class="size-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8">
				{#if menuOpen}
					<path d="M6 6l12 12M18 6 6 18" />
				{:else}
					<path d="M4 7h16M4 12h16M4 17h16" />
				{/if}
			</svg>
		</button>
	</div>

	{#if menuOpen}
		<nav
			class="section-shell flex flex-col border-t border-white/10 bg-[#121212] py-3 md:hidden"
			aria-label="Navegação móvel"
			transition:fly={{ y: -8, duration: 180 }}
		>
			{#each navigation as [href, label] (href)}
				<a
					{href}
					class="border-b border-white/8 py-3 text-sm font-medium text-white/70"
					onclick={() => (menuOpen = false)}>{label}</a
				>
			{/each}
			<a
				href="https://github.com/Ricardtds"
				target="_blank"
				rel="noopener noreferrer"
				class="py-3 text-sm font-medium text-[#e8a537]">GitHub ↗</a
			>
		</nav>
	{/if}
</header>
