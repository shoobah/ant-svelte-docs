<script>
  import { slide } from "svelte/transition";
  import { Icon } from "ant-svelte";

  export let code = "";

  let display = false;
</script>

<style>
  .code-section {
    border-top: solid 1px #ccc;
    border-bottom: solid 1px #ccc;
    margin: 1em 0;
  }
</style>

<div style="cursor:pointer" on:click={() => (display = !display)}>
  Show code
  <Icon flip={display} type="up" theme="outline" size="1em" />
</div>
{#if display}
  <div class="code-section" transition:slide>{code}</div>
{/if}
