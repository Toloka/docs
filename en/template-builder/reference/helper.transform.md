# helper.transform

Creates a new array by transforming each of the elements in the original array.

For example, you can convert an array of image links to [view.image](view.image.md) components to display these images. This may be useful if the number of images in the array is unknown in advance.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/IqTqGpfg3ttBtA)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.transform" | Set component type ||
|| `into` | _any_ | Template to transform elements in the array. The array value can be substituted using the `data.local` component. To do this, use the construction `{ "type": "data.local", "path": "item"}`. [Learn more](../operations/work-with-data.md). ||
|| `items` | _array_ | The array that you want to convert. You can specify an array in three ways:

- Specify the array itself. Example: `["one", "two", "three"]`.
- Insert a reference to data (input, output, or internal). Example: `{"type": "data.input", "path": "path.to.data"}`.
- Use a reference to another configuration element. Example: `{"$ref": "vars.myarray"}`.
  ||
  || `items[]` | _any_ | Array element. This can be any element — strings, numbers, JSON objects, or other arrays.

If you used a reference to a field with input data, you do not need to also specify the element. ||
|#
