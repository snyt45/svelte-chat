<script lang="ts">
  let messages: { userId: string; message: string }[] = []
  let testDate = [
    { userId: "test0001", message: "test1"},
    { userId: "test0002", message: "test2"},
    { userId: "test0001", message: "test3"},
    { userId: "test0002", message: "test4"},
    { userId: "test0001", message: "test5"}
  ]
  messages = testDate
</script>

<main>
  <div class="wrapper">
    <h1>Svelte Chat</h1>
    <div class="board">
      <div class="mine">
        <p class="message">ここに文章</p>
      </div>
      <div>
        <p class="message">ここに文章</p>
      </div>
      <div class="mine">
        <p class="message">ここに文章</p>
      </div>
      <div>
        <p class="message">ここに文章</p>
      </div>
    </div>
    <div class="message-form-wrapper">
      <input type="text" placeholder="Message to send">
      <button type="submit">submit</button>
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
  .mine {
    display: flex;
    flex-direction: row-reverse;
  }
  .message {
    border-radius: 10px;
    padding: 10px;
    background-color: #fff;
    display: inline-block;
  }
  .mine .message {
    background-color: #85e249;
  }
  .message-form-wrapper {
    display: flex;
  }
  .message-form-wrapper input[type="text"] {
    flex: 1 1 auto;
  }
</style>
