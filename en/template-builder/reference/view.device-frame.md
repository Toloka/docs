# view.device-frame

Wraps the content of a component in a frame that is similar to a mobile phone. You can place other components inside the frame.

## Component properties {#properties}

| Name                                     | Type                | Description                                                                                                                                                             |
| ---------------------------------------- | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.device-frame" | <p>Set component type</p>                                                                                                                                               |
| `label`                                  | _string_            | <p>Label above the component.</p>                                                                                                                                       |
| `content`                                | _view_              | <p>Content inside the frame.</p>                                                                                                                                        |
| `fullHeight`                             | _boolean_           | <p>If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels.</p>                                               |
| `hint`                                   | _string_            | <p>Hint text.</p>                                                                                                                                                       |
| `maxWidth`                               | _number_            | <p>Maximum width of the element in pixels, must be greater than `minWidth`.</p>                                                                                         |
| `minWidth`                               | _number_            | <p>Minimum width of the element in pixels. Takes priority over `maxWidth`.</p>                                                                                          |
| `ratio`                                  | _array_             | <p>An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).</p><p>Not valid if `"fullHeight": true`.</p> |
| `ratio[]`                                | _number_            | <p>Relative size of one side.</p>                                                                                                                                       |
| `validation`                             | _condition_         | <p>Validation based on condition.</p>                                                                                                                                   |
