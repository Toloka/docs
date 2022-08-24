# Button for image file upload

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for uploading images in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.media-file){% endif %}.

{% endnote %}


To add an image upload button ![](../../_images/other/b-image-button.png) to the task, use the `{{field type= "file-img" name="<[output field](../incoming.md) name> "sources="<sources parameter>" fileType="<fileType parameter>"}}`. After the image is uploaded the Toloker will see an icon for image preview. Example:

```no-highlight
{{field type="file-img" name="photo" sources="CAMERA" fileType="IMAGE" camera=true}}
```

In the [output data](../incoming.md) description, add one of the fields:

- Field with the `file` type — for uploading one image only. Example:
    ```no-highlight
    {
    "result": {
    "type": "file",
    "required": true
    }
    }
    ```

- Field with the `array_file` type — for uploading several images at once. Example:
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
``` type ``` | Field type: `file-img` — Button for image file upload. | yes | no
``` name ``` | Attribute for the output data field. Contains the output field name. | yes | no
``` sources ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/><br/>The file source.<br/><br/>You can specify multiple values in the `sources="<value 1> <value 2>"` (with a space, without a comma).<br/><br/>Supported values:<br/><br/>- `CAMERA`.<br/>- `GALLERY`.<br/>- `FILE_MANAGER`. | Yes (when creating tasks for mobile devices) | no
``` fileType ``` | {% note info %}<br/><br/>This parameter applies to the tasks completed in the mobile app.<br/><br/>{% endnote %}<br/><br/>File type: `IMAGE`. | Yes (when creating tasks for mobile devices) | no
``` validation-show ``` | The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.<br/><br/>Supported values:<br/><br/>- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.<br/>    <br/>- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.<br/>    <br/>- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.<br/>    <br/>- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.<br/>    <br/>- Don't display the message (`"false"`). | no | ``` "top-left" ```
``` preview ``` | Displaying an image preview after image file upload:<br/><br/>- `preview=true` — Display an image preview.<br/>    <br/>- `preview=false` — Don't display an image preview. | no | ``` true ```
``` camera ``` | Open the camera when the image upload button is clicked:<br/><br/>- `camera=true` — Open camera.<br/>    <br/>- `camera=false` — Don't open camera. | no | ``` false ```
``` compress ``` | Image compression:<br/>- `compress=true` — Reduce the shorter side to 1000 pixels. The image is saved in the JPEG format with a quality level of 90.<br/>    <br/>- `compress=false` — Leave image without changes. | no | ``` true ```
``` requiredCoordinates ``` | Whether coordinates should be required in the image data.<br/>- `requiredCoordinates=true` — Coordinates should be required.<br/>    <br/>- `requiredCoordinates=false` — Coordinates should not be required. | no | ``` false ```
``` multipleSelect ``` | The number of files to download at the same time.<br/>For the single file upload, set the value to `false`.<br/><br/>For upload of multiple files:<br/><br/>1. Set the value to `true`.<br/>1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).

{% include [contact-support](../../_includes/contact-support-help.md) %}