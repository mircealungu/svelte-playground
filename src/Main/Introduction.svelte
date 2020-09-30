<script>
    export let name, clearCookie, todo, quotes
</script>

<h1>Hello {name}!</h1>

<h3>To Do List</h3>
    <ul>
    {#each todo as i}
    <li>{i}</li>
    {/each}
    </ul>
<br>
<h3>Useful Quotes</h3>
    <ul>
    {#each quotes as j}
    <li><span style="font-weight: bold;">Source: {j.source}.</span> {j.text}</li>
    {/each}
    </ul>
<!--<button on:click={() => clearCookie()}>Clear Cookie</button> -->