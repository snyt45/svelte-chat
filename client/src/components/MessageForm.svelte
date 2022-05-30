<script lang="ts">
  import { createEventDispatcher } from 'svelte';

  export let message;

  const dispatch = createEventDispatcher();

  const handleSubmit = () => {
    dispatch('submit');
  };
</script>

<input bind:value="{message}" type="text" placeholder="Message to send">
<button on:click="{handleSubmit}">submit</button>

<style>
  input[type="text"] {
    flex: 1 1 auto;
  }
</style>
