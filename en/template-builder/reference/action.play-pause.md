# action.play-pause

This component controls audio or video playback. It stops playback in progress or starts if it is stopped.

For example, this component will allow you to play two videos simultaneously.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/AiIEBqw-3YbMBH)

You can also stop or start playback for some event ([plugin.trigger](plugin.trigger.md)) or by pressing the hotkey ([plugin.hotkeys](plugin.hotkeys.md)).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/ip43S-aL3tz9c7)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.play-pause" | Set component type ||
|| `view` | _ref_ | Points to the component that plays audio or video. ||
|#
