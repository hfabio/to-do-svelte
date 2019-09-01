<script>
  import Todo from "../components/Todo.svelte";
  export let name;
</script>

<style>
  .container {
    margin: 0 auto;
    width: 480px;
  }
</style>

<main class="container">
  <Todo />
</main>
