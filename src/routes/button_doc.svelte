<script>
  import { Button, Icon } from "ant-svelte";

  let size = "default";
</script>

<style>
  div {
    padding: 0 0 10px 0;
  }
</style>

<div slot="main">
  <h1>Button</h1>
  <section>
    <div>
      <Button onClick={() => (size = 'large')}>Large</Button>
      <Button onClick={() => (size = 'default')}>Default</Button>
      <Button onClick={() => (size = 'small')}>Small</Button>
      <br />
      <br />
      <Button type="primary" {size}>Primary</Button>
      <Button {size}>Normal</Button>
      <Button type="dashed" {size}>Dashed</Button>
      <Button type="danger" {size}>Danger</Button>
      <Button type="link" {size}>Link</Button>
      <br />
      <Button type="primary" icon="download" {size} />
      <Button type="primary" shape="circle" icon="download" {size} />
      <Button type="primary" shape="round" icon="download" {size} />
      <Button type="primary" shape="round" icon="download" {size}>
        Download
      </Button>
      <Button type="primary" icon="download" {size}>Download</Button>
      <br />
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
</div>
