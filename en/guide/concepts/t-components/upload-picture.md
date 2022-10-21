# Button for image file upload

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button for uploading images in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.media-file.md){% endif %}.

{% endnote %}

To add an image upload button ![](../../_images/other/b-image-button.png) to the task, use the `{{field type= "file-img" name="<[output field](../incoming.md) name> "sources="<sources parameter>" fileType="<fileType parameter>"}}`. After the image is uploaded the Toloker will see an icon for image preview. Example:

```plaintext
{{field type="file-img" name="photo" sources="CAMERA" fileType="IMAGE" camera=true}}
```

In the [output data](../incoming.md) description, add one of the fields:

- Field with the `file` type — for uploading one image only. Example:

    ```json
    {
    "result": {
    "type": "file",
    "required": true
    }
    }
    ```

- Field with the `array_file` type — for uploading several images at once. Example:

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
||`type`| Field type: `file-img` — Button for image file upload. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`sources`|

{% note info %}

This parameter applies to the tasks completed in the mobile app.

{% endnote %}

The file source.

You can specify multiple values in the `sources="<value 1> <value 2>"` (with a space, without a comma).

Supported values:

- `CAMERA`.

- `GALLERY`.

- `FILE_MANAGER`. | Yes (when creating tasks for mobile devices) | no||
||`fileType`|

{% note info %}

This parameter applies to the tasks completed in the mobile app.

{% endnote %}

File type: `IMAGE`. | Yes (when creating tasks for mobile devices) | no||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`preview`| Displaying an image preview after image file upload:

- `preview=true` — Display an image preview.

- `preview=false` — Don't display an image preview. | no | `true`||
||`camera`| Open the camera when the image upload button is clicked:

- `camera=true` — Open camera.

- `camera=false` — Don't open camera. | no | `false`||
||`compress`| Image compression:

- `compress=true` — Reduce the shorter side to 1000 pixels. The image is saved in the JPEG format with a quality level of 90.

- `compress=false` — Leave image without changes. | no | `true`||
||`requiredCoordinates`| Whether coordinates should be required in the image data.

- `requiredCoordinates=true` — Coordinates should be required.

- `requiredCoordinates=false` — Coordinates should not be required. | no | `false`||
||`multipleSelect`| The number of files to download at the same time.

For the single file upload, set the value to `false`.

For upload of multiple files:

1. Set the value to `true`.

1. In the output data description, add a field with the `array_file` type or another type of array. | no | `true` (if the output data description contains a field with the `array_file` type or another type of array).||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}