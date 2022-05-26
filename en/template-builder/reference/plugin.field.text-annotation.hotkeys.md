# plugin.field.text-annotation.hotkeys

Use this to set keyboard shortcuts for the [field.text-annotation](field.text-annotation.md) component.

[View example in the sandbox](https://clck.ru/asSoy).

## Component properties {#properties}

| Name                                     | Type                                   | Description                                                                                                                                       |
| ---------------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "plugin.field.text-annotation.hotkeys" | <p>Set component type</p>                                                                                                                         |
| `labels`                                 | _array_                                | <p>Keyboard shortcuts for selecting categories. They're assigned to buttons with categories in the order they're shown.</p>                       |
| `labels[]`                               | _string_                               | <p>A keyboard shortcut.</p>                                                                                                                       |
| `remove`                                 | _string_                               | <p>Use this property to allow the performer to deselect an entire line or part of it. The key that you assign to this property will deselect.</p> |
