# Playing back audio

In this section, we'll show how you can [embed an audio player](#insert-to-interface) into the interface, and how you can make sure that the user [listened](#validate-listened) to your file.

{% note info %}

You can add
{% cut "media files" %}

audio files, videos, images

{% endcut %}

 from your own server, [Yandex.Disk](../reference/helper.proxy.md), or a cloud storage like [Yandex.Cloud]({{ toloka-requester-concepts-yacloud-dita }}), Google Cloud, or Amazon AWS.

{% endnote %}



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

.


## Make sure that the user listened to the audio {#validate-listened}

#### Started listening

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

.

#### Listened completely

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

.


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

.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
