# Drop-down list

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a drop-down list in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.select){% endif %}.

{% endnote %}


To add a dropdown list to the task, use `{{#field type="select" name="<output field [name](../incoming.md)>"}}... {{/field}}`. The entries in the dropdown list are created using the nested expression ``{{select_item}}``. Example:
 {% if locale == "en-com" %}
```no-highlight
{{#field type="select" name="colour" placeholder="Choose a color" width="200px"}}
  {{select_item value="red" text="Red"}}
  {{select_item value="green" text="Green"}} {{/field}}
```
{% endif %}
Add a `string` field to the [output data description](../../../glossary.md#input-output-data-ru).

```no-highlight
{
  "colour": {
    "type": "string",
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
``` type ``` | Field type: `select` — Dropdown list. | yes | no
``` name ``` | Attribute for the output data field. Contains the output field name. | yes | no
``` placeholder ``` | The name of the dropdown list in the interface. | no | no
``` width ``` | Width of the field. Set in the following units:<br/><br/>- Pixels. For example, `width="100px"`.<br/>    <br/>- Percentage of the size of the parent element. For example, `width="100%"`.<br/>    <br/><br/>You can also use a formula for setting the width. For example, `width="calc(100%-30px)"`. | no | depends on the length of the signature
``` validation-show ``` | The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.<br/><br/>Supported values:<br/><br/>- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.<br/>    <br/>- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.<br/>    <br/>- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.<br/>    <br/>- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.<br/>    <br/>- Don't display the message (`"false"`). | no | ``` "top-left" ```
``` size ``` | Size of the field.<br/><br/>Supported values: `"S"`, `"M"`, `"L"`. | no | ``` "L" ```
``` class ``` | The CSS class for the field. For example, `class="annotation"`. | no | ``` ".field" ".field_type_select" ```
``` disabled ``` | Whether data can be edited:<br/><br/>- `disabled=true` — Non-editable field.<br/>    <br/>- `disabled=false` — Editable field. | no | ``` false ```
``` mode ``` | Direction to expand the list:<br/><br/>- `mode="dropdown"` — Down.<br/>    <br/>- `mode="dropup"` — Up. | no | ``` "dropdown" ```
``` value ``` | Text to write to the output data file if the item is selected. | no | no
``` text ``` | The name of the list item. | no | no
``` selected ``` | The item selected by default:<br/><br/>- `selected=true` — Make item selected by default.<br/>    <br/>- `selected=false` — Leave item deselected by default. | no | ``` false ```

{% include [contact-support](../../_includes/contact-support-help.md) %}