<script>
	let menuOpen = false;
	import { fade } from 'svelte/transition';
</script>

<header class="bg-[#0A141F] font-[InknutAntiqua] shadow-md">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-auto items-center justify-between py-1">
			<!-- Logo -->
			<div class="flex flex-shrink-0 items-center">
				<a
					href="/"
					class="inline-flex text-xl font-bold hover:animate-pulse"
					aria-label="Página inicial"
				>
					<p class="text-[#F9C756]">R</p>
					<p class="text-white">icardins</p>
					<p class="text-[#F9C756]">T</p>
				</a>
			</div>

			<!-- Menu Desktop -->
			<nav class="hidden items-center space-x-6 md:flex">
				<a href="#sobre" class="text-[#a7a7a7] hover:text-blue-600" aria-label="Sobre Mim"
					>Sobre Mim</a
				>
				<a href="#resumo" class="text-[#a7a7a7] hover:text-blue-600" aria-label="Resumo">Resumo</a>
				<a href="#contato" class="text-[#a7a7a7] hover:text-blue-600" aria-label="Contato"
					>Contato</a
				>

				<!-- Ícones sociais Desktop -->
				<div class="ml-4 flex items-center space-x-4">
					<a
						href="https://www.instagram.com/ricardtds/"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="Instagram"
					>
						<svg class="h-5 w-5 text-[#E1306C]" fill="currentColor" viewBox="0 0 24 24">
							<path
								d="M7.75 2h8.5A5.76 5.76 0 0122 7.75v8.5A5.76 5.76 0 0116.25 22h-8.5A5.76 5.76 0 012 16.25v-8.5A5.76 5.76 0 017.75 2zm0 1.5A4.26 4.26 0 003.5 7.75v8.5A4.26 4.26 0 007.75 20.5h8.5a4.26 4.26 0 004.25-4.25v-8.5A4.26 4.26 0 0016.25 3.5h-8.5zM12 7a5 5 0 110 10 5 5 0 010-10zm0 1.5a3.5 3.5 0 100 7 3.5 3.5 0 000-7zm4.75-.88a1.12 1.12 0 110 2.25 1.12 1.12 0 010-2.25z"
							/>
						</svg>
					</a>
					<a
						href="https://github.com/Ricardtds"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="GitHub"
					>
						<svg class="h-5 w-5 text-white" fill="currentColor" viewBox="0 0 24 24">
							<path
								d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.11.82-.26.82-.577v-2.234c-3.338.724-4.033-1.416-4.033-1.416-.546-1.385-1.333-1.754-1.333-1.754-1.09-.744.082-.729.082-.729 1.205.084 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.997.108-.774.418-1.305.762-1.605-2.665-.3-5.467-1.332-5.467-5.933 0-1.31.468-2.382 1.235-3.222-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 016 0c2.292-1.552 3.3-1.23 3.3-1.23.653 1.653.241 2.873.118 3.176.77.84 1.234 1.912 1.234 3.222 0 4.61-2.807 5.63-5.479 5.923.43.37.823 1.102.823 2.222v3.293c0 .32.218.694.825.576C20.565 21.796 24 17.3 24 12c0-6.63-5.373-12-12-12z"
							/>
						</svg>
					</a>
					<a
						href="https://www.linkedin.com/in/ricardtds/"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="LinkedIn"
					>
						<svg
							class="h-5 w-5 text-[#0A66C2]"
							fill="currentColor"
							xmlns="http://www.w3.org/2000/svg"
							viewBox="0 0 640 640"
							><!--!Font Awesome Free v7.0.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2025 Fonticons, Inc.--><path
								d="M512 96L127.9 96C110.3 96 96 110.5 96 128.3L96 511.7C96 529.5 110.3 544 127.9 544L512 544C529.6 544 544 529.5 544 511.7L544 128.3C544 110.5 529.6 96 512 96zM231.4 480L165 480L165 266.2L231.5 266.2L231.5 480L231.4 480zM198.2 160C219.5 160 236.7 177.2 236.7 198.5C236.7 219.8 219.5 237 198.2 237C176.9 237 159.7 219.8 159.7 198.5C159.7 177.2 176.9 160 198.2 160zM480.3 480L413.9 480L413.9 376C413.9 351.2 413.4 319.3 379.4 319.3C344.8 319.3 339.5 346.3 339.5 374.2L339.5 480L273.1 480L273.1 266.2L336.8 266.2L336.8 295.4L337.7 295.4C346.6 278.6 368.3 260.9 400.6 260.9C467.8 260.9 480.3 305.2 480.3 362.8L480.3 480z"
							/></svg
						>
					</a>
				</div>
			</nav>

			<!-- Botão Mobile -->
			<div class="flex items-center md:hidden">
				<button
					class="text-[#a7a7a7] hover:text-blue-600 focus:outline-none"
					on:click={() => (menuOpen = !menuOpen)}
					aria-label={menuOpen ? 'Fechar menu' : 'Abrir menu'}
				>
					{#if menuOpen}
						<p class="animate-bounce text-[#F9C756]">✖</p>
					{:else}
						<p class="text-[#F9C756]">☰</p>
					{/if}
				</button>
			</div>
		</div>
	</div>

	<!-- Menu Mobile -->
	{#if menuOpen}
		<nav class="flex flex-col gap-2 px-4 py-2 shadow-md md:hidden" transition:fade>
			<a href="#sobre" class="block text-white hover:text-blue-600" aria-label="Sobre Mim"
				>Sobre Mim</a
			>
			<a href="#resumo" class="block text-white hover:text-blue-600" aria-label="Resumo">Resumo</a>
			<a href="#contato" class="block text-white hover:text-blue-600" aria-label="Contato"
				>Contato</a
			>

			<div class="mt-2 flex justify-start gap-4">
				<a
					href="https://www.instagram.com/ricardtds/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="Instagram"
				>
					<svg class="h-6 w-6 text-[#E1306C]" fill="currentColor" viewBox="0 0 24 24"
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
				>
					<svg class="h-6 w-6 text-white" fill="currentColor" viewBox="0 0 24 24"
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
				>
					<svg
						class="h-6 w-6 text-[#0A66C2]"
						fill="currentColor"
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 640 640"
						><!--!Font Awesome Free v7.0.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2025 Fonticons, Inc.--><path
							d="M512 96L127.9 96C110.3 96 96 110.5 96 128.3L96 511.7C96 529.5 110.3 544 127.9 544L512 544C529.6 544 544 529.5 544 511.7L544 128.3C544 110.5 529.6 96 512 96zM231.4 480L165 480L165 266.2L231.5 266.2L231.5 480L231.4 480zM198.2 160C219.5 160 236.7 177.2 236.7 198.5C236.7 219.8 219.5 237 198.2 237C176.9 237 159.7 219.8 159.7 198.5C159.7 177.2 176.9 160 198.2 160zM480.3 480L413.9 480L413.9 376C413.9 351.2 413.4 319.3 379.4 319.3C344.8 319.3 339.5 346.3 339.5 374.2L339.5 480L273.1 480L273.1 266.2L336.8 266.2L336.8 295.4L337.7 295.4C346.6 278.6 368.3 260.9 400.6 260.9C467.8 260.9 480.3 305.2 480.3 362.8L480.3 480z"
						/></svg
					>
				</a>
			</div>
		</nav>
	{/if}
</header>
