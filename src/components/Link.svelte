<script>
  export let label;
  export let href;
</script>

<a class="link-btn" {href}>{label}</a>

<style>
  a.link-btn {
		text-decoration: none;
		padding: 12px;
		background-color: #730707c2;
		width: 8em;
		text-align: center;
		border-radius: 8px;
		color: aliceblue;
    transition: 200ms;
	}

	a.link-btn:hover {
		background-color: #730707df;
    transform: scale(1.025);
    box-shadow: 0px 4px 12px -2px #bbb;
	}
</style>