# view.alert

The component creates a color block to highlight important information.

You can use both plain text and other visual components inside it.

[View example in the sandbox](https://clck.ru/RfBPM).

## Component properties {#properties}

| Name                                     | Type         | Description                                                                                                                                                 |
| ---------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.alert" | <p>Set component type</p>                                                                                                                                   |
| `label`                                  | _string_     | <p>Label above the component.</p>                                                                                                                           |
| `content`                                | _view_       | <p>Content of the block with important information.</p>                                                                                                     |
| `hint`                                   | _string_     | <p>Hint text.</p>                                                                                                                                           |
| `theme`                                  | _string_     | <p>Determines the block color:</p><ul><li>`info` (default) — Blue.</li><li>`success` — Green.</li><li>`warning` — Yellow.</li><li>`danger` — Red.</li></ul> |
| `validation`                             | _condition_  | <p>Validation based on condition.</p>                                                                                                                       |
