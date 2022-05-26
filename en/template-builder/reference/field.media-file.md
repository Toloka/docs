# field.media-file

Adds buttons for different types of uploads: uploading photos or videos, selecting files from the file manager or choosing from the gallery. In the `accept` property, select which buttons you need.

By default, only one file can be uploaded, but you can allow multiple files in the `multiple` property.

This component is convenient when using mobile devices. To upload files from a computer, it's better to use [field.file](field.file.md) for a more flexible configuration of the file types.

In the task review mode, the uploaded images will appear automatically. You can view, rotate, and switch among the images.

[View example in the sandbox](https://clck.ru/asSVc).

## Using the Toloka mobile app

In the Toloka mobile app, the photo and video buttons open the camera, and the gallery and file manager buttons open the corresponding apps.

After the performer submits the task, the files are saved in the app and gradually uploaded to Toloka when there's a Wi-Fi connection. While there's no connection, the task status remains "Submitting via Wi-Fi".

## Component properties {#properties}

| Name                                       | Type                                                                                   | Description                                                                                                                                                                                                                   |
| ------------------------------------------ | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>   | "field.media-file"                                                                     | <p>Set component type</p>                                                                                                                                                                                                     |
| `data`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>                                                                                                                                                                    |
| `label`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                                                                                                             |
| `accept`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Adds different buttons for four types of uploads. Pass the `true` value for the ones that you need. </p><p>For example, if you need a button for uploading files from the gallery, add the `"gallery": true` property.</p> |
| `accept.fileSystem`                        | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Adds a button for uploading files from the file manager.</p>                                                                                                                                                               |
| `accept.gallery`                           | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Adds a button for uploading files from the gallery.</p>                                                                                                                                                                    |
| `accept.photo`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Adds a button for uploading images.</p>                                                                                                                                                                                    |
| `accept.video`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Adds a button for uploading videos.</p>                                                                                                                                                                                    |
| `hint`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                                                                                                             |
| `multiple`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Determines whether multiple files can be uploaded:</p><ul><li>`false` (default) — forbidden.</li><li>`true` — allowed.</li></ul>                                                                                           |
| `requiredCoordinates`                      | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>If the value is `true`, a file without geotag can not be uploaded.</p>                                                                                                                                                     |
| `validation`                               | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                                                                                         |
