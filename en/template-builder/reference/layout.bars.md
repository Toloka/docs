# layout.bars

A component that adds top and bottom bars to the content.

You can use other components inside each part of this component, such as images, text, or options.

The top bar is located at the top edge of the component, and the bottom one is at the bottom edge. The content is placed between the bars and takes up all available space.

## Component properties {#properties}

| Name                                        | Type                                                                                   | Description                                                   |
| ------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>    | "layout.bars"                                                                          | <p>Set component type</p>                                     |
| `barAfter`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>The bar displayed at the bottom edge of the component.</p> |
| `barBefore`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>The bar displayed at the top edge of the component.</p>    |
| `content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>The main content.</p>                                      |
| `validation`                                | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                         |
