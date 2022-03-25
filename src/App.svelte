<script>
	import Button from './Button.svelte' ;
  let thingsToDo = [];
  let value;
  function addThing() {
    thingsToDo = [...thingsToDo, value];
    value = "";

  }

  function eraseToDo(i) {
    thingsToDo.splice(i, 1);
	thingsToDo=[...thingsToDo 	]

  }
</script>

<main>
  <h1>This is your To Do List</h1>
  <h2>Simply write what you need and we'll add it to the list</h2>
  <input bind:value on:change={addThing} />
  <ul>
    This is what you're up to today:
    {#each thingsToDo as thing,i}
      <li id={thing}>{thing} <Button on:click={()=>{eraseToDo(i)}}></Button></li>

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
