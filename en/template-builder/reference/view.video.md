# view.video

Player for video playback.

The player is a rectangular block with a frame and buttons to control the video. You can set the block size using the `ratio`, `fullHeight`, `minWidth`, and `maxWidth` properties.

The video resolution does not affect the size of the block — the video will fit into the block and will not be cropped.

## Component properties {#properties}

| Name                                     | Type         | Description                                                                                                                                |
| ---------------------------------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "view.video" | <p>Set component type</p>                                                                                                                  |
| `label`                                  | _string_     | <p>Label above the component.</p>                                                                                                          |
| `fullHeight`                             | _boolean_    | <p>If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels.</p>                  |
| `hint`                                   | _string_     | <p>Hint text.</p>                                                                                                                          |
| `maxWidth`                               | _number_     | <p>Maximum width of the element in pixels, must be greater than `minWidth`.</p>                                                            |
| `minWidth`                               | _number_     | <p>Minimum width of the element in pixels. Takes priority over `maxWidth`.</p>                                                             |
| `ratio`                                  | _array_      | <p>The aspect ratio of the video block. An array of two numbers: the first sets the width of the block and the second sets the height.</p> |
| `ratio[]`                                | _number_     | <p>Relative size of one side.</p>                                                                                                          |
| `url`<span style="color: red">\*</span>  | _string_     | <p>Link to the video file.</p>                                                                                                             |
| `validation`                             | _condition_  | <p>Validation based on condition.</p>                                                                                                      |
