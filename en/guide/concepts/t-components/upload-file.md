# Button for file upload

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for uploading files in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.media-file.md){% endif %}.

{% endnote %}

To add a file upload button to the task, use the `{{field type= "file" name="output field name> "sources="<sources parameter>" fileType="<fileType parameter>"}}` component. Example:

```plaintext
`{{field type="file" name="result" sources="GALLERY" fileType="IMAGE_OR_VIDEO"}}`
```

For a complete list of parameters, see the [table](#parameters).

In the [output data](../../../glossary.md#input-output-data) description, add one of the fields:

- Field with the `file` type — for uploading one file only. Example:

    ```json
    {
    "result": {
    "type": "file",
    "required": true
    }
    }
    ```

- Field with the `array_file` type — for uploading several files at once. Example:

    ```json
    {
    "result": {
    "type": "array_file",
    "required": true
    }
    }
    ```

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`type`| Field type: `file` — Button for file upload. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`sources`|

{% note info %}

This parameter applies to the tasks completed in the mobile app.

{% endnote %}

The file source.

You can set several values in the format `sources="<value 1><value 2>"` (with a space, without a comma).

Supported values:

- `RECORDER` — Built-in voice recorder in the device.

- `CAMERA`.

- `GALLERY`.

- `FILE_MANAGER`. | yes | no||
||`fileType`|

{% note info %}

This parameter applies to the tasks completed in the mobile app.

{% endnote %}

File type. You can set one of the allowed values:

- `IMAGE_OR_VIDEO` — Image or video.

- `VIDEO` — Video.

- `AUDIO` — Audio recording.

- `ANY` — Any file. | Yes (when creating tasks for mobile devices) | no||
||`label`| The button label. For example, `label="Click me"`. | no | Depending on the interface language, “Загрузить файл” (Russian), “Upload file” (English), “Dosya yükle” (Turkish), “Faylni yuklash” (Uzbek).||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`class`| The CSS class for the field. For example, `class="annotation"`. | no | `".field" ".field_type_file"`||
||`multipleSelect`| The number of files to download at the same time.

For the single file upload, set the value to `false`.

For upload of multiple files:

1. Set the value to `true`.

1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}
