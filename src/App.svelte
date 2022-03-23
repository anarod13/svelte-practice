<script>
	let thingsToDo = []
	let value;
function addThing(){
	thingsToDo = [...thingsToDo,value]
	value=''
	console.log(thingsToDo)
}
function eraseToDo(i){
	thingsToDo = [...thingsToDo.splice(i,1)]
	


}

</script>

<main>
	<h1>This is your To Do List</h1>
	<h2>Simply write what you need and we'll add it to the list</h2>
	<input bind:value={value} on:change={addThing}>
<ul>This is what you're up to today:
		{#each thingsToDo as thing}
	<li id={thing}>{thing} <button>x</button></li>
	<!-- Al agregar el onclick al botón llama automaticamente la fn -->
	{/each}
</ul>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>