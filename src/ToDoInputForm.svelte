<script>
  import { onMount } from "svelte";
  import { toDoItems } from "./store";

  export let userName;
  let newItem = "";
  let newItemInputForm = null;

  onMount(() => {
    newItemInputForm.focus();
  });

  function addToList() {
    $toDoItems = [...$toDoItems, { text: newItem, status: false }];
    newItem = "";
  }
</script>

<input
  bind:value={newItem}
  bind:this={newItemInputForm}
  type="text"
  placeholder="新しく追加するタスク"
/>
<button on:click={addToList}>追加</button>

<h3>{userName}のタスクリスト:</h3>
