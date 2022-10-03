# Button for file upload

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for uploading files in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.media-file){% endif %}.

{% endnote %}


To add a file upload button to the task, use the `{{field type= "file" name="[output field name](../incoming.md)> "sources="<sources parameter>" fileType="<fileType parameter>"}}` component. Example:

```no-highlight
`{{field type="file" name="result" sources="GALLERY" fileType="IMAGE_OR_VIDEO"}}`
```

For a complete list of parameters, see the [table](#table).

In the [output data](../../../glossary.md#input-output-data-ru) description, add one of the fields:

- Field with the `file` type — for uploading one file only. Example:
    ```no-highlight
    {
    "result": {
    "type": "file",
    "required": true
    }
    }
    ```

- Field with the `array_file` type — for uploading several files at once. Example:
    ```no-highlight
    {
    "result": {
    "type": "array_file",
    "required": true
    }
    }
    ```


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
``` sources ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>The file source.<br/><br/>You can set several values in the format `sources="<value 1><value 2>"` (with a space, without a comma).<br/><br/>Supported values:<br/><br/>- `RECORDER` — Built-in voice recorder in the device.<br/>- `CAMERA`.<br/>- `GALLERY`.<br/>- `FILE_MANAGER`. | yes | no
``` fileType ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>File type. You can set one of the allowed values:<br/><br/>- `IMAGE_OR_VIDEO` — Image or video.<br/>- `VIDEO` — Video.<br/>- `AUDIO` — Audio recording.<br/>- `ANY` — Any file. | Yes (when creating tasks for mobile devices) | no
``` label ``` | The button label. For example, `label="Click me"`. | no | Depending on the interface language, “Загрузить файл” (Russian), “Upload file” (English), “Dosya yükle” (Turkish), “Faylni yuklash” (Uzbek).
``` validation-show ``` | The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.<br/><br/>Supported values:<br/><br/>- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.<br/>    <br/>- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.<br/>    <br/>- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.<br/>    <br/>- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.<br/>    <br/>- Don't display the message (`"false"`). | no | ``` "top-left" ```
``` class ``` | The CSS class for the field. For example, `class="annotation"`. | no | ``` ".field" ".field_type_file" ```
``` multipleSelect ``` | The number of files to download at the same time.<br/>For the single file upload, set the value to `false`.<br/><br/>For upload of multiple files:<br/><br/>1. Set the value to `true`.<br/>1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).

{% include [contact-support](../../_includes/contact-support-help.md) %}