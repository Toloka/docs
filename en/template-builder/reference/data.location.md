# @toloka/data.location

This component sends the device coordinates.

To get the coordinates, add type `@yandex-toloka/data.location` to the property of the desired component.

To find out if the transmitted coordinates match the ones that you specified, use the [condition.distance](condition.distance.md) component. Add `@yandex-toloka/data.location` to the `to` or `from` properties, depending on how you want to compare the coordinates.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/HFMC2_XU3y3Tps)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@toloka/data.location" | Set component type. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
