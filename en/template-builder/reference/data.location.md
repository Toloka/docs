# data.location

This component sends the device coordinates.

To get the coordinates, add type `@toloka/data.location` to the property of the desired component.

To find out if the transmitted coordinates match the ones that you specified, use the [condition.distance](condition.distance.md) component. Add `@toloka/data.location` to the `to` or `from` properties, depending on how you want to compare the coordinates.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/xyD-vvUV4K8eKb)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [field.media-file](field.media-file.md): Adds buttons for different types of uploads.
- [condition.all](condition.all.md): Checks that all child conditions are met.
- [condition.required](condition.required.md): Checks that the data is filled in.
- [condition.distance](condition.distance.md): Checks whether the sent coordinates match the ones that you specified.
- [plugin.toloka](plugin.toloka.md): Customizes the task layout.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@toloka/data.location" | Set component type. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
