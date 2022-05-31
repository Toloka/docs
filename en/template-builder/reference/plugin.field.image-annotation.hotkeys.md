# plugin.field.image-annotation.hotkeys

Used to set hotkeys for the [field.image-annotation](field.image-annotation.md) component.

You can set hotkeys to select area types and selection modes and to confirm or cancel area creation. When setting hotkeys, you can use the up and down arrows (`up`,`down`), numbers, and Latin letters.

[View example in the sandbox](https://clck.ru/asSTF).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "plugin.field.image-annotation.hotkeys" | Set component type ||
|| `cancel` | _string_ | Keyboard shortcut for canceling area creation. ||
|| `confirm` | _string_ | Keyboard shortcut for confirming area creation. ||
|| `labels` | _array_ | Keyboard shortcuts for choosing area types. They're assigned to buttons in the order they are shown if you enabled the option to choose multiple area types. ||
|| `labels[]` | _string_ | A keyboard shortcut. ||
|| `modes` | _object_ | Keyboard shortcuts for choosing selection modes. ||
|| `modes.point` | _string_ | Keyboard shortcut for selecting areas using points. ||
|| `modes.polygon` | _string_ | Keyboard shortcut for selecting areas using polygons. ||
|| `modes.rectangle` | _string_ | Keyboard shortcut for selecting areas using rectangles. ||
|| `modes.select` | _string_ | Keyboard shortcut for selecting shapes and points. ||
|#
