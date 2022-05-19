# Troubleshooting

## Video and audio {#media}

{% cut "Video or audio is not playing" %}

Errors may occur when playing back the linked media files. The preview window shows the error causes. The table below describes how to troubleshoot errors.

#|
||**Error message**|**Cause and fix**||
||Playback was interrupted|**Cause:** Getting and downloading the media file has been interrupted by the user.

**How to fix:** Refresh the page.||
||Can't download video/audio due to network problems|**Cause:** The media file can't be downloaded because the network connection is down or unstable.

**How to fix:** Check the network connection and refresh the page.||
||The format is not supported by your device|**Cause:** An attempt to decode the media file has failed.

This might happen if the media file format mismatches the device codec or the file is damaged.

**How to fix:**
1. Check the media file: it might be damaged.
1. Reinstall or add the codecs for the device's operating system.||
||Video/audio file download failure or non-video file hosted at the URL|**Possible causes and fixes:**
- **Cause:** There is no media file at the link.

  **How to fix:** Make sure that you provided a correct media file link.

- **Cause:** The media file format is not supported. File format support depends on the user's browser, OS, and device.

  **How to fix:** Try using files in one of the specified formats.
  
  {% cut "Video formats" %}

    - [MP4]({{ wiki-mp4 }}) in the H.264 or H.265 encoding is the recommended format.
    - [WebM]({{ wiki-webm }});
    - [MPEG]({{ wiki-mpeg }}).

  {% endcut %}

  {% cut "Audio formats" %}

    - [FLAC]({{ wiki-flac }});
    - [MP3]({{ wiki-mp3 }}) (recommended format).
    - [OGG]({{ wiki-ogg }});
    - [OPUS]({{ wiki-opus }});
    - [WAV]({{ wiki-wav }}).
  
  {% endcut %}
  
- **Cause:** The server that hosts the media file fails to send it to the task suite. It returns an empty output or the "Access denied" message, because the downloaded file is detected at an unknown domain.

  **How to fix:** Refine the settings of your server or change the domain that sends the request for the media file download.

- **Cause:** The server failed or network connection was interrupted.

  **How to fix:** Check the server access and network connection, and try to download the media file again.||
|#

{% endcut %}

## Shortcuts {#hotkey}

{% cut "A shortcut is not displayed" %}


To display a shortcut in the interface, set the shortcut to the same [action](../reference/actions.md) that is performed when the button is clicked.

Assign an action to the component if you haven't yet:
- [action.set](../reference/action.set.md) for radio buttons.
- [action.toggle](../reference/action.toggle.md) for checkboxes.
- [action.play-pause](../reference/action.play-pause.md) for playback control.
- [action.open-close](../reference/action.open-close.md) to zoom in on images.

You can see the full list of actions in [List of actions](../reference/actions.md).

Keep in mind the following:

- The data types for actions must be the same. For example, in the following case the shortcut works but is not displayed: clicking on the button saves the `“true”` string to the results, and the Boolean value `true` is defined for the shortcut.
- If multiple actions are triggered when the button is clicked ([action.bulk](../reference/action.bulk.md)), the sequence of these actions for the shortcut must be the same.
- If you use a conditional operator to select an action, such as [helper.if](../reference/helper.if.md), the same conditional operator (**helper.if**) must be called under the same rules when the shortcut key is pressed.

{% endcut %}

## Escaping

#### How to add quotation marks and slashes in JSON

{% include [json-guide-escaping_json](../_includes/quickstart/id-json-guide/escaping_json.md) %}
