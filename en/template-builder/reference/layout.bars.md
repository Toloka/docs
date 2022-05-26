# layout.bars

A component that adds top and bottom bars to the content.

You can use other components inside each part of this component, such as images, text, or options.

The top bar is located at the top edge of the component, and the bottom one is at the bottom edge. The content is placed between the bars and takes up all available space.

## Component properties {#properties}

| Name                                        | Type          | Description                                                   |
| ------------------------------------------- | ------------- | ------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>    | "layout.bars" | <p>Set component type</p>                                     |
| `barAfter`                                  | _view_        | <p>The bar displayed at the bottom edge of the component.</p> |
| `barBefore`                                 | _view_        | <p>The bar displayed at the top edge of the component.</p>    |
| `content`<span style="color: red">\*</span> | _view_        | <p>The main content.</p>                                      |
| `validation`                                | _condition_   | <p>Validation based on condition.</p>                         |
