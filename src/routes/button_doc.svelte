<script>
  import { Button } from "ant-svelte";
</script>

<style>
  div {
    padding: 0 0 10px 0;
  }
</style>

<h1>Button</h1>
<section>
  <div>
    <Button>Normal</Button>
    <Button type="primary">Primary</Button>
    <Button type="danger">Danger</Button>
    <Button type="dashed">Dashed</Button>
  </div>
  <div>
    <Button size="small">Normal - small</Button>
    <Button size="small" type="primary">Primary - small</Button>
    <Button size="small" type="danger">Danger - small</Button>
    <Button size="small" type="dashed">Dashed - small</Button>
  </div>
  <div>
    <Button size="large">Normal - large</Button>
    <Button size="large" type="primary">Primary - large</Button>
    <Button size="large" type="danger">Danger - large</Button>
    <Button size="large" type="dashed">Dashed - large</Button>
  </div>
  <div>
    <Button icon="download">Normal with icon</Button>
    <Button icon="download" type="primary">Primary with icon</Button>
    <Button icon="download" type="danger">Danger with icon</Button>
    <Button icon="download" type="dashed">Dashed with icon</Button>
  </div>
  <div>
    <Button icon="download" shape="round">Round with icon</Button>
    <Button icon="download" shape="circle" />
    <Button icon="download" type="primary" shape="circle" />
  </div>
</section>
