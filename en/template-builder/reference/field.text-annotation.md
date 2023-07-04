# field.text-annotation

A component for text segmentation.

Use it to select multiple words, individual words, or letters in the text and label them with values. You can create multiple categories to label parts of the text, like all nouns and adjectives.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/XbppitaZ3twmLU)

You can use [plugin.field.text-annotation.hotkeys](plugin.field.text-annotation.hotkeys.md) to assign keyboard shortcuts for selecting categories.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.text-annotation" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `label` | _string_ | Label above the component. ||
|| `adjust` | _string_ | If the property value is set to `words`, only words can be selected in the text. If you don't use this property, any part of a line can be selected. ||
|| `content`<span style="color: red">\*</span> | _string_ | The text where a Toloker has to select part of a line. ||
|| `disabled` | _boolean_ | This property blocks the component. If `true`, the component is unavailable to a Toloker. The default value is `false`. ||
|| `hint` | _string_ | Hint text. ||
|| `labels`<span style="color: red">\*</span> | _array_ | An array of categories that a Toloker uses to label parts of the text. ||
|| `labels[]` | _object_ | A category. ||
|| `labels[].label`<span style="color: red">\*</span> | _string_ | Specify the category name in the `label` property. ||
|| `labels[].value`<span style="color: red">\*</span> | _string_ | Specify the category value in the `value` property. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
