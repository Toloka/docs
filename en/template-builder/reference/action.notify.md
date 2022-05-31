# action.notify

The component creates a message in the lower-left corner of the screen.

You can set the how long the message will be active, the delay before displaying it, and the background color.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.notify" | Set component type ||
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
