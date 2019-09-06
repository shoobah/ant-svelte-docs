<script>
  import Main from "./_icondoc/icon-doc-main.svelte";
  import Right from "./_icondoc/right-icon.svelte";

  let selectedIcon;

  const setSelectedIcon = icon => (selectedIcon = icon);
</script>

<style>
  .wrapper {
    display: grid;
    grid-auto-columns: 1fr 5%;
  }
</style>

<div class="wrapper">
  <div style="grid-column-start: 1">
    <Main {setSelectedIcon} />
  </div>
  <div style="grid-column-start: 2;">
    <Right {selectedIcon} />
  </div>
</div>
