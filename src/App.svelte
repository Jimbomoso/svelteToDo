<script>
  import Container from '../components/Container.svelte';
  let todos = [];
  function addTodo(){
    todos = [...todos, ''];
  }
  function removeSelf(){

  }
</script>

<Container>
  <h1> Todos: </h1>
  {#each todos as todo, index}
    <input bind:value={todos[index]}>
  {/each}

  <button on:click={addTodo}>Add</button>
</Container>
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
