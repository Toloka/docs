# condition.played-fully

This component checks for the end of playback. Validation is passed if playback is finished. To play media with the `condition.played-fully` check, you can use [view.audio](view.audio.md) and [view.video](view.video.md). The `condition.played-fully` check only works in the player's `validation` property.

[View example in the sandbox](https://clck.ru/asS7a).

## Component properties {#properties}

| Name                                     | Type                     | Description                                            |
| ---------------------------------------- | ------------------------ | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.played-fully" | <p>Set component type</p>                              |
| `hint`                                   | _string_                 | <p>Validation error message that the user will see</p> |
