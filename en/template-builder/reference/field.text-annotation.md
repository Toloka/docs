# field.text-annotation

A component for text segmentation.

Use it to select multiple words, individual words, or letters in the text and label them with values. You can create multiple categories to label parts of the text, like all nouns and adjectives.

[View example in the sandbox](https://clck.ru/asSZA).

You can use [plugin.field.text-annotation.hotkeys](plugin.field.text-annotation.hotkeys.md) to assign keyboard shortcuts for selecting categories.

## Component properties {#properties}

| Name                                               | Type                    | Description                                                                                                                                                 |
| -------------------------------------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>           | "field.text-annotation" | <p>Set component type</p>                                                                                                                                   |
| `data`<span style="color: red">\*</span>           | _writable_              | <p>Data with values that will be processed or changed.</p>                                                                                                  |
| `label`                                            | _string_                | <p>Label above the component.</p>                                                                                                                           |
| `adjust`                                           | _string_                | <p>If the property value is set to `words`, only words can be selected in the text. If you don't use this property, any part of a line can be selected.</p> |
| `content`<span style="color: red">\*</span>        | _string_                | <p>The text where the performer has to select part of a line.</p>                                                                                           |
| `disabled`                                         | _boolean_               | <p>This property blocks the component. If `true`, the component is unavailable to the performer. The default value is `false`.</p>                          |
| `hint`                                             | _string_                | <p>Hint text.</p>                                                                                                                                           |
| `labels`<span style="color: red">\*</span>         | _array_                 | <p>An array of categories that the performer uses to label parts of the text.</p>                                                                           |
| `labels[]`                                         | _object_                | <p>A category.</p>                                                                                                                                          |
| `labels[].label`<span style="color: red">\*</span> | _string_                | <p>Specify the category name in the `label` property.</p>                                                                                                   |
| `labels[].value`<span style="color: red">\*</span> | _string_                | <p>Specify the category value in the `value` property.</p>                                                                                                  |
| `validation`                                       | _condition_             | <p>Validation based on condition.</p>                                                                                                                       |
