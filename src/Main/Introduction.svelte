<script>
    export let name, clearCookie
</script>

<h1>Hello {name}!</h1>

<p>This is the introduction page</p><br>

<button on:click={() => clearCookie()}>Clear Cookie</button>