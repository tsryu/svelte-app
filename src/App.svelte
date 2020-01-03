<script>
  import PageTemplate from "~/components/PageTemplate.svelte";
  import logo from "~/images/svelte-logo-horizontal.svg";
  import TodoInput from "~/components/TodoInput.svelte";
  import TodoList from "~/components/TodoList.svelte";
  let title = `TODO LIST`;
  let todoValue = ``; // initial state

  let handleKeyup = e => {
    todoValue = e.target.value; // keyup 이벤트 발생시 todoValue 값을 업데이트
  };
   let todos = [
    {
      id: 0,
      content: `첫 번째 할일`,
      done: false
    },
    {
      id: 1,
      content: `두 번째 할일`,
      done: true
    },
    {
      id: 2,
      content: `세 번째 할일`,
      done: false
    }
  ];
</script>

<style lang="scss" src="./styles/global.scss"></style>

<PageTemplate {logo} {title}>
  <TodoInput {todoValue} {handleKeyup}/>
  <TodoList {todos} />
</PageTemplate>