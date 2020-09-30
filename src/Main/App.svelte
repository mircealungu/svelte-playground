<script>
import Component from "../Basics/Component.svelte";
import John from "../Basics/John.svelte";
import Introduction from "./Introduction.svelte";



function getCookie() {
	return document.cookie
	
}
function setCookie(username) {
	document.cookie = username
	location.reload()
}

const clearCookie = () => {
	document.cookie = ""
	location.reload()
}

let name = getCookie()
const home = () => ({page: Introduction, props: {name: name, clearCookie: clearCookie}})

let options = [
	{name: "Component", page: Component},
	{name: "John", page: John}
],
selected = home()


</script>

<style>
	.sized {
		height: 100%;
		widows: 100%;
	}
	.intro {
		display: flex;
		flex-direction: column;
		height: 100%;
		widows: 100%;
		align-items: center;
		justify-content: center;
	}



	.intro input, button {
		justify-self: center;
		height: 10%;
		width: 20%;
		text-align: center;
	}

	
</style>





<div class="sized">
{#if getCookie() === (undefined || "")}
<div class="intro">
	<p>I'm sorry, do I know you?</p>
	<input type="text" bind:value={name}>
	<button on:click={() => setCookie(name)} >Lets go</button>
</div>
	{:else}
<div class="main">
	<button on:click={() => {selected = home()}}>Home</button>
	{#each options as option}
		<button on:click={() => {selected = option}} >{option.name}</button>
	{/each}

<svelte:component this={selected.page} {...selected.props}/>
</div>
{/if}
</div>

