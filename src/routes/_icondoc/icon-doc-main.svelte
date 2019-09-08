<script>
  import { Icon } from "ant-svelte";
  import * as allIcons from "@ant-design/icons/lib/dist";
  import { fade } from "svelte/transition";
  import copy from "copy-to-clipboard";

  export let setSelectedIcon;

  var sortByNameThenTheme = (a, b) => {
    var nameComp = a.name.localeCompare(b.name, "en");
    var themeComp = a.theme.localeCompare(b.theme, "en");
    if (themeComp === 0) {
      return nameComp;
    }
    return themeComp;
  };

  var sortByThemeThenName = (a, b) => {
    var nameComp = a.name.localeCompare(b.name, "en");
    var themeComp = a.theme.localeCompare(b.theme, "en");
    if (nameComp === 0) {
      return themeComp;
    }
    return nameComp;
  };

  var selectedIcon;
  var byName = false;
  var icons = [];
  var flipped = false;

  $: icons = Object.keys(allIcons)
    .map(key => allIcons[key])
    .filter(e => e.name && e.theme)
    .map(i => ({
      name: i.name,
      theme: i.theme,
      id: i.name + "." + i.theme + "_text",
      html: `<Icon type="${i.name}" theme="${i.theme}" />`
    }))
    .sort(byName ? sortByNameThenTheme : sortByThemeThenName);

  function onClick(icon) {
    selectedIcon = icon;
    setSelectedIcon(icon);
    var text = icon.name + "." + icon.theme + "_text";
    var thing = document.getElementById(text);
    thing.select();
    copy(icon.html);
  }

  function toggleSort(e) {
    byName = e.target.checked;
  }
</script>

<style>
  .wrapper {
    display: flex;
    flex-flow: wrap;
    width: 100%;
  }

  .icon-box {
    flex: 0 1 auto;
    text-align: center;
    padding-bottom: 20px;
    width: 150px;
    cursor: pointer;
  }

  section {
    padding-bottom: 1em;
  }
  textarea {
    border: none;
    resize: none;
    user-select: none;
    cursor: pointer;
    display: none;
  }
</style>

<svelte:head>
  <title>Ant-svelte Icon</title>
</svelte:head>

<h1>Icon</h1>
<section>
  <h2>Usage</h2>
  <p>The Icon element are used thus:</p>
  <pre>
    {'<Icon type="close-circle" theme="outline" color="black" />'}
    <Icon type="close-circle" theme="outline" color="black" />
  </pre>
  <p>
    The attribute
    <strong>theme</strong>
    is optional and defaults to outline.
    <br />
    The attribute
    <strong>color</strong>
    is optional and defaults to black.
  </p>
  <p>
    If you want to use the twotone theme there's another optional attribute
    called
    <strong>twoToneColor</strong>
    that's used for the second color.
  </p>
  <pre>
    {'<Icon type="close-circle" theme="twotone" color="black" twoToneColor="red" />'}
    <Icon
      type="close-circle"
      theme="twotone"
      color="black"
      twoToneColor="red" />
  </pre>
  <p>The attribute twoToneColor is optional and defaults to #80e8ff</p>
  <p>You can set the spin attribute to make it spin (obviously).</p>
  <pre>
    {'<Icon type="close-circle" spin />'}
    <Icon type="loading" theme="outline" spin />
  </pre>
  <p>The attribute twoToneColor is optional and defaults to #80e8ff</p>
  <p>
    An icon can be rotated half a turn by setting the
    <strong>flip</strong>
    attribute to true
  </p>
  Click this! ->
  <Icon
    size="1em"
    type="caret-up"
    theme="fill"
    flip={flipped}
    style="cursor:pointer"
    on:click={() => (flipped = !flipped)} />
</section>
<h2>Available icons:</h2>

<div>{icons.length} icons available</div>
<div style="padding-bottom:20px">
  <input
    type="checkbox"
    id="sortorder"
    name="sortorder"
    on:change={toggleSort} />
  <label for="sortorder">Sort by theme:</label>
</div>
<div class="wrapper">
  {#each icons as icon}
    <div in:fade class="icon-box" on:click={e => onClick(icon)}>
      <Icon type={icon.name} theme={icon.theme} />
      <br />
      <span>{icon.name} - {icon.theme}</span>
      <textarea id={icon.id} readonly>{icon.html}</textarea>
    </div>
  {/each}
</div>
