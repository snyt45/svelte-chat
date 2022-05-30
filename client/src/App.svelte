<script lang="ts">
  import Message from './components/Message.svelte';
  import MessageForm from './components/MessageForm.svelte';
  import { getUserId } from './lib/getUserId';
  let messages: { userId: string; message: string }[] = []
  let testDate = [
    { userId: "test0001", message: "test1"},
    { userId: "test0002", message: "test2"},
    { userId: "test0001", message: "test3"},
    { userId: "test0002", message: "test4"},
    { userId: "test0001", message: "test5"}
  ]
  const currentUserId = getUserId()
  messages = testDate
</script>

<main>
  <div class="wrapper">
    <h1>Svelte Chat</h1>
    <div class="board">
      {#each messages as {userId, message}}
        <Message currentUserId="{currentUserId}" userId="{userId}" message="{message}" />
      {/each}
    </div>
    <div class="message-form-wrapper">
      <MessageForm />
    </div>
  </div>
</main>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
    height: 100vh;
    max-width: 400px;
    margin: 0 auto;
  }
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    text-align: center;
    font-size: 2em;
    font-weight: 400;
  }
  .board {
    padding: 1em;
    background-color: #ebeeee;
    height: 80vh;
    overflow: scroll;
    scroll-behavior: smooth;
  }
  .message-form-wrapper {
    display: flex;
  }
</style>
