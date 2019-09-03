<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<style>
  .wrapper {
    display: grid;
    width: 100%;
    height: 250px;
    grid-template-areas:
      "nav  main"
      "nav  foot";
    grid-template-rows: 1fr 30px;
    grid-template-columns: 150px 1fr;
  }
  main {
    position: relative;
    max-width: 56em;
    background-color: white;
    padding-left: 1em;
    box-sizing: border-box;
    border-left: solid 1px #333;
    grid-area: main;
  }
</style>

<div class="wrapper">
  <Nav {segment} />
  <main>
    <slot />
  </main>
</div>
