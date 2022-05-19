# plugin.field.image-annotation.hotkeys

Used to set hotkeys for the [field.image-annotation](field.image-annotation.md) component.

You can set hotkeys to select area types and selection modes and to confirm or cancel area creation. When setting hotkeys, you can use the up and down arrows (`up`,`down`), numbers, and Latin letters.

[View example in the sandbox](https://clck.ru/asSTF).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                                                                                         |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "plugin.field.image-annotation.hotkeys"                                          | <p>Set component type</p>                                                                                                                                           |
| `cancel`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for canceling area creation.</p>                                                                                                               |
| `confirm`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for confirming area creation.</p>                                                                                                              |
| `labels`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>   | <p>Keyboard shortcuts for choosing area types. They're assigned to buttons in the order they are shown if you enabled the option to choose multiple area types.</p> |
| `labels[]`                               | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>A keyboard shortcut.</p>                                                                                                                                         |
| `modes`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a> | <p>Keyboard shortcuts for choosing selection modes.</p>                                                                                                             |
| `modes.point`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for selecting areas using points.</p>                                                                                                          |
| `modes.polygon`                          | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for selecting areas using polygons.</p>                                                                                                        |
| `modes.rectangle`                        | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for selecting areas using rectangles.</p>                                                                                                      |
| `modes.select`                           | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Keyboard shortcut for selecting shapes and points.</p>                                                                                                           |
