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

const todo = [
	"First Meeting with Mircea",
	"If all we figure out in the first meeting is: we know what we're making, we're good!",
	"Come up with a meeting agenda",
	"PLAN A: An extension that redirects you to our microlearning website, then back to the extension",
	"Come up with list of ideas / Brainstorm app ideas",
	"Read both papers provided by Mircea",
	"Introduction to Svelte Scrimba (John)",
	"Google Extensions vid (John)",
	"Svelte Videos (John)",
	"Begin to familiarize ourselves with Svelte (Take notes while learning)",
	"Compile the notes somewhere!",
	"(Microlearning)",
	"Take a look at Codecademy’s Quizzes?",
	"Take a look at SoloLearn?",
	"Take a look at Duolingo?",
	"Look for other microlearning apps?",
	"Look up some stuff on microlearning?",
	"Start making a website?",
]

const quotes = [
	"Based on these different outcomes, future implementations of the extension may consider different, specialized versions which cater to different types of users. Currently, Aiki is designed as an ultra-simple one-fits-all solution, put specializations are worth exploring: for instance design with a focus on promoting awareness and/or reflection a focus on distracting from procrastination behavior, or a focus on maximizing for engagement with the learning tasks.",
	"When inquiring about this further in this and other participants’ post-study interviews, we discussed a design goal of designing the extension / learning environment to provide positive feedback in order to create positive associations with the microlearning tasks.",
]

let name = getCookie()
const home = () => ({page: Introduction, props: {name: name, clearCookie: clearCookie, todo: todo, quotes: quotes}})

let options = [
	{name: "Component", page: Component},
	{name: "John", page: John},
],
selected = home()

</script>


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


