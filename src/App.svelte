<script>
  import PageTemplate from "~/components/PageTemplate.svelte";
  import logo from "~/images/svelte-logo-horizontal.svg";
  import TodoInput from "~/components/TodoInput.svelte";
  import TodoList from "~/components/TodoList.svelte";
  let title = `TODO LIST`;

  let handleInsert = () => {
    if (todoValue) {
      const newTodo = {
        id: ++todoId,
        content: todoValue,
        done: false
      };

      todos[todos.length] = newTodo;
      todoValue = ``;
    } else {
      alert(`내용을 입력해 주세요.`);
    }
  };
  let handleCheck = (id, done) => {
    const index = todos.findIndex(todo => todo.id === id);

    todos[index][`done`] = !done;
  };
</script>

<style lang="scss" src="./styles/global.scss">

</style>

<PageTemplate {logo} {title}>
  <TodoInput />
  <TodoList />
</PageTemplate>
