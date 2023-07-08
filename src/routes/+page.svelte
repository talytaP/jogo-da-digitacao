<script>
	import Link from '../components/Link.svelte';
</script>

<main>
	<div class="container">
		<div class="principal-menu">
			<h1>Jogo da Digitação</h1>
			<br />
			<Link href="/jogo" label="Iniciar" />
			<Link href="/instrucoes" label="Instruções" />
		</div>
	</div>
</main>

<style>
	
	div.container {
		height: 100vh;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		background-image: url("https://img.freepik.com/fotos-premium/fundo-de-textura-de-papel-retro-vintage-velho-grunge_47840-948.jpg");
	}

	div.principal-menu {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 8px;
		padding: 1em;
	}

	h1 {
		padding: 0;
		margin: 0;
	}
</style>
