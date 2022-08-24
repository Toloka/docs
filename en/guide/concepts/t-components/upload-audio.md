# Button for recording and uploading an audio file

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for recording and uploading audio files in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.audio){% endif %}.

{% endnote %}


To add a button for audio recording and upload to the task, use the `{{field type="file" sources="RECORDER" fileType="AUDIO" name="<[output field](../incoming.md) name>" sources="<sources parameter>" fileType="<fileType parameter>"}}` component. Example:
 {% if locale == "en-com" %}
```no-highlight
{{field type="file" name="result" sources="RECORDER" fileType="AUDIO" label="Record audio"}}
```
{% endif %}
For a complete list of parameters, see the [table](#table).

Add a field with the `file` type in the [output data description](../incoming.md). Example:

```no-highlight
{
  "result": {
    "type": "file",
    "required": true
  }
}
```

Create tasks for mobile devices if you want to use the button for recording and uploading audio files, because these devices have a built-in voice recorder. Set the **Client = Mobile Toloka**[filter](../filters.md) in the [pool](../../../glossary.md#pool-ru).

#### Parameters


Parameter
 |
Description
 |
Required
 |
Default value

----- | ----- | ----- | -----
``` type ``` | Field type: `file` — Button for file upload. | yes | no
``` name ``` | Attribute for the output data field. Contains the output field name. | yes | no
``` sources ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>The file source.<br/><br/>You can set several values in the format `sources="<value 1><value 2>"` (with a space, without a comma).<br/><br/>Supported values:<br/><br/>- `RECORDER` — Built-in voice recorder in the device.<br/>- `FILE_MANAGER`. | yes | no
``` fileType ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/>File type: `AUDIO` — Audio recording. | yes | no
``` label ``` | The button label. For example, `label="Click me"`. | no | Depending on the interface language, <q>Загрузить файл</q> (Russian), <q>Upload file</q> (English), <q>Dosya yükle</q> (Turkish), <q>Faylni yuklash</q> (Uzbek).
``` multipleSelect ``` | The number of files to download at the same time.<br/>For the single file upload, set the value to `false`.<br/><br/>For upload of multiple files:<br/><br/>1. Set the value to `true`.<br/>1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).
``` validation-show ``` | The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.<br/><br/>Supported values:<br/><br/>- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.<br/>    <br/>- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.<br/>    <br/>- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.<br/>    <br/>- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.<br/>    <br/>- Don't display the message (`"false"`). | no | ``` "top-left" ```

{% include [contact-support](../../_includes/contact-support-help.md) %}