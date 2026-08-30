<script lang="ts">
	import Formulary from '$lib/components/Formulary.svelte';

	const services = [
		{
			index: '01',
			title: 'Software & APIs',
			description:
				'Aplicações, serviços e integrações que transformam necessidades reais em soluções utilizáveis.',
			items: ['Python', 'Svelte', 'Laravel', 'REST APIs']
		},
		{
			index: '02',
			title: 'Automação & dados',
			description:
				'Rotinas e fluxos que reduzem trabalho manual, integram sistemas e organizam informações.',
			items: ['Python', 'PowerShell', 'Bash', 'ETL']
		},
		{
			index: '03',
			title: 'Infraestrutura & redes',
			description:
				'Conhecimento da camada que sustenta o software: Linux, conectividade, serviços e entrega.',
			items: ['Linux', 'Docker', 'MikroTik', 'WireGuard']
		},
		{
			index: '04',
			title: 'Experiência técnica',
			description:
				'Diagnóstico e suporte de computadores, telefonia IP e videomonitoramento no dia a dia.',
			items: ['Hardware', 'Windows', 'VoIP', 'CFTV']
		}
	];
</script>

<svelte:head>
	<title>Ricardo Teixeira — Engenharia de Software e infraestrutura</title>
	<meta
		name="description"
		content="Portfólio de Ricardo Teixeira: engenharia de software, aplicações, APIs, automação com Python, dados, Linux, redes e infraestrutura."
	/>
	<meta property="og:title" content="Ricardo Teixeira — Engenharia de Software" />
	<meta
		property="og:description"
		content="Software construído com uma visão prática de automação, infraestrutura e redes."
	/>
	<meta property="og:type" content="website" />
</svelte:head>

