<script>
  import Container from '../components/Container.svelte';
  let todos = [];
  function addTodo(){
    todos = [...todos, ''];
  }
  function removeSelf(index){
    todos = [...todos.slice(0, index), ...todos.slice(index+1)];
  }
</script>

<Container>
  <main>
    <h1> Todos: </h1>
    {#each todos as todo, index}
      <input bind:value={todos[index]}>
      <button on:click={()=>removeSelf(index)}> X</button>
      <br>
    {/each}

    <button on:click={addTodo}>Add</button>
  </main>
</Container>

<style>

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
  }
</style>
