<script>
    export let name, clearCookie, todo
</script>

<h1>Hello {name}!</h1>

<h3>To Do List</h3>
    <ul>
    {#each todo as i}
    <li>{i}</li>
    {/each}
    </ul>

<!--<button on:click={() => clearCookie()}>Clear Cookie</button> -->