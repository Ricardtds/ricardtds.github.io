<script>
	export let endpoint = ''; // URL do Formspree

	let nome = '';
	let email = '';
	let assunto = '';
	let mensagem = '';
	let status = '';

	async function handleSubmit(e) {
		e.preventDefault();

		const data = {
			name: nome,
			email,
			subject: assunto,
			message: mensagem
		};

		try {
			const res = await fetch(endpoint, {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json',
					Accept: 'application/json'
				},
				body: JSON.stringify(data)
			});

			const result = await res.json();

			if (result.ok || res.status === 200) {
				status = 'Mensagem enviada com sucesso!';
				nome = '';
				email = '';
				assunto = '';
				mensagem = '';
			} else {
				status = 'Erro ao enviar a mensagem.';
			}
		} catch (err) {
			status = 'Erro ao enviar a mensagem.';
			console.error(err);
		}
	}
</script>

<form class="flex flex-col gap-3" on:submit={handleSubmit}>
	<input
		type="text"
		placeholder="Seu Nome Completo"
		bind:value={nome}
		class="w-full rounded-md bg-[#D4D4D4]/30 px-4 py-2 font-bold text-white placeholder-[#A7A7A7] focus:ring focus:ring-blue-200 focus:outline-none"
		required
	/>
	<input
		type="text"
		placeholder="Seu Assunto"
		bind:value={assunto}
		class="w-full rounded-md bg-[#D4D4D4]/30 px-4 py-2 font-bold text-white placeholder-[#A7A7A7] focus:ring focus:ring-blue-200 focus:outline-none"
		required
	/>
	<input
		type="email"
		placeholder="Seu Email"
		bind:value={email}
		class="w-full rounded-md bg-[#D4D4D4]/30 px-4 py-2 font-bold text-white placeholder-[#A7A7A7] focus:ring focus:ring-blue-200 focus:outline-none"
		required
	/>
	<textarea
		placeholder="Sua Mensagem"
		rows="5"
		bind:value={mensagem}
		class="w-full rounded-md bg-[#D4D4D4]/30 px-4 py-2 font-bold text-white placeholder-[#A7A7A7] focus:ring focus:ring-blue-200 focus:outline-none"
		required
	></textarea>
	<div class="flex justify-start">
		<button
			type="submit"
			class="rounded-full bg-[#F9C756] px-6 py-2 font-bold text-white transition hover:brightness-105"
		>
			Enviar
		</button>
	</div>
</form>

{#if status}
	<p class="mt-2 text-white">{status}</p>
{/if}
