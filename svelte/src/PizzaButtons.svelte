<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let buttons = [];
</script>

{#each buttons as button}
  <button on:click={() => dispatch("click", { value: button.value })}>
    {button.text}
  </button>
{/each}

<style>
    button {
        font-family: 'Nunito', sans-serif;
        display: block;
        font-size: 1.2rem;
        margin: 10px auto;
        transition: 1s;
        padding: 0.7em 1em;
        cursor: pointer;
        border-radius: 50px;
        background-color: #40b3ff;
        color: white;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
	}
</style>
