# Working with data

To work with data, use the components with the type `data.*`:

- `data.input`: The input data. For example, links to images that will be shown to users. In the Template Builder sandbox, you can set an example of input data.
- `data.output`: The output data. This is what you get when you click the **Send** button.
- `data.internal`: The data available only from within the task. This data is not saved to the results. Use this data to calculate or store intermediate values.
- `data.local`: The local data available only from inside the component. This data is used in some auxiliary components, such as [helper.transform](../reference/helper.transform.md).
- `data.relative`: A special component for saving data. It's only available in the [field.list](../reference/field.list.md) component.


## List of properties {#properties}

The list of properties is the same for all components.

#|
||**Title**|**Type**|**Overview**||
||`type`|{% cut "string" %}

A string enclosed in quotation marks. For example: `"Hello world"`.

{% endcut %}|Name of the component.||
||`path`|{% cut "string" %}

A string enclosed in quotation marks. For example: `"Hello world"`.

{% endcut %}|Path to the property containing data. Dots are used as separators: `path.to.some.element`

To specify the path to the array element, specify its sequence number starting from zero, for example: `items.0`||
||`default`|{% cut "any" %}

Any value. Those might be:
- Standard JSON elements: string, number, `true`, `false`, object, or array.
- [Helpers](../reference/helpers.md) that return a value.
- Other components, if allowed in the configuration.
- References to other places in the configuration using the structure `{ "$ref": "path.to.element" }`. Use this type of linking for [code reuse](../best-practices/reuse.md).

{% endcut %}|The value to use as the default data.
This value will be shown in the interface, so it might hide some placeholders, for example, in the [field.text](../reference/field.text.md) component.||
|#

## What's next {#concept_esd_q1h_ymb}

- [See examples of reading and writing data](input-output-data.md).
- [Read about creating specifications in Toloka](create-specs.md).
- [Learn how to clear the entered data](clear-data.md).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
