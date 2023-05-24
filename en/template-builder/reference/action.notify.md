# action.notify

The component creates a message in the lower-left corner of the screen.

You can set the how long the message will be active, the delay before displaying it, and the background color.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/n-FbOGzS4DZfHW)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Displays a text.
- [data.input](../operations/work-with-data.md): The input data. For example, links to images that will be shown to Tolokers.
- [view.action-button](view.action-button.md): Displays a button that calls an action.

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.notify" | Set component type. ||
|| `payload`<span style="color: red">\*</span> | _object_ | Parameters for the message. ||
|| `payload.content`<span style="color: red">\*</span> | _string_ | Message text. ||
|| `payload.delay` | _number_ | The duration of the delay (in milliseconds) before the message appears. ||
|| `payload.duration` | _number_ | The duration of the message activity (in milliseconds), which includes the duration of the delay before displaying it.

For example, if `duration` is 1000 and `delay` is 400, the message will be displayed for 600 milliseconds. ||
|| `payload.theme`<span style="color: red">\*</span> | _string_ | The background color of the message:

- `info` — blue.
- `success` — green.
- `warning` — yellow.
- `danger` — red.
  ||
  |#

{% include [contact-support](../_includes/contact-support.md) %}
