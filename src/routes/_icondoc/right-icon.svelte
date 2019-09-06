<script>
  export let selectedIcon;
  import { Icon } from "ant-svelte";
</script>

<style>
  div {
    position: fixed;
    top: 1em;
  }
</style>

{#if selectedIcon}
  <div>
    <Icon size="8em" type={selectedIcon.name} theme={selectedIcon.theme} />
    <pre>{selectedIcon.html}</pre>
    <p>Copied to clipboard</p>
  </div>
{/if}
