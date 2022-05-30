<script lang="ts">
  import Message from './components/Message.svelte';
  import MessageForm from './components/MessageForm.svelte';
  import { getUserId } from './lib/getUserId';
  let message: string = ''
  let messages: { userId: string; message: string }[] = []
  const updateMessages = () => {
    messages = [...messages, {userId: currentUserId, message}]
    message = ''
  }
  const currentUserId = getUserId()
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
      <MessageForm bind:message on:submit="{updateMessages}"/>
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
