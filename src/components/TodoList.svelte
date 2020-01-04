<script>
  import TodoItem from "~/components/TodoItem.svelte";

  export let todos;
  export let handleCheck;
  export let handleRemove;
  export let handleModify;
</script>

<style lang="scss">
  ul {
    padding: 0.9rem 0 1.2rem;
  }
</style>

<ul>
  <!-- #반복문 스타일 1
    {#each todos as todo}
    <TodoItem {todo} />
  {/each} -->
  <!-- #반복문 스타일 2
    {#each items as item, i}
    <li>{i + 1}: {item.name}</li>
  {/each} -->
  {#each todos as todo}
     <TodoItem {todo} {handleCheck} {handleModify} {handleRemove} />
  {:else}
    <p>No tasks today!</p>
  {/each}
</ul>