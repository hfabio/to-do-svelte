<script>
  import TodoItem from "./TodoItem.svelte";
  import { tasks } from "../store.js";
  let task = "";

  const showDifference = e => {
    console.log(e.target.value);
  };

  const addTask = () => {
    tasks.update(() => [...$tasks, getTask()]);
  };

  const deleteTask = id => {
    tasks.update(() => $tasks.filter((el, index) => index !== id));
  };

  function getTask() {
    let input = document.querySelector(".form__field").value;
    task = "";
    return input;
  }
</script>

<style>
  .form {
    display: flex;
    align-content: center;
    justify-content: space-around;
  }

  .form__field {
    border: 1px solid #dcdcdc;
    border-radius: 50px;
    color: #333333;
    font-family: Arial, sans-serif;
    font-size: 2rem;
    padding: 1rem 2rem;
    margin-right: 0.5rem;
    vertical-align: middle;
  }

  .form__field:focus {
    outline: none;
  }

  .form__button {
    background: #00cc99;
    border: none;
    border-radius: 10px;
    color: #ffffff;
    display: inline-block;
    font-family: Arial, sans-serif;
    padding: 1rem;
  }

  .form__button:hover {
    cursor: pointer;
  }

  .form__button:focus {
    outline: none;
  }
</style>

<form class="form" on:submit|preventDefault={addTask}>
  <input
    bind:value={task}
    type="text"
    class="form__field"
    on:keyup={showDifference} />
  <button class="form__button" type="submit">Add</button>
</form>

<TodoItem list={$tasks} del={deleteTask} />
