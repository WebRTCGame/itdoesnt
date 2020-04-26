<script>
  export let name;
  import Header from "../common/header.svelte";
  import Zach from "../common/button.svelte";
  let test = "assy";
  import Nested from "./Nested.svelte";
  import Info from "./Info.svelte";

  const pkg = {
    name: "butt",
    version: 9,
    speed: "crotch",
    website: "https://face.ugly"
  };
  let user = { loggedIn: false };

  function toggle() {
    user.loggedIn = !user.loggedIn;
  }
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 140px;
    margin: 0 auto;
  }
  p {
    color: purple;
    font-family: "Comic Sans MS", cursive;
    font-size: 2em;
  }
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .box {
    background: purple;
  }
</style>

<main>
  <Header />
  <h1>Helloddfasd {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <h1>{test}!</h1>
  <Zach />

</main>
<Nested />
<Info {...pkg} />
{#if user.loggedIn}
  <button on:click={toggle}>Log out</button>
{/if}

{#if !user.loggedIn}
  <button on:click={toggle}>Log in</button>
{/if}
