# String input field

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a string input field in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.text.md){% endif %}.

{% endnote %}

To add a string input field to the task, use the `{{field type="input" name="<output field> name"}}` component. Example:

{% if locale == "en-com" %}

```plaintext
{{field type="input" name="result" placeholder="Enter a word" validation-show="right-center"}}
```

{% endif %}

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
||`type`| Field type: `input` — String input field. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`value`| A string to be recorded in the output data file by default. | no | no||
||`width`| Width of the field. Set in the following units:

- Pixels. For example, `width="100px"`.

- Percentage of the size of the parent element. For example, `width="100%"`.

You can also use a formula for setting the width. For example, `width="calc(100%-30px)"`. | no | depends on the browser and font size||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`size`| Size of the field.

Supported values: `"S"`, `"M"`, `"L"`, `"XL"`. | no | `"L"`||
||`disabled`| Whether data can be edited:

- `disabled=true` — Non-editable field.

- `disabled=false` — Editable field. | no | `false`||
||`placeholder`| The prompt text to display in the empty field. | no | no||
||`class`| The CSS class for the field. For example, `class="annotation"`. | no | `".field" ".field_type_input"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}