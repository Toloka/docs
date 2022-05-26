# action.play-pause

This component controls audio or video playback. It stops playback in progress or starts if it is stopped.

For example, this component will allow you to play two videos simultaneously.

[View example in the sandbox](https://clck.ru/asRof).

You can also stop or start playback for some event ([plugin.trigger](plugin.trigger.md)) or by pressing the hotkey ([plugin.hotkeys](plugin.hotkeys.md)).

[View example in the sandbox](https://clck.ru/asRpD).

## Component properties {#properties}

| Name                                     | Type                | Description                                               |
| ---------------------------------------- | ------------------- | --------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "action.play-pause" | <p>Set component type</p>                                 |
| `view`                                   | _ref_               | <p>Points to the component that plays audio or video.</p> |
