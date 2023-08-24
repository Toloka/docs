# helper.text-transform

Allows you to change the case of the text, like make all letters uppercase.

For example, you can use this component to automatically process input data.

This component is available in property values with the `string` type, for example in the `content` property in the [view.text](view.text.md) component.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/XWH9Iupl4Nv7Be)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [field.text](field.text.md): Adds a field for entering a short text.
- [view.text](view.text.md): Displays a text.
- [data.local](../operations/work-with-data.md): Local data.

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.text-transform" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _any_ | The text string in which you want to change the case. ||
|| `transformation`<span style="color: red">\*</span> | _string_ | Conversion mode:

- `uppercase` — Makes all letters uppercase.
- `lowercase` — Makes all letters lowercase.
- `capitalize` — Capitalizes **the first** letter in the text, and leaves the rest lowercase. The text is not divided into sentences: there will be only one uppercase letter in the entire text, even if you have several sentences.
  ||
  |#

{% include [contact-support](../_includes/contact-support.md) %}
