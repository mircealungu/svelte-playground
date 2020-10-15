<script>
    let array = ["TRex","Stegosaurus","Brachiosaurus","Triceratops","Pteranodon","Iguanadon","Eleonora"];
</script>

<style>

</style>

<h1>05: Logic</h1>

<ul>
    {#each array as dino}
    {#if dino.length > 5}
        <li>{dino} is the longest dino</li>
    {:else}
        <li>{dino} is the shortest dino</li>
    {/if}
    {/each}
</ul>