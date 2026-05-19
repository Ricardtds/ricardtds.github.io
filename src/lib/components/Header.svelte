<script>
	let menuOpen = false;
	import { fly } from 'svelte/transition';

	let scrollY = 0;
	$: scrolled = scrollY > 20;
</script>

<svelte:window bind:scrollY />

<header class="fixed top-0 right-0 left-0 z-50 transition-all duration-300" class:scrolled>
	<div class="mx-auto max-w-6xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<a href="/" class="logo-text" aria-label="Página inicial">
				<span class="logo-bracket">&lt;</span><span class="logo-name"
					>Ricardo<span class="logo-accent">T</span></span
				><span class="logo-bracket">/&gt;</span>
			</a>

			<nav class="hidden items-center gap-8 md:flex">
				{#each [['#sobre', 'Sobre'], ['#tecnologias', 'Skills'], ['#resumo', 'Currículo'], ['#contato', 'Contato']] as [href, label]}
					<a {href} class="nav-link">{label}</a>
				{/each}
				<div class="flex items-center gap-3 border-l border-white/10 pl-6">
					<a
						href="https://www.instagram.com/ricardtds/"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="Instagram"
						class="social-icon"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24"
							><path
								d="M7.75 2h8.5A5.76 5.76 0 0122 7.75v8.5A5.76 5.76 0 0116.25 22h-8.5A5.76 5.76 0 012 16.25v-8.5A5.76 5.76 0 017.75 2zm0 1.5A4.26 4.26 0 003.5 7.75v8.5A4.26 4.26 0 007.75 20.5h8.5a4.26 4.26 0 004.25-4.25v-8.5A4.26 4.26 0 0016.25 3.5h-8.5zM12 7a5 5 0 110 10 5 5 0 010-10zm0 1.5a3.5 3.5 0 100 7 3.5 3.5 0 000-7zm4.75-.88a1.12 1.12 0 110 2.25 1.12 1.12 0 010-2.25z"
							/></svg
						>
					</a>
					<a
						href="https://github.com/Ricardtds"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="GitHub"
						class="social-icon"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24"
							><path
								d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.11.82-.26.82-.577v-2.234c-3.338.724-4.033-1.416-4.033-1.416-.546-1.385-1.333-1.754-1.333-1.754-1.09-.744.082-.729.082-.729 1.205.084 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.997.108-.774.418-1.305.762-1.605-2.665-.3-5.467-1.332-5.467-5.933 0-1.31.468-2.382 1.235-3.222-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 016 0c2.292-1.552 3.3-1.23 3.3-1.23.653 1.653.241 2.873.118 3.176.77.84 1.234 1.912 1.234 3.222 0 4.61-2.807 5.63-5.479 5.923.43.37.823 1.102.823 2.222v3.293c0 .32.218.694.825.576C20.565 21.796 24 17.3 24 12c0-6.63-5.373-12-12-12z"
							/></svg
						>
					</a>
					<a
						href="https://www.linkedin.com/in/ricardtds/"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="LinkedIn"
						class="social-icon"
					>
						<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24"
							><path
								d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
							/></svg
						>
					</a>
				</div>
			</nav>

			<button
				class="hamburger md:hidden"
				on:click={() => (menuOpen = !menuOpen)}
				aria-label={menuOpen ? 'Fechar menu' : 'Abrir menu'}
			>
				<span class="bar" class:open={menuOpen}></span>
			</button>
		</div>
	</div>

	{#if menuOpen}
		<nav class="mobile-menu md:hidden" transition:fly={{ y: -10, duration: 200 }}>
			{#each [['#sobre', 'Sobre'], ['#tecnologias', 'Skills'], ['#resumo', 'Currículo'], ['#contato', 'Contato']] as [href, label]}
				<a {href} class="mobile-nav-link" on:click={() => (menuOpen = false)}>{label}</a>
			{/each}
			<div class="mt-3 flex gap-4 border-t border-white/10 pt-3">
				<a
					href="https://www.instagram.com/ricardtds/"
					target="_blank"
					rel="noopener noreferrer"
					class="social-icon"
					><svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24"
						><path
							d="M7.75 2h8.5A5.76 5.76 0 0122 7.75v8.5A5.76 5.76 0 0116.25 22h-8.5A5.76 5.76 0 012 16.25v-8.5A5.76 5.76 0 017.75 2zm0 1.5A4.26 4.26 0 003.5 7.75v8.5A4.26 4.26 0 007.75 20.5h8.5a4.26 4.26 0 004.25-4.25v-8.5A4.26 4.26 0 0016.25 3.5h-8.5zM12 7a5 5 0 110 10 5 5 0 010-10zm0 1.5a3.5 3.5 0 100 7 3.5 3.5 0 000-7zm4.75-.88a1.12 1.12 0 110 2.25 1.12 1.12 0 010-2.25z"
						/></svg
					></a
				>
				<a
					href="https://github.com/Ricardtds"
					target="_blank"
					rel="noopener noreferrer"
					class="social-icon"
					><svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24"
						><path
							d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.11.82-.26.82-.577v-2.234c-3.338.724-4.033-1.416-4.033-1.416-.546-1.385-1.333-1.754-1.333-1.754-1.09-.744.082-.729.082-.729 1.205.084 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.997.108-.774.418-1.305.762-1.605-2.665-.3-5.467-1.332-5.467-5.933 0-1.31.468-2.382 1.235-3.222-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 016 0c2.292-1.552 3.3-1.23 3.3-1.23.653 1.653.241 2.873.118 3.176.77.84 1.234 1.912 1.234 3.222 0 4.61-2.807 5.63-5.479 5.923.43.37.823 1.102.823 2.222v3.293c0 .32.218.694.825.576C20.565 21.796 24 17.3 24 12c0-6.63-5.373-12-12-12z"
						/></svg
					></a
				>
				<a
					href="https://www.linkedin.com/in/ricardtds/"
					target="_blank"
					rel="noopener noreferrer"
					class="social-icon"
					><svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24"
						><path
							d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
						/></svg
					></a
				>
			</div>
		</nav>
	{/if}
</header>

<style>
	header {
		background: transparent;
	}
	header.scrolled {
		background: rgba(6, 11, 18, 0.94);
		backdrop-filter: blur(20px);
		border-bottom: 1px solid rgba(249, 199, 86, 0.08);
		box-shadow: 0 4px 32px rgba(0, 0, 0, 0.5);
	}
	.logo-text {
		font-family: 'Courier New', monospace;
		font-size: 1.1rem;
		font-weight: 700;
		text-decoration: none;
		display: flex;
		align-items: center;
	}
	.logo-bracket {
		color: #f9c756;
	}
	.logo-name {
		color: #fff;
	}
	.logo-accent {
		color: #f9c756;
	}
	.nav-link {
		font-size: 0.8rem;
		font-weight: 500;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: #9ca3af;
		text-decoration: none;
		position: relative;
		padding-bottom: 3px;
		transition: color 0.2s;
	}
	.nav-link::after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 0;
		width: 0;
		height: 1px;
		background: #f9c756;
		transition: width 0.25s;
	}
	.nav-link:hover {
		color: #f9c756;
	}
	.nav-link:hover::after {
		width: 100%;
	}
	.social-icon {
		color: #9ca3af;
		transition:
			color 0.2s,
			transform 0.2s;
		display: flex;
	}
	.social-icon:hover {
		color: #f9c756;
		transform: translateY(-2px);
	}
	.hamburger {
		background: none;
		border: none;
		cursor: pointer;
		width: 36px;
		height: 36px;
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
	}
	.bar {
		display: block;
		width: 22px;
		height: 2px;
		background: #f9c756;
		border-radius: 2px;
		transition: all 0.3s;
		position: relative;
	}
	.bar::before,
	.bar::after {
		content: '';
		position: absolute;
		width: 22px;
		height: 2px;
		background: #f9c756;
		border-radius: 2px;
		transition: all 0.3s;
	}
	.bar::before {
		top: -7px;
	}
	.bar::after {
		top: 7px;
	}
	.bar.open {
		background: transparent;
	}
	.bar.open::before {
		transform: rotate(45deg);
		top: 0;
	}
	.bar.open::after {
		transform: rotate(-45deg);
		top: 0;
	}
	.mobile-menu {
		background: rgba(6, 11, 18, 0.98);
		border-bottom: 1px solid rgba(249, 199, 86, 0.1);
		padding: 1rem 1.5rem 1.25rem;
		display: flex;
		flex-direction: column;
		gap: 0;
	}
	.mobile-nav-link {
		color: #9ca3af;
		text-decoration: none;
		font-size: 0.9rem;
		font-weight: 500;
		padding: 0.6rem 0;
		border-bottom: 1px solid rgba(255, 255, 255, 0.05);
		transition: color 0.2s;
	}
	.mobile-nav-link:hover {
		color: #f9c756;
	}
</style>
