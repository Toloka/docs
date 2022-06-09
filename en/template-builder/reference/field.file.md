# field.file

This component can be used for uploading files. It's displayed in the interface as an upload button.

You can list in the `accept` property the file types that will be suggested to a Toloker when uploading. By default, only one file can be uploaded, but you can allow multiple files in the `multiple` property.

If a Toloker logs in from a mobile device, it's more convenient to use [field.media-file](field.media-file.md) — it's adapted for mobile devices and makes it easier to upload photos and videos.

In the task review mode, the uploaded images will appear automatically. You can view, rotate, and switch among the images.

[View example in the sandbox](https://clck.ru/asSRq).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.file" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `accept` | _array_ | A list of file types that will be suggested to a Toloker when uploading. By default, you can upload any files.

Specify the types in the [MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) format. For example, you can suggest uploading images by adding the `image/jpeg` and `image/png` types. ||
|| `accept[]` | _string_ | File type in the [MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) format. ||
|| `hint` | _string_ | Hint text. ||
|| `multiple` | _boolean_ | Determines whether multiple files can be uploaded:

- `false` (default) — forbidden.
- `true` — allowed. ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#
