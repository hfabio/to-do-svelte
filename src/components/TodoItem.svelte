<script>
  export let list;
  export let del;
</script>

<style>
  ul,
  li {
    margin: 0;
    padding: 0;
  }
  .list__item {
    color: #595959;
    background-color: lightblue;
    font-family: Arial, sans-serif;
    font-style: 1.5rem;
    list-style: none;
    font-size: 1.5rem;
    margin: 0.5rem 0;
    border-radius: 20px;
    padding-left: 10px;

    display: flex;
    align-content: center;
    justify-content: space-between;
  }

  .list__item div {
    display: inline-block;
    margin: auto 0;
  }

  .list__item div button {
    display: inline-block;
    margin: auto;
    background-color: transparent;
    border: 2px solid gray;
    border-radius: 50px;
  }

  .list__item button > img,
  span {
    align-content: center;
    vertical-align: middle;
  }
</style>

<ul class="list">
  {#each list as item, i}
    <li class="list__item">
      <div>
        <span>{item}</span>
      </div>
      <div>
        <button on:click={() => del(i)}>
          <span>Done</span>
          <img src="../img/done.svg" alt="done" width="24px" height="24px" />
        </button>
      </div>
    </li>
  {/each}
</ul>
