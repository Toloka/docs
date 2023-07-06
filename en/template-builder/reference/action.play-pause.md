# action.play-pause

This component controls audio or video playback. It stops playback in progress or starts if it is stopped.

For example, this component will allow you to play two videos simultaneously.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/AiIEBqw-3YbMBH)

{% cut "Components used in the example" %}

- [layout.side-by-side](layout.side-by-side.md): Displays several data blocks of the same width on a single horizontal panel.
- [view.video](view.text.md): Adds a player for video playback.
- [view.list](view.list.md): Displays data in a list.
- [field.radio-group](field.radio-group.md): Adds a component for selecting one value out of several options.
- [view.action-button](view.action-button.md): Displays a button that calls an action.
- [plugin.hotkeys](plugin.hotkeys.md): Sets keyboard shortcuts for actions. 

{% endcut %}


You can also stop or start playback for some event ([plugin.trigger](plugin.trigger.md)) or by pressing the hotkey ([plugin.hotkeys](plugin.hotkeys.md)).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/ip43S-aL3tz9c7)

{% cut "Components used in the example" %}

- [layout.side-by-side](layout.side-by-side.md): Displays several data blocks of the same width on a single horizontal panel.
- [view.video](view.text.md): Adds a player for video playback.
- [view.list](view.list.md): Displays data in a list.
- [field.radio-group](field.radio-group.md): Adds a component for selecting one value out of several options.
- [view.action-button](view.action-button.md): Displays a button that calls an action.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.play-pause" | Set component type. ||
|| `view` | _ref_ | Points to the component that plays audio or video. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
