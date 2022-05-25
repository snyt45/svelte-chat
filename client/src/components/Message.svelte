<script lang="ts">
  export let currentUserId: string;
  export let userId: string;
  export let message: string;
</script>

<div class:mine="{currentUserId === userId}">
  <p class="message">{message}</p>
</div>

<style>
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
</style>
