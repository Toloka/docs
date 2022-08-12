# @yandex-toloka/data.location

This component sends the device coordinates.

To get the coordinates, add type `@yandex-toloka/data.location` to the property of the desired component.

To find out if the transmitted coordinates match the ones that you specified, use the [condition.distance](condition.distance.md) component. Add `@yandex-toloka/data.location` to the `to` or `from` properties, depending on how you want to compare the coordinates.

[![image](../_images/buttons/view-example.svg)](https://clck.ru/asSxk)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/data.location" | Set component type ||
|#
