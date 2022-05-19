# @yandex-toloka/condition.distance

This component checks whether the sent coordinates match the ones that you specified.

For example, you want the user to take a photo of a specific place. The `condition.distance` component checks whether the photo was taken at the location that you specified.

The device coordinates are sent using the [data.location](data.location.md) component. You can use it without `condition.distance` if you need to read the user's device coordinates without comparing them to the specified ones.

[View example in the sandbox](https://clck.ru/asSxk).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                               |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "@yandex-toloka/condition.distance"                                              | <p>Set component type</p>                                                                 |
| `from`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>The coordinates that will be compared to the coordinates from the `to` property.</p>   |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Validation error message that the user will see</p>                                    |
| `max`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a> | <p>The distance in meters by which the specified and sent coordinates may differ.</p>     |
| `to`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>The coordinates that will be compared to the coordinates from the `from` property.</p> |
