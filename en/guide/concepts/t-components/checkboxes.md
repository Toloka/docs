# Checkbox

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a checkbox in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.checkbox.md){% endif %}.

{% endnote %}

To insert a checkbox in a task, use the `{{field type="checkbox" name="<[output field](../incoming.md)> name"}}` component. For example, a set of three checkboxes:

{% if locale == "en-com" %}

```plaintext
{{field type="checkbox" name="red" label="red" hotkey="1"}}
{{field type="checkbox" name="green" label="green" hotkey="2"}}
{{field type="checkbox" name="yellow" label="yellow" hotkey="3"}}
```

{% endif %}

Add a field of `boolean` type to the [output data description](../incoming.md). Example:

```json
{
  "red": {
    "type": "boolean",
    "required": true
  }
}
```

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`type`| Field type: `checkbox`. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`label`| Signature. For example, `label="Yes"`. | no | no||
||`hotkey`| The shortcut for selecting a value. | no | no||
||`value`| The value to pass (written to the output file).

Supported values: `true`, `false`. | no | `false`||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`checked`| The state of a checkbox when the page is displayed:

- `checked=true` — Checked.

- `checked=false` — Unchecked. | no | `false`||
||`size`| Size of the field.

Supported values: `"M"`, `"L"`. | no | `"L"`||
||`width`| Width of the field. Set in the following units:

- Pixels. For example, `width="100px"`.

- Percentage of the size of the parent element. For example, `width="100%"`.

You can also use a formula for setting the width. For example, `width="calc(100%-30px)"`. | no | depends on the length of the signature||
||`disabled`| Whether data can be edited:

- `disabled=true` — Non-editable field.

- `disabled=false` — Editable field. | no | `false`||
||`class`| The CSS class for the field. For example, `class="annotation"`. | no | `".field" ".field_type_checkbox"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}