<div class="overflow-hidden bg-[#f7f7f5] text-[#171717]">
	<section id="inicio" class="hero-grid relative overflow-hidden bg-white pt-20">
		<div class="pointer-events-none absolute inset-0" aria-hidden="true">
			<div class="hero-orbit hero-orbit-one"></div>
			<div class="hero-orbit hero-orbit-two"></div>
			<p class="code-fragment code-left">from idea import solution<br />app.build()</p>
			<p class="code-fragment code-right">
				infra.connect()<br />service.deploy()<br />status: ready_
			</p>
		</div>

		<div
			class="section-shell relative grid min-h-[660px] items-center lg:grid-cols-[1fr_1.12fr_1fr]"
		>
			<div
				class="hero-copy hero-copy-left z-10 order-2 pb-10 text-center lg:order-1 lg:pb-0 lg:text-left"
			>
				<p class="section-kicker justify-center lg:justify-start">engenharia de software</p>
				<h1 class="hero-title mt-4">software<span class="text-[#e39b24]">.</span></h1>
				<p class="mx-auto mt-5 max-w-[18rem] text-sm leading-6 text-[#777] lg:mx-0">
					Aplicações, APIs e integrações pensadas para resolver problemas reais com código claro e
					confiável.
				</p>
				<div class="mt-7 flex flex-wrap justify-center gap-2 lg:justify-start">
					<span class="mini-tag">aplicações</span>
					<span class="mini-tag">APIs</span>
					<span class="mini-tag">python</span>
				</div>
			</div>

			<div
				class="portrait-stage relative order-1 flex h-[430px] items-end justify-center self-end lg:order-2 lg:h-[610px]"
			>
				<div class="portrait-glow" aria-hidden="true"></div>
				<enhanced:img
					src="$lib/assets/hero-ricardo.png"
					alt="Retrato de Ricardo Teixeira"
					class="hero-portrait relative z-[2] max-h-full max-w-full object-contain object-bottom"
				/>
				<div class="identity-card">
					<span class="identity-dot"></span>
					<div>
						<strong>Ricardo Teixeira</strong>
						<small>Software + Infraestrutura de TI</small>
					</div>
				</div>
			</div>

			<div class="hero-copy z-10 order-3 pb-14 text-center lg:pb-0 lg:pl-4 lg:text-left">
				<p class="section-kicker justify-center text-[#15958d] lg:justify-start">base técnica</p>
				<h2 class="hero-title mt-4 whitespace-nowrap">&lt;infra&gt;</h2>
				<p class="mx-auto mt-5 max-w-[19rem] text-sm leading-6 text-[#777] lg:mx-0">
					A vivência com Linux, redes, manutenção, VoIP e CFTV amplia minha visão sobre como o
					software funciona no mundo real.
				</p>
				<div class="mt-7 flex flex-wrap justify-center gap-2 lg:justify-start">
					<span class="mini-tag teal">linux</span>
					<span class="mini-tag teal">redes</span>
					<span class="mini-tag teal">hardware</span>
				</div>
			</div>
		</div>
	</section>

	<section id="projetos" class="border-y border-black/[0.07] bg-[#f4f4f1] py-24 sm:py-28">
		<div class="section-shell">
			<div class="section-heading">
				<span></span>
				<p>Alguns trabalhos e projetos</p>
				<span></span>
			</div>

			<div class="mt-12 grid gap-5 lg:grid-cols-2">
				<article class="work-card group">
					<div class="work-visual project-visual bg-[#edf2ef]">
						<enhanced:img
							src="$lib/assets/coletai-dashboard.png"
							alt="Dashboard do sistema Coletaí"
							class="size-full object-contain object-center transition duration-500 group-hover:scale-[1.02]"
						/>
					</div>
					<div class="p-6">
						<p class="card-number">01 / SOFTWARE · INPATICS</p>
						<h3>Coletaí — Inpatics</h3>
						<p>
							Atuação no desenvolvimento do Coletaí, produto da Inpatics para organizar
							solicitações, rotas e a operação de coletas domiciliares.
						</p>
						<div class="project-tags">
							<span>Laravel</span><span>Python</span><span>APIs</span><span>Dados</span>
						</div>
					</div>
				</article>

				<article class="work-card group">
					<div class="work-visual project-visual bg-[#eef3f8]">
						<enhanced:img
							src="$lib/assets/checkplace.png"
							alt="Interface do CheckPlace comparando endereços originais e corrigidos"
							class="size-full object-contain object-center transition duration-500 group-hover:scale-[1.02]"
						/>
					</div>
					<div class="p-6">
						<p class="card-number">02 / BACKEND & DADOS</p>
						<h3>CheckPlace</h3>
						<p>
							Backend em FastAPI e PostgreSQL para corrigir localidades brasileiras, consultando
							serviços de CEP e APIs do Google.
						</p>
						<div class="project-tags">
							<span>FastAPI</span><span>PostgreSQL</span><span>Docker</span><span
								>APIs externas</span
							>
						</div>
					</div>
				</article>

				<article class="work-card group">
					<div class="work-visual project-visual bg-[#f0f2f5]">
						<enhanced:img
							src="$lib/assets/pragabook.png"
							alt="Página inicial do projeto acadêmico PragaBOOK"
							class="size-full object-contain object-center transition duration-500 group-hover:scale-[1.02]"
						/>
					</div>
					<div class="p-6">
						<p class="card-number">03 / PROJETO ACADÊMICO</p>
						<h3>PragaBOOK</h3>
						<p>
							Website desenvolvido em Svelte em um projeto de faculdade para consultar dados da
							AgroPraga e apresentar informações sobre culturas e pragas ao público.
						</p>
						<div class="project-tags">
							<span>Svelte</span><span>AgroPraga</span><span>UI web</span>
						</div>
					</div>
				</article>

				<article class="work-card group">
					<div class="work-visual project-visual overflow-hidden bg-[#dce9ea]">
						<enhanced:img
							src="$lib/assets/tchat.png"
							alt="Interface do aplicativo TChaT"
							class="size-full object-cover object-left-top transition duration-500 group-hover:scale-[1.03]"
						/>
					</div>
					<div class="p-6">
						<p class="card-number">04 / SOFTWARE OPEN SOURCE</p>
						<h3>TChaT — chat multiplataforma</h3>
						<p>
							Aplicação open source para acompanhar múltiplos chats de lives em uma interface única.
						</p>
						<a href="https://github.com/Ricardtds/TChaT" target="_blank" rel="noreferrer"
							>Ver no GitHub ↗</a
						>
						<div class="project-tags">
							<span>Svelte 5</span><span>Tauri</span><span>Rust</span><span>SQLite</span>
						</div>
					</div>
				</article>

				<article class="work-card thermins-card group lg:col-span-2">
					<div class="work-visual project-visual thermins-visual bg-[#0d1016]">
						<enhanced:img
							src="$lib/assets/thermins-dashboard.png"
							alt="Dashboard do Thermins exibindo telemetria de CPU, memória e armazenamento"
							class="size-full object-contain object-center transition duration-500 group-hover:scale-[1.02]"
						/>
					</div>
					<div class="p-6 lg:self-center lg:p-10">
						<p class="card-number">05 / DESKTOP & SISTEMAS</p>
						<h3>Thermins — monitor de recursos</h3>
						<p>
							Aplicação local multiplataforma para acompanhar CPU, memória, discos, rede,
							temperatura, bateria e processos. O backend em Rust coleta a telemetria com sysinfo e
							publica novas amostras para a interface a cada dois segundos.
						</p>
						<p class="project-detail">
							Inclui processos pesquisáveis e um console de diagnóstico seguro, limitado a comandos
							somente de leitura definidos por sistema operacional.
						</p>
						<a href="https://github.com/Ricardtds/Thermins" target="_blank" rel="noreferrer"
							>Ver no GitHub ↗</a
						>
						<div class="project-tags">
							<span>Tauri 2</span><span>Svelte 5</span><span>Rust</span><span>sysinfo</span>
						</div>
					</div>
				</article>
			</div>
		</div>
	</section>

	<section id="atuacao" class="bg-white py-24 sm:py-32">
		<div class="section-shell grid gap-16 lg:grid-cols-[0.72fr_1.28fr]">
			<div>
				<p class="section-kicker">competências</p>
				<h2 class="section-title">Engenharia de software de ponta a ponta.</h2>
				<p class="mt-6 max-w-md text-base leading-7 text-[#686868]">
					Atuo como engenheiro de software na Inpatics, contribuindo para o desenvolvimento do
					Coletaí. Minha experiência como técnico em Alagoinhas acrescenta uma visão concreta sobre
					usuários, sistemas operacionais, hardware e infraestrutura.
				</p>
				<div class="mt-8 flex items-center gap-3 text-sm font-semibold">
					<span class="grid size-9 place-items-center rounded-full bg-[#f3ab39]/15 text-[#c97d08]"
						>⌖</span
					>
					Alagoinhas, Bahia
				</div>
				<div class="mt-8 flex items-center gap-3 text-sm font-semibold">
					<span class="grid size-9 place-items-center rounded-full bg-[#f3ab39]/15 text-[#c97d08]"
						>⌖</span
					>
					Cruz das Almas, Bahia
				</div>
			</div>

			<div class="grid gap-px overflow-hidden border border-black/10 bg-black/10 sm:grid-cols-2">
				{#each services as service (service.index)}
					<article class="service-card">
						<div class="flex items-start justify-between gap-5">
							<h3>{service.title}</h3>
							<span>{service.index}</span>
						</div>
						<p>{service.description}</p>
						<div class="mt-6 flex flex-wrap gap-2">
							{#each service.items as item (item)}
								<small>{item}</small>
							{/each}
						</div>
					</article>
				{/each}
			</div>
		</div>
	</section>

	<section id="sobre" class="bg-[#171717] py-24 text-white sm:py-32">
		<div class="section-shell grid items-center gap-14 lg:grid-cols-[0.82fr_1.18fr]">
			<div class="relative mx-auto w-full max-w-[390px]">
				<div
					class="absolute -top-4 -left-4 size-28 border-t border-l border-[#efaa3f]"
					aria-hidden="true"
				></div>
				<enhanced:img
					src="$lib/assets/me2.png"
					alt="Ricardo Teixeira"
					class="aspect-[4/5] w-full object-cover grayscale"
				/>
				<div class="absolute -right-4 -bottom-5 bg-[#f0aa3d] px-5 py-4 text-[#171717] shadow-xl">
					<p class="font-mono text-[10px] font-bold tracking-[0.16em] uppercase">
						em constante evolução
					</p>
				</div>
			</div>

			<div>
				<p class="section-kicker text-[#4fd0c5]">sobre mim</p>
				<h2 class="section-title text-white">Curiosidade técnica com responsabilidade.</h2>
				<div class="mt-7 max-w-2xl space-y-5 text-base leading-8 text-white/60">
					<p>
						Sou estudante de Engenharia da Computação na UFRB e concentro meus projetos em
						engenharia de software, aplicações, APIs e automação. Gosto de entender tanto o código
						quanto as camadas que o colocam em funcionamento.
					</p>
					<p>
						Minha atuação como técnico — com computadores, redes, Windows/Linux, VoIP e CFTV — é um
						diferencial importante: ela me aproxima dos usuários e dos problemas concretos que o
						software precisa resolver.
					</p>
				</div>
				<div class="mt-9 grid gap-4 border-t border-white/10 pt-8 sm:grid-cols-2">
					<div>
						<p class="text-sm font-semibold">Engenharia da Computação</p>
						<small class="mt-1 block text-xs text-white/40">UFRB · Em andamento</small>
					</div>
					<div>
						<p class="text-sm font-semibold">Ciência e Tecnologia</p>
						<small class="mt-1 block text-xs text-white/40">UFRB · Bacharelado concluído</small>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section id="contato" class="bg-[#f4f4f1] py-24 sm:py-32">
		<div class="section-shell">
			<div
				class="grid overflow-hidden border border-black/10 bg-white shadow-[0_24px_80px_rgba(0,0,0,0.06)] lg:grid-cols-[0.75fr_1.25fr]"
			>
				<div class="relative overflow-hidden bg-[#eaa333] p-8 sm:p-12">
					<p class="section-kicker text-[#171717]">contato</p>
					<h2
						class="mt-5 max-w-sm text-4xl leading-[1.04] font-bold tracking-[-0.045em] sm:text-5xl"
					>
						Tem um problema para resolver?
					</h2>
					<p class="mt-6 max-w-sm text-sm leading-7 text-black/65">
						Para oportunidades, projetos, suporte ou uma boa conversa técnica, mande uma mensagem.
					</p>
					<div class="mt-10 flex gap-3">
						<a
							class="social-link"
							href="https://github.com/Ricardtds"
							target="_blank"
							rel="noreferrer">GitHub ↗</a
						>
						<a
							class="social-link"
							href="https://www.linkedin.com/in/ricardtds/"
							target="_blank"
							rel="noreferrer">LinkedIn ↗</a
						>
					</div>
					<div
						class="absolute -right-16 -bottom-16 size-52 rounded-full border border-black/10"
						aria-hidden="true"
					></div>
				</div>
				<div class="p-8 sm:p-12">
					<Formulary endpoint="https://formspree.io/f/mgvlgdge" />
				</div>
			</div>
		</div>
	</section>
</div>
