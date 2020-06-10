<script>
  import Face from "./Face.svelte"
  import Container from "./Container.svelte";
  import Buttons from "./Buttons.svelte";
	export let name;

  let say = false;
</script>

<main>
  <Container>
    <Buttons on:click={(e) => { say = e.detail }}></Buttons>

    {#if say}
      <h1>Hello {name}!</h1>
      <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
    {:else}
      ...
    {/if}

    {#each [0, 1, 2, 3] as index}
      <Face {index} size={(index + 1) * 3} />
    {/each}
  </Container>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

  :global(*) {
    box-sizing: border-box;
  }

  :global(body, html) {
    margin: 0;
    height: 100vh;
    overflow: hidden;
  }
</style>
