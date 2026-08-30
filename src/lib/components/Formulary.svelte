<script lang="ts">
	let { endpoint = '' } = $props<{ endpoint?: string }>();

	let nome = $state('');
	let email = $state('');
	let assunto = $state('');
	let mensagem = $state('');
	let status = $state('');
	let sending = $state(false);

	async function handleSubmit(event: SubmitEvent) {
		event.preventDefault();
		sending = true;
		status = '';

		try {
			const response = await fetch(endpoint, {
				method: 'POST',
				headers: { 'Content-Type': 'application/json', Accept: 'application/json' },
				body: JSON.stringify({ name: nome, email, subject: assunto, message: mensagem })
			});

			if (!response.ok) throw new Error('Falha ao enviar mensagem');

			status = 'Mensagem enviada. Obrigado pelo contato!';
			nome = '';
			email = '';
			assunto = '';
			mensagem = '';
		} catch (error) {
			status = 'Não foi possível enviar agora. Tente novamente em instantes.';
			console.error(error);
		} finally {
			sending = false;
		}
	}

	const fieldClass =
		'w-full border border-black/10 bg-[#f7f7f4] px-4 py-3 text-sm text-[#171717] placeholder:text-black/30 transition focus:border-[#15958d]/60 focus:ring-2 focus:ring-[#15958d]/10 focus:outline-none';
</script>

<form class="grid gap-4" onsubmit={handleSubmit}>
	<div class="grid gap-4 sm:grid-cols-2">
		<label class="grid gap-2 text-[0.65rem] font-bold tracking-[0.1em] text-black/50 uppercase">
			Nome
			<input
				class={fieldClass}
				type="text"
				autocomplete="name"
				placeholder="Como posso chamar você?"
				bind:value={nome}
				required
			/>
		</label>
		<label class="grid gap-2 text-[0.65rem] font-bold tracking-[0.1em] text-black/50 uppercase">
			E-mail
			<input
				class={fieldClass}
				type="email"
				autocomplete="email"
				placeholder="voce@exemplo.com"
				bind:value={email}
				required
			/>
		</label>
	</div>
	<label class="grid gap-2 text-[0.65rem] font-bold tracking-[0.1em] text-black/50 uppercase">
		Assunto
		<input
			class={fieldClass}
			type="text"
			placeholder="Projeto, oportunidade ou conversa técnica"
			bind:value={assunto}
			required
		/>
	</label>
	<label class="grid gap-2 text-[0.65rem] font-bold tracking-[0.1em] text-black/50 uppercase">
		Mensagem
		<textarea
			class={fieldClass}
			rows="5"
			placeholder="Conte um pouco sobre o contexto."
			bind:value={mensagem}
			required
		></textarea>
	</label>
	<div class="flex flex-col gap-3 sm:flex-row sm:items-center sm:justify-between">
		<button
			type="submit"
			disabled={sending}
			class="inline-flex items-center justify-center bg-[#171717] px-6 py-3 text-sm font-bold text-white transition hover:bg-[#15958d] disabled:cursor-wait disabled:opacity-60"
		>
			{sending ? 'Enviando…' : 'Enviar mensagem'}
		</button>
		<p class="text-sm text-black/50" aria-live="polite">{status}</p>
	</div>
</form>
