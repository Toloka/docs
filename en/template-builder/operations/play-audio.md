# Playing back audio

In this section, we'll show how you can [embed an audio player](#insert-to-interface) into the interface, and how you can make sure that a Toloker [listened](#validate-listened) to your file.

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

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/hn12lyBE3ttC7a)

## Make sure that the Toloker listened to the audio {#validate-listened}

{% list tabs %}

- Started listening

  To make sure that the Toloker played back the audio and at least started listening to it, use the `condition.played` component in the `validation` property.

  ```json
  {
    "type": "view.audio",
    "url": "http://example.com/audio.mp3",
    "validation": {
      "type": "condition.played"
    }
  }
  ```

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/wVqSKJCJ3ttC9M)

- Listened completely

  To make sure that the Toloker listened to the entire recording, use the `condition.played-fully` component in the `validation` property.

  ```json
  {
    "type": "view.audio",
    "url": "http://example.com/audio.mp3",
    "validation": {
      "type": "condition.played-fully"
    }
  }
  ```

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ImNzPO9F3ttCB7)

{% endlist %}

## Record audio {#record-audio}

To allow Tolokers to upload their audio files, use the [field.audio](../reference/field.audio.md) component.

On the website, `field.audio` allows Tolokers to upload audio files, and in the app, it opens the sound recorder.

```json
{
  "type": "field.audio",
  "data": {
    "type": "data.output",
    "path": "path",
  }
}
```

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/uDWbPPCP3ttFAM)

## Create a task to transcribe audio {#transform-to-text}

To create a template for audio transcription tasks, we used the following components:

- [condition.played](../reference/condition.played.md): To make sure that a Toloker listened to the audio.
- [condition.required](../reference/condition.required.md): To make sure that a Toloker entered text into the multiline field ([field.textarea](../reference/field.textarea.md)).
- [plugin.toloka](../reference/plugin.toloka.md): To customize the task layout.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/aAynLBRt3ttCCg)

{% include [contact-support](../_includes/contact-support.md) %}