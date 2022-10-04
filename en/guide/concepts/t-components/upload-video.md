# Button for recording and uploading a video file

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for recording and uploading a video file in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.media-file){% endif %}.

{% endnote %}


To add a video upload button to the task, use the `{{field type= "file" name="[output field name](../incoming.md)> "sources="<sources parameter>" fileType="<fileType parameter>"}}` component.

For example, to add a video recording button, use:

```no-highlight
`{{field type="file" name="result" sources="CAMERA" fileType="VIDEO"}}`
```

For a complete list of parameters, see the [table](#table_param).

In the [output data](../incoming.md) description, add one of the fields:

- Field with the `file` type — For uploading one video only. Example:
    ```no-highlight
    {
    "result": {
    "type": "file",
    "required": true
    }
    }
    ```

- Field with the `array_file` type — For uploading several video files at once. Example:
    ```no-highlight
    {
    "result": {
    "type": "array_file",
    "required": true
    }
    }
    ```


Run tasks with a video recording button on mobile devices, since they have a built-in camera. Set the **Client = Mobile Toloka**[filter](../filters.md) in the [pool](../../../glossary.md#pool-ru).

#### Parameters

Parameter | Description | Required | Default value
----- | ----- | ----- | -----
``` type ``` | Field type: `file` — Button for file upload. | yes | no
``` name ``` | Attribute for the output data field. Contains the output field name. | yes | no
``` sources ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>The file source.<br/><br/>You can set several values in the format `sources="<value 1><value 2>"` (with a space, without a comma).<br/><br/>Supported values:<br/><br/>- `CAMERA`.<br/>- `GALLERY`.<br/>- `FILE_MANAGER`. | Yes (when creating tasks for mobile devices) | no
``` fileType ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>File type. You can set one of the allowed values:<br/><br/>- `VIDEO` — Video.<br/>- `IMAGE_OR_VIDEO` — Image or video.<br/>- `ANY` — Any file. | Yes (when creating tasks for mobile devices) | no
``` label ``` | The button label. For example, `label="Click me"`. | no | Depending on the interface language, "Загрузить файл" (Russian), "Upload file" (English), "Dosya yükle" (Turkish), "Faylni yuklash" (Uzbek).
``` validation-show ``` | The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.<br/><br/>Supported values:<br/><br/>- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.<br/>    <br/>- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.<br/>    <br/>- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.<br/>    <br/>- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.<br/>    <br/>- Don't display the message (`"false"`). | no | ``` "top-left" ```
``` camera ``` | Open the camera when the video upload button is clicked:<br/><br/>- `camera=true` — Open camera.<br/>    <br/>- `camera=false` — Don't open camera. | no | ``` false ```
``` multipleSelect ``` | The number of files to download at the same time.<br/>For the single file upload, set the value to `false`.<br/><br/>For upload of multiple files:<br/><br/>1. Set the value to `true`.<br/>1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).

{% include [contact-support](../../_includes/contact-support-help.md) %}
