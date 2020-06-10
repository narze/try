<script>
  import Face from "./Face.svelte"
  import Container from "./Container.svelte";
	export let name;

  let say = false;

  setTimeout(() => {
    say = true;
  }, 1000)
</script>

<main>
  <Container>

    {#if say}
      <h1>Hello {name}!</h1>
      <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

      <Face />
      <Face size="4" index="1" />
      <Face size="6" index="2" />
    {:else}
      ...
    {/if}
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
