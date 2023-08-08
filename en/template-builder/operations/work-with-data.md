# Working with data

To work with data, use the components with the `data.*` type. These include both core components and [special data components](../reference/datas.md).

## Core components

Core components are a part of other components which are used for accessing data from task files, Toloker responses, or internal data.

The core components include:

- `data.input`: The input data. For example, links to images that will be shown to Tolokers. In the Template Builder sandbox, you can set an example of input data.

- `data.output`: The output data. This is what you get when a Toloker clicks the **Submit** button.

- `data.internal`: The data available only from within the task. This data is not saved to the results. Use this data to calculate or store intermediate values.

- `data.local`: The local data available only from inside the component. This data is used in some auxiliary components, such as [helper.transform](../reference/helper.transform.md).

- `data.relative`: A special component for saving data. It's only available in the [field.list](../reference/field.list.md) component.

### Component properties {#properties-core}

The list of properties is the same for all core components.

#|
||**Title**|**Type**|**Overview**||
||`type`|[string](*string)|Name of the component.||
||`path`|[string](*string)|Path to the property containing data. Dots are used as separators: `path.to.some.element`

To specify the path to the array element, specify its sequence number starting from zero, for example: `items.0`||
||`default`|[any](*any)|The value to use as the default data.

This value will be shown in the interface, so it might hide some placeholders, for example, in the [field.text](../reference/field.text.md) component.||
|#

## Special data components

Special data components send or return some data which is specific to Toloka and can be used, for example, to track some of the Toloker activities or the labeling progress.

The special data components include:

- [data.assignment-id](../reference/data.assignment-id.md): This component returns the assignment ID.

- [data.location](../reference/data.location.md): This component sends the device coordinates.

Refer to each component page for more details on component properties and usage examples.

### Component properties {#properties-special}

Special data components have only `type` property.

#|
||**Title**|**Type**|**Overview**||
||`type`|[string](*string)|Name of the component.||
|#

## What's next {#concept_esd_q1h_ymb}

- [See examples of reading and writing data](input-output-data.md).
- [Read about creating specifications in Toloka](create-specs.md).
- [Learn how to clear the entered data](clear-data.md).

{% include [contact-support](../_includes/contact-support.md) %}

[*string]: A string enclosed in quotation marks. For example: `"Hello world"`.
[*any]: {% include [any-type](../_includes/any-type.md) %}