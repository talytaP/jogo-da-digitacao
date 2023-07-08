<script>
	export let contador;
</script>

<div class="container">
	<div class="content">{contador}</div>
</div>

<style>
	div.container {
		height: 100vh;
		width: 100vw;
		position: fixed;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #000000dd;
	}

	div.content {
		color: white;
		font-size: 42px;
		text-align: center;
	}
</style>
