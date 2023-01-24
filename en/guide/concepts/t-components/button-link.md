# Button with click validation

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button with click validation in [Template Builder](../../../template-builder/operations/internet-search.md#action.open-link).

{% endnote %}

If a task requires a Toloker to click a link (for example, to open a webpage), Toloka can check if the Toloker did it. The link is displayed in the task as a button.

Variations of button use:

- Checking if the Toloker opened a link. The [output data](../../../glossary.md#input-output-data) will contain a field with values `true` (the Toloker opened the link) or `false` (the Toloker didn't open the link).

- Preventing the Toloker from completing the task if the link was not opened. Add the `"allowed_values":[true]` parameter in the output data description.

To add the button with the link to the [task interface](../../../glossary.md#task-interface), use the `{{field type="button-clicked" name="output field name>"}}` component. Example:

```plaintext
{{field type="button-clicked" name="ads" label="Click me" href="https://yandex.ru" action=true}}
```

For a complete list of parameters, see the [table](#parameters).

Add a field of `Boolean` type to the output data description. To prevent the Toloker from sending responses without opening the link, add the `"allowed_values":[true]` parameter.

```json
{
  "ads": {
    "type": "boolean",
    "required": true,
    "allowed_values": [true]
  }
}
```

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`type`| Field type: `button-clicked` — button with click validation. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`label`| Button text. Example: `label="Click me"`. | no | no||
||`href`| URL that the Toloker must open to complete the task. | no | no||
||`size`| Size of the field.

Supported values: `"S"`, `"M"`, `"L"`, `"XL"`. | no | `"L"`||
||`action`| Button color:

- `action=true` — Yellow.

- `action=false` — White. | no | `false`||
|#

{% include [contact-support](../../_includes/contact-support.md) %}