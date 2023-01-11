# field.media-file

Adds buttons for different types of uploads: uploading photos or videos, selecting files from the file manager or choosing from the gallery. In the `accept` property, select which buttons you need.

By default, only one file can be uploaded, but you can allow multiple files in the `multiple` property.

This component is convenient when using mobile devices. To upload files from a computer, it's better to use [field.file](field.file.md) for a more flexible configuration of the file types.

In the task review mode, the uploaded images will appear automatically. You can view, rotate, and switch among the images.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/Td82X7Jv3twhPM)

## Using the Toloka mobile app

In the Toloka mobile app, the photo and video buttons open the camera, and the gallery and file manager buttons open the corresponding apps.

After a Toloker submits the task, the files are saved in the app and gradually uploaded to Toloka when there's a Wi-Fi connection. While there's no connection, the task status remains "Submitting via Wi-Fi".

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.media-file" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `accept`<span style="color: red">\*</span> | _object_ | Adds different buttons for four types of uploads. Pass the `true` value for the ones that you need.

For example, if you need a button for uploading files from the gallery, add the `"gallery": true` property. ||
|| `accept.fileSystem` | _boolean_ | Adds a button for uploading files from the file manager. ||
|| `accept.gallery` | _boolean_ | Adds a button for uploading files from the gallery. ||
|| `accept.photo` | _boolean_ | Adds a button for uploading images. ||
|| `accept.video` | _boolean_ | Adds a button for uploading videos. ||
|| `hint` | _string_ | Hint text. ||
|| `multiple` | _boolean_ | Determines whether multiple files can be uploaded:

- `false` (default) — forbidden.
- `true` — allowed. ||
  || `requiredCoordinates` | _boolean_ | If the value is `true`, a file without geotag can not be uploaded. ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#
