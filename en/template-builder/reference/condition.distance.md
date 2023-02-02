# @yandex-toloka/condition.distance

This component checks whether the sent coordinates match the ones that you specified.

For example, you want a Toloker to take a photo of a specific place. The `condition.distance` component checks whether the photo was taken at the location that you specified.

The device coordinates are sent using the [data.location](data.location.md) component. You can use it without `condition.distance` if you need to read a Toloker's device coordinates without comparing them to the specified ones.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/knIIN8ge3xEJAH)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/condition.distance" | Set component type ||
|| `from` | _string_ | The coordinates that will be compared to the coordinates from the `to` property. ||
|| `hint` | _string_ | Validation error message that a Toloker will see ||
|| `max` | _number_ | The distance in meters by which the specified and sent coordinates may differ. ||
|| `to` | _string_ | The coordinates that will be compared to the coordinates from the `from` property. ||
|#
