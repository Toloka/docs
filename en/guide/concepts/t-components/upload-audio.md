# Button for recording and uploading an audio file

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for recording and uploading audio files in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.audio.md){% endif %}.

{% endnote %}

To add a button for audio recording and upload to the task, use the `{{field type="file" sources="RECORDER" fileType="AUDIO" name="<[output field](../incoming.md) name>" sources="<sources parameter>" fileType="<fileType parameter>"}}` component. Example:

{% if locale == "en-com" %}

```plaintext
{{field type="file" name="result" sources="RECORDER" fileType="AUDIO" label="Record audio"}}
```

{% endif %}

For a complete list of parameters, see the [table](#table).

Add a field with the `file` type in the [output data description](../incoming.md). Example:

```json
{
  "result": {
    "type": "file",
    "required": true
  }
}
```

Create tasks for mobile devices if you want to use the button for recording and uploading audio files, because these devices have a built-in voice recorder. Set the **Client = Mobile Toloka**[filter](../filters.md) in the [pool](../../../glossary.md#pool).

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

- `FILE_MANAGER`. | yes | no||
||`fileType`|

{% note info %}

This parameter applies to the tasks completed in the mobile app.

{% endnote %}

File type: `AUDIO` — Audio recording. | yes | no||
||`label`| The button label. For example, `label="Click me"`. | no | Depending on the interface language, “Загрузить файл” (Russian), “Upload file” (English), “Dosya yükle” (Turkish), “Faylni yuklash” (Uzbek).||
||`multipleSelect`| The number of files to download at the same time.

For the single file upload, set the value to `false`.

For upload of multiple files:

1. Set the value to `true`.

1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}
