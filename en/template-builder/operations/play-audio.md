# Playing back audio

In this section, we'll show how you can [embed an audio player](#insert-to-interface) into the interface, and how you can make sure that the user [listened](#validate-listened) to your file.

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Add an audio player to the interface {#insert-to-interface}

To insert an audio file into the task interface, add the [view.audio](../reference/view.audio.md) component to the template. In the `url` property, specify a direct link to the file (we recommend that you use the MP3 format):
```json
{
  "type": "view.audio",
  "url": "http://example.com/audio.mp3"
}
```

If you pass a link to an audio file in the [input data](work-with-data.md), use the `data.input` component in the `url` property.

To loop audio playback automatically, put `true` in the `loop` property.


[View example in the sandbox](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQwCuAEzgRhKpXn0AnbppAALOnSZ9kAejfxuRALREAHrpSTN58PpBSnAgS9voARpwmbvohELqGfG4ATAAMAIwA7G55eZ5w3gD6AUEhRBUAsgAKAMwVBTk5ANIAQpzBzWbUqnjcEBBMbHRW+qxDNAC+5gC6iotQ8yBCIHBQTPp0KGgb80A&locale=en).


## Make sure that the user listened to the audio {#validate-listened}

{% list tabs %}

- Started listening

  To make sure that the user played back the audio and at least started listening to it, use the `condition.played` component in the `validation` property.
  ```json
  {
    "type": "view.audio",
    "url": "http://example.com/audio.mp3",
    "validation": {
      "type": "condition.played"
    }
  }
  ```

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQwCuAEzgRhKpXm66ARkW6aQAFQBODLGF5gA1nCgIsAMr61lISWHBSUkTGupLcbiQSABYQ+nRYArrOdL7+dElEWAbGEJxm1Kp4+s72KLRJdHRMfMgA9K3w3EQAtEQAHrpSTF183ZBSnAjJwZwmrfrDELqGfK0ATAAMAIwA7K1bWx1wXQD6-YPDRCcAsgAKAMwnOxsbANIAQpxD9+WqOFq6XiGWImKBsKh-Gh4dSsOp4SBQYw5aCcYa6BjRX6Q+q+QRwkAATVSWCgRGiWDoECwaLc+UKxRM7l4TDKIHMYgAvuysFyKlgALqKXkckBCEC+JhpFBoEUcoA).


- Listened completely

  To make sure that the user listened to the entire recording, use the `condition.played-fully` component in the `validation` property.
  ```json
  {
    "type": "view.audio",
    "url": "http://example.com/audio.mp3",
    "validation": {
      "type": "condition.played-fully"
    }
  }
  ```

  
[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQwCuAEzgRhKpXm66ARkW6aQAFQBODLAN3O6cKAix0ACyIsA2MIEKhDLDBeMABrHz8AZX1rKQksEgkAiH06LF4BIihE-3DA4OLvZ2CayGdjX04zalU8fWd7FFoAujomPmQAeiH4biIAWiIAD10pJnG+CcgpTgRs1M4TIf0FiF1DPiGAJgAGAEYAdiHz89G4cYB9GbmFokeAWQAFAGZHy9OpwA0gAhTjzH4tVQ4LS6XiGXTeaBsKjQmh4dSsbp4SCRCQmKCcBa6BhEQwTGD6bjcBhQtE9HyCbEgACauSwUCIZLKWGJbgqISMJmivCYPIFxUMzRA5jEAF9ZVgFa0sABdRTKuUgIQgHxMPIoNBauVAA).

{% endlist %}

## Record audio {#record-audio}

To allow users to upload their audio files, use the [field.audio](../reference/field.audio.md) component.

On the website, `field.audio` allows users to upload audio files, and in the app, it opens the sound recorder.

```json
{
  "type": "field.audio",
  "data": {
    "type": "data.output",
    "path": "path",
  }
}
```

[View example in the sandbox](https://clck.ru/TEDEW).


## Create a task to transcribe audio {#transform-to-text}

To create a template for audio transcription tasks, we used the following components:

- [condition.played](../reference/condition.played.md): To make sure that the user listened to the audio.
- [condition.required](../reference/condition.required.md): To make sure that the user entered text into the multiline field ([field.textarea](../reference/field.textarea.md)).
- [plugin.toloka](../reference/plugin.toloka.md): To customize the task layout.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1uAQwBGRbmzwAZfpOx0IWOgAsiWdQFcAJnDNheTTsJVK8jFnoLESTjtHCA9qVTxbACddFGVw1VofVji8e3U6dU44KCZbQRARBIiQJgyLP2CnPE8xAF8ixPZ1XnS6Jyg2Kiacb2YUijxIKEd26E4mDQYiezCe2gscgsGQAE0IWywoIhnzM0n1BnMrGwcnLBc4NxrimjrarAaH7sS+31SQeB17TkkAD0yUSI6jmrxAGm0sRWABV+sdrP86FgGBssFZ1FEsDl4acQhdXO5Cg9eiA2iC4i8mm8BrQyZwNnQ8gVGj08GVLH4gXxbNwCsTHiySvgWnA2h0uvySck-MNRh1OECAI62OBA2ZE25iPCLKDLWjQxZ8LBSWwCLDaLDwbjcXY5G5Ne63R1iAC6iie1DZ3FsCBysjiCgSlJo1L8kx9OV+EG4EAA1uTBSHwYcGRLNbRYzl1Ss+GAotHYomtfR1HxYwB1UUcuIAVgADHWHs67oo3VA6oUQDkmSg0Io8FVQh8LHRGXxkAB6CdWogAWiIf3UUkmRD4s8gUk4vsstk02QgE9skwg6nsfAnACY6wBGADsE+v1+ncBtAH0F0uV6+ALIABQAzK+t4NgA0gAQpwy7-jcHZ1EAA).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
