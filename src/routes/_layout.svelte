<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<style>
  main {
    position: relative;
    max-width: 56em;
    background-color: white;
    padding: 2em;
    margin: 0 auto;
    box-sizing: border-box;
    display: grid;
    grid-template-columns: [left] 20% [main] auto [right] 10%;
  }

  .left {
    grid-area: "left";
  }
</style>

<Nav {segment} />

<main>
  <slot name="left" class="left" />
  <slot name="main" class="main" />
  <slot name="right" class="right" />
</main>
