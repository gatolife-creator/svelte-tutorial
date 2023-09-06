<script>
  import ToDoInputForm from "./ToDoInputForm.svelte";
  import ToDoList from "./ToDoList.svelte";

  let nameEntered = false;

  let lastName = "田中";
  let firstName = "太郎";

  $: fullName = lastName + " " + firstName;
</script>

<main>
  {#if nameEntered}
    <h1>タスクリストアプリケーションへようこそ、{fullName}さん。</h1>
    <ToDoInputForm userName={fullName} />
    <ToDoList />
  {:else}
    <h1>タスクリストアプリケーションへようこそ</h1>
    <h3>名前を入力してください。</h3>
    <div>
      <input type="text" placeholder="姓" required />
    </div>
    <div>
      <input type="text" placeholder="名" required />
    </div>
  {/if}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 450px;
    margin: 0 auto;
  }
</style>
