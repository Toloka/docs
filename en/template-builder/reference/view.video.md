# view.video

Player for video playback.

The player is a rectangular block with a frame and buttons to control the video. You can set the block size using the `ratio`, `fullHeight`, `minWidth`, and `maxWidth` properties.

The video resolution does not affect the size of the block — the video will fit into the block and will not be cropped.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.video" | Set component type ||
|| `label` | _string_ | Label above the component. ||
|| `fullHeight` | _boolean_ | If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels. ||
|| `hint` | _string_ | Hint text. ||
|| `maxWidth` | _number_ | Maximum width of the element in pixels, must be greater than `minWidth`. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Takes priority over `maxWidth`. ||
|| `ratio` | _array_ | The aspect ratio of the video block. An array of two numbers: the first sets the width of the block and the second sets the height. ||
|| `ratio[]` | _number_ | Relative size of one side. ||
|| `url`<span style="color: red">\*</span> | _string_ | Link to the video file. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
