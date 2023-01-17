# view.map

Adds a map to your task.

Use this component to set the targets for the tasks with the markers, select the areas with polygons. Specify the position and colors for the elements on the map.

You can set the following map properties: scale, position of the map center, label, and hint for Tolokers.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/sVwUCmig3tz5fk)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.map" | Set component type ||
|| `label` | _string_ | Label above the component. ||
|| `center`<span style="color: red">\*</span> | _string_ | Determines the position of the map center. Specify the coordinates in the string format, for example, "29.748713,-95.404287", or use the [data.location](data.location.md) component to set the center of the map to the Toloker's current position. ||
|| `hint` | _string_ | Hint text. ||
|| `markers` | _array_ | Specifies the markers present on the map. ||
|| `markers[]` | _object_ | The list of the markers set on the map. ||
|| `markers[].color` | _string_ | Determines the marker color. Use the hexadecimal values preceded by the `#` sign to specify the color. ||
|| `markers[].label` | _string_ | The label for the marker that tells Tolokers what this marker is for and helps distinguish it from other markers. ||
|| `markers[].position`<span style="color: red">\*</span> | _string_ | Determines the marker position. Specify the coordinates in the string format, for example, "29.748713,-95.404287", or use the [data.location](data.location.md) component to set the marker to the Toloker's current position. ||
|| `polygons` | _array_ | Specifies the polygonal objects that you can use to select areas on the map. ||
|| `polygons[]` | _object_ | The list of the polygonal selection areas on the map. ||
|| `polygons[].color` | _string_ | Determines the polygonal selection area color. Use the hexadecimal values preceded by the `#` sign to specify the color. ||
|| `polygons[].points` | _array_ | The list of the polygonal selection area points. ||
|| `polygons[].points[]` | _string_ | Determines the position and shape of the polygonal selection areas. Specify the coordinates in the string format, for example, "29.748713,-95.404287". ||
|| `validation` | _condition_ | Validation based on condition. ||
|| `zoom` | _integer_ | The map initial scale. Use the values from `0` to `19`. Bigger values give a more detailed map view. ||
|#
