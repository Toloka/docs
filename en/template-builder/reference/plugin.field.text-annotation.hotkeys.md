# plugin.field.text-annotation.hotkeys

Use this to set keyboard shortcuts for the [field.text-annotation](field.text-annotation.md) component.

[View example in the sandbox](https://clck.ru/asSoy).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                                                                       |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "plugin.field.text-annotation.hotkeys"                                           | <p>Set component type</p>                                                                                                                         |
| `labels`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>   | <p>Keyboard shortcuts for selecting categories. They're assigned to buttons with categories in the order they're shown.</p>                       |
| `labels[]`                               | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>A keyboard shortcut.</p>                                                                                                                       |
| `remove`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Use this property to allow the performer to deselect an entire line or part of it. The key that you assign to this property will deselect.</p> |
