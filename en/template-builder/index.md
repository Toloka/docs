<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  column-gap: 50px;
  row-gap: 20px;
}
.grid-item {
  display: flex;
  flex-direction: column;
}
h2 {
  padding-top: 32px !important;
  margin-top: 0 !important;
}
h3 {
  padding-top: 8px !important;
  margin-top: 0 !important;
}
</style>

# Template Builder

Use [Template Builder]({{ template-builder }}) to create an interface for your web page that you can reuse with different input data. For example, you can use Template Builder to create a task interface for labeling images in [Toloka]({{ toloka-requester-index-dita }}).

<div class="grid-container">
    <div class="grid-item">
        <h3><a href="quickstart">Quick start</a></h3>
        <p>Learn how to create interfaces in Template Builder</p>
    </div>
    <div class="grid-item">
        <h3><a href="operations/all">List of instructions</a></h3>
        <p>Look up the instructions and examples for popular tasks</p>
    </div>
    <div class="grid-item">
        <h3><a href="templates/">Presets</a></h3>
        <p>Check out the list of ready-made presets</p>
    </div>
    <div class="grid-item">
        <h3><a href="reference/">Component reference guide</a></h3>
        <p>Find a detailed description for the component you are interested in</p>
    </div>
    <div class="grid-item">
        <h3><a href="troubleshooting/troubleshooting">Troubleshooting</a></h3>
        <p>Find the solution in the list of frequently asked questions</p>
    </div>
    <div class="grid-item">
        <h3><a href="concepts/support">Support</a></h3>
        <p>Email us if you have any problems</p>
    </div>
</div>

{% include [global-community](../_includes/global-community.md) %}

{% include [social-media](../_includes/social-media.md) %}