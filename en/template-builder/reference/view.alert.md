# view.alert

The component creates a color block to highlight important information.

You can use both plain text and other visual components inside it.

[View example in the sandbox](https://clck.ru/RfBPM).

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                                                                                                                                 |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.alert"                                                                           | <p>Set component type</p>                                                                                                                                   |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                                           |
| `content`                                | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Content of the block with important information.</p>                                                                                                     |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                                           |
| `theme`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Determines the block color:</p><ul><li>`info` (default) — Blue.</li><li>`success` — Green.</li><li>`warning` — Yellow.</li><li>`danger` — Red.</li></ul> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                       |
