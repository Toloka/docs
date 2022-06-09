# field.image-annotation

Component for image labeling.

The interface lets you select areas using points, rectangles, and polygons. You can use the `shapes` property to configure labeling modes that are available to an annotator.

If you need to categorize selected items, create labels for each category using the `labels` property.

You can disable labeling using the `disabled` property. For example, use this if you need to create a task to check labeled images, or if you want to allow labeling only after a certain [condition](helper.if.md) has been met.

[See example in the sandbox](https://clck.ru/asSTF).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.image-annotation" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | Determines whether adding and deleting areas is allowed:

- `false` (default) — Allowed.
- `true` — Not allowed.

You can use this feature when creating an interface to check whether the selection is correct, or if you need to allow selection only when a certain [condition](../reference/helper.if.md) is met. ||
|| `fullHeight` | _boolean_ | If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels. ||
|| `hint` | _string_ | Hint text. ||
|| `image`<span style="color: red">\*</span> | _string_ | The image you want to select areas in. ||
|| `labels` | _array_ | Labels for classifying areas.

Each array element creates a button in the interface for selecting a label.

If you use labels, you need to add at least two. ||
|| `labels[]` | _object_ | `labels` array area:

- `"label": "button text"`;
- `"value": "value"`.

At least two objects must be added to the array. ||
|| `labels[].label`<span style="color: red">\*</span> | _string_ | Text on the label selection button. ||
|| `labels[].value`<span style="color: red">\*</span> | _string_ | A value that corresponds to the label and is sent in the output. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Takes priority over `maxWidth`. ||
|| `ratio` | _array_ | An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).

Not valid if `"fullHeight": true`. ||
|| `ratio[]` | _number_ | Relative size of one side. ||
|| `shapes` | _object_ | Setting up labeling modes that are available to an annotator.

By default, all three selection modes are available: points, rectangles, and polygons.

Modes with the `true` value are available to an annotator. ||
|| `shapes.point` | _boolean_ | Point selector. ||
|| `shapes.polygon` | _boolean_ | Labeling with polygons. ||
|| `shapes.rectangle` | _boolean_ | Rectangle selector. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
