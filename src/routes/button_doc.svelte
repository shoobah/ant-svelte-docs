<script>
  import { Button, Icon } from "ant-svelte";
  import Main from "../components/Main.svelte";
  import CodeSection from "../components/CodeSection.svelte";

  let size = "default";

  const codeSection_0 = `<Button onClick={() => (size = 'large')}>Large</Button>
      <Button onClick={() => (size = 'default')}>Default</Button>
      <Button onClick={() => (size = 'small')}>Small</Button>`;
</script>

<style>
  div {
    padding: 0 0 10px 0;
  }
</style>

<svelte:head>
  <title>Ant-svelte Button</title>
</svelte:head>

<h1>Button</h1>
<h2>Usage</h2>
<p />

<section>
  <div>
    <div>
      <Button onClick={() => (size = 'large')}>Large</Button>
      <Button onClick={() => (size = 'default')}>Default</Button>
      <Button onClick={() => (size = 'small')}>Small</Button>
    </div>
    <CodeSection code={codeSection_0} />
    <div>
      <Button type="primary" {size}>Primary</Button>
      <Button {size}>Normal</Button>
      <Button type="dashed" {size}>Dashed</Button>
      <Button type="danger" {size}>Danger</Button>
      <Button type="link" {size}>Link</Button>
    </div>
    <div>
      <Button type="primary" icon="download" {size} />
      <Button type="primary" shape="circle" icon="download" {size} />
      <Button type="primary" shape="round" icon="download" {size} />
      <Button type="primary" shape="round" icon="download" {size}>
        Download
      </Button>
      <Button type="primary" icon="download" {size}>Download</Button>
    </div>
    <div>
      <Button type="primary" loading {size} />
      <Button type="primary" shape="circle" loading {size} />
      <Button type="primary" shape="round" loading {size} />
      <Button type="primary" shape="round" loading {size}>Download</Button>
      <Button type="primary" loading {size}>Download</Button>
    </div>
    <!-- <Button.Group {size}>
      <Button type="primary">
        <Icon type="left" />
        Backward
      </Button>
      <Button type="primary">
        Forward
        <Icon type="right" />
      </Button>
    </Button.Group> -->
  </div>
</section>
