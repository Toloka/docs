# plugin.field.image-annotation.hotkeys

Used to set hotkeys for the [field.image-annotation](field.image-annotation.md) component.

You can set hotkeys to select area types and selection modes and to confirm or cancel area creation. When setting hotkeys, you can use the up and down arrows (`up`,`down`), numbers, and Latin letters.

[View example in the sandbox](https://clck.ru/asSTF).

## Component properties {#properties}

| Name                                     | Type                                    | Description                                                                                                                                                         |
| ---------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "plugin.field.image-annotation.hotkeys" | <p>Set component type</p>                                                                                                                                           |
| `cancel`                                 | _string_                                | <p>Keyboard shortcut for canceling area creation.</p>                                                                                                               |
| `confirm`                                | _string_                                | <p>Keyboard shortcut for confirming area creation.</p>                                                                                                              |
| `labels`                                 | _array_                                 | <p>Keyboard shortcuts for choosing area types. They're assigned to buttons in the order they are shown if you enabled the option to choose multiple area types.</p> |
| `labels[]`                               | _string_                                | <p>A keyboard shortcut.</p>                                                                                                                                         |
| `modes`                                  | _object_                                | <p>Keyboard shortcuts for choosing selection modes.</p>                                                                                                             |
| `modes.point`                            | _string_                                | <p>Keyboard shortcut for selecting areas using points.</p>                                                                                                          |
| `modes.polygon`                          | _string_                                | <p>Keyboard shortcut for selecting areas using polygons.</p>                                                                                                        |
| `modes.rectangle`                        | _string_                                | <p>Keyboard shortcut for selecting areas using rectangles.</p>                                                                                                      |
| `modes.select`                           | _string_                                | <p>Keyboard shortcut for selecting shapes and points.</p>                                                                                                           |
