<script>
	import ErroDigito from '../../components/ErroDigito.svelte';
	import FimDeJogo from '../../components/FimDeJogo.svelte';
	import { checarLetras } from '../../gameFunctions';
	import { niveis } from '../../niveis';

	let nivel = 1;
	let subnivel = 5;
	let pontos = 0;

	$: palavra = niveis[nivel - 1][subnivel - 1];

	let digitacao = '';

	let cores = [];

	let vitoria = false;
	let fimDeJogo = false;

	let errouDigito = false;

	let timer = 60;
	let timerId = setInterval(function () {
		if (timer > 0) {
			timer--;
		} else {
			clearInterval(timerId);
			fimDeJogo = true;
		}
	}, 1000);

	function checarDigitacao(palavra, digitacao) {
		for (let i in digitacao) {
			if (checarLetras(palavra[i], digitacao[i])) {
				cores[i] = true;
			} else {
				return erroDigitacao();
			}
		}

		if (palavra.length === digitacao.length) {
			return sucessoSubNivel();
		}
	}

	function sucessoSubNivel() {
		pontos += timer + palavra.length;
		timer += 10 - nivel;

		setTimeout(function () {
			if (subnivel >= niveis[nivel - 1].length) {
				if (niveis[nivel]) {
					subnivel = 1;
					nivel++;
				} else {
					vitoria = true;
					clearInterval(timerId);
					alert('VOCÊ ZEROU!!!');
				}
			} else {
				subnivel++;
			}

			digitacao = '';
			cores = [];
		}, 1000);
	}

	function erroDigitacao() {
		digitacao = '';
		cores = [];
		errouDigito = true;
		timer -= 5;

		setTimeout(function () {
			errouDigito = false;
		}, 1000);
	}

	$: checarDigitacao(palavra, digitacao);
</script>

<main class="container">
	<div>
		<div class="content">
			<div class="letras-container">
				{#each palavra as letra, i}
					<div
						class={`letra ${
							cores[i] ? 'letra-success' : errouDigito ? 'letra-error' : 'letra-neutral'
						}`}
					>
						{letra}
					</div>
				{/each}
			</div>
			<br />
			<div>
				<strong>Pontuação: {pontos}</strong>
			</div>
			<div>
				<strong>nivel: {subnivel}/{nivel}</strong>
			</div>
			{#if errouDigito}
				<ErroDigito />
			{/if}
			{#if fimDeJogo}
				<FimDeJogo />
			{/if}
			<h2>{timer} segundos</h2>

			<input
				type="text"
				class={errouDigito && 'input-error'}
				bind:value={digitacao}
				disabled={errouDigito || vitoria}
			/>
		</div>
	</div>
</main>

<style>
	main.container {
		height: 100vh;
		width: 100vw;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		background-image: url('https://img.freepik.com/fotos-premium/fundo-de-textura-de-papel-retro-vintage-velho-grunge_47840-948.jpg');
	}

	div.content {
		width: 90vw;
		display: flex;
		flex-direction: column;
	}

	div.letras-container {
		max-width: 75%;
		flex-wrap: wrap;
		display: flex;
		justify-content: center;
		gap: 8px;
		margin: auto;
		margin-bottom: 2em;
	}

	div.letra {
		font-size: 38px;
		padding: 0.5em;
		border-radius: 8px;
		transition: 200ms;
	}

	.letra-success {
		background-color: green;
		color: white;
	}

	.letra-error {
		background-color: red;
		color: white;
	}

	.letra-neutral {
		background-color: #00000016;
	}

	input {
		width: 75%;
		margin: auto;
		padding: 0.5em;
		font-size: 30px;
		border: none;
		border-bottom: 2px solid black;
		text-align: center;
		background: #00000016;
		transition: 200ms;
	}

	.input-error {
		border-color: red;
	}
</style>
