# condition.played

Checks the start of playback. Validation will be passed if playback is started. To play media with the `condition.played` check, you can use [view.audio](view.audio.md) and [view.video](view.video.md). The `condition.played` check only works in the player's `validation` property.

[View example in the sandbox](https://clck.ru/asS9J).

## Component properties {#properties}

| Name                                     | Type               | Description                                            |
| ---------------------------------------- | ------------------ | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.played" | <p>Set component type</p>                              |
| `hint`                                   | _string_           | <p>Validation error message that the user will see</p> |
