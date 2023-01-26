# Radio button

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a radio button in [Template Builder](../../../template-builder/reference/field.radio-group.md).

{% endnote %}

To add radio buttons to the task, use the `{{field type="radio" name="<output field name>"}}` component. For example, a set of two radio buttons:

```plaintext
{{field type="radio" name="result" label="Yes" value="Yes" hotkey="1"}}
{{field type="radio" name="result" label="No" value="No" hotkey="2"}}
```

Add a field of `string` type in the [output data description](../incoming.md). Example:

```json
{
  "result": {
    "type": "string",
    "required": true
  }
}
```

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`type`| Field type: `radio` — Radio button. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`label`| Signature. For example, `label="Yes"`. | no | no||
||`value`| The value to pass (written to the output file). | no | no||
||`hotkey`| The shortcut for selecting a value. | no | no||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`checked`| The state of the radio button when the page is displayed:

- `checked=true` — Selected.

- `checked=false` — Deselected. | no | `false`||
||`size`| Size of the field.

Supported values: `"M"`, `"L"`. | no | `"L"`||
||`width`| Width of the field. Set in the following units:

- Pixels. For example, `width="100px"`.

- Percentage of the size of the parent element. For example, `width="100%"`.

You can also use a formula for setting the width. For example, `width="calc(100%-30px)"`. | no | depends on the length of the signature||
||`class`| The CSS class for the field. For example, `class="annotation"`. | no | `".field" ".field_type_radio"`||
|#

{% include [contact-support](../../_includes/contact-support.md) %}