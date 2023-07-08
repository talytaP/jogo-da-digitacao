<script>
  export let bg;
  export let label;
  export let handleClick;
</script>

<button style={`background-color: ${bg}`} on:click={handleClick}>{label}</button>


<style>
  button {
    color: #000000;
    padding: 0.75em 2em;
    border-radius: 8px;
    font-weight: 600;
    transition: 200ms;
    cursor: pointer;
    border: none;
  }
</style>