<script>
  import { Icon } from "ant-svelte";
  export let segment;
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding-top: 1em;
    padding-left: 1em;
    min-height: calc(100vh - 2px);
    position: fixed;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    padding-bottom: 0.5em;
  }

  .selected {
    position: relative;
    display: inline-block;
  }

  .selected::after {
    position: absolute;
    content: "";
    width: 100%;
    height: 2px;
    background-color: rgb(255, 62, 0);
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    /* padding: 1em 0.5em; */
    display: inline;
  }
</style>

<nav>
  <ul>
    <li>
      <a class={segment === undefined ? 'selected' : ''} href=".">
        <Icon type="home" size="20px" />
        home
      </a>
    </li>
    <li>
      <a
        rel="prefetch"
        class={segment === 'icon_doc' ? 'selected' : ''}
        href="icon_doc">
        <Icon type="appstore" theme="outline" size="20px" />
        icon
      </a>
    </li>
    <li>
      <a
        rel="prefetch"
        class={segment === 'button_doc' ? 'selected' : ''}
        href="button_doc">
        <Icon type="check-square" theme="outline" size="20px" />
        button
      </a>
    </li>
  </ul>
</nav>
