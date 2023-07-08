<script>
	import { onMount } from 'svelte';
	import Link from '../../components/Link.svelte';

  // onMount(() => {
  //   const html = document.getElementsByTagName('html')[0];
  //   html.style.backgroundImage = 'https://br.freepik.com/fotos-vetores-gratis/papel-velho';
  // })
</script>

<main>
	<h1>Instruções</h1>


	<div class="instrucoes">
		<h2>O jogo tem as seguintes regras:</h2>

		<ul>
			<li>
				Você terá 60 segundos para digitar a palavra na tela.
			</li>
      <li>
        A cada erro perde-se  5 segundos, e precisará clicar no campo de
				digitação novamente.
      </li>
			<li>
				Existem 5 níveis. A cada 5 acertos você passa para o próximo nível onde as palavras são
				maiores e mais difíceis.
			</li>
			<li>Atenção aos acentos.</li>
			<li>No último nível você jogará com frases, atenção aos espaços e vírgulas.</li>
		</ul>
		<br />
		<h3>Boa sorte!</h3>
	</div>

  <br>

	<div class="criadoras">
    <h2 class="subtitulo">Criadoras:</h2>
    <div><strong>Isabelly Arruda</strong></div>
    <div><strong>Maria Letícia</strong></div>
    <div><strong>Talyta Paz</strong></div>
  </div>
  <br>
  <Link href="/" label="Voltar" />
</main>

<style>
	main {
		height: 100vh;
		padding: 1em;
		background-image: url('https://img.freepik.com/fotos-gratis/papel-de-papiro-castanho_53876-14519.jpg');
		background-size: cover;
	}
	
  .instrucoes {
		margin: 1em;
		margin-top: 2em;
		padding: 1em;
		
	}
	
  .instrucoes h3 {
		text-align: center;
	}
	li {
		margin: 1em;
	}
  
  .criadoras {
    margin: 1em;
		margin-top: 2em;
		padding: 0.75em 1em;
		background-color: #00000016;
		border-radius: 1em;
    width: min-content;
  }
  
  .subtitulo {
    margin: 0;
    margin-bottom: 0.5em;
    color: rgb(145, 32, 32);
  }

  h1 {
    text-align: center;
  }
</style>
