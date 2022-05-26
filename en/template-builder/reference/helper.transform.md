# helper.transform

Creates a new array by transforming each of the elements in the original array.

For example, you can convert an array of image links to [view.image](view.image.md) components to display these images. This may be useful if the number of images in the array is unknown in advance.

[View example in the sandbox](https://clck.ru/RnsYo).

## Component properties {#properties}

| Name                                     | Type               | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------- | ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "helper.transform" | <p>Set component type</p>                                                                                                                                                                                                                                                                                                                                                                    |
| `into`                                   | _any_              | <p>Template to transform elements in the array. The array value can be substituted using the `data.local` component. To do this, use the construction `{ "type": "data.local", "path": "item"}`. <a href="../operations/work-with-data.dita">Learn more</a>.</p>                                                                                                                             |
| `items`                                  | _array_            | <p>The array that you want to convert. You can specify an array in three ways:</p><ul><li>Specify the array itself. Example: `["one", "two", "three"]`.</li><li>Insert a reference to data (input, output, or internal). Example: `{"type": "data.input", "path": "path.to.data"}`.</li><li>Use a reference to another configuration element. Example: `{"$ref": "vars.myarray"}`.</li></ul> |
| `items[]`                                | _any_              | <p>Array element. This can be any element — strings, numbers, JSON objects, or other arrays. </p><p>If you used a reference to a field with input data, you do not need to also specify the element.</p>                                                                                                                                                                                     |
