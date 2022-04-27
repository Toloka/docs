# view.video

Player for video playback.

The player is a rectangular block with a frame and buttons to control the video. You can set the block size using the `ratio`, `fullHeight`, `minWidth`, and `maxWidth` properties.

The video resolution does not affect the size of the block — the video will fit into the block and will not be cropped.

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                                                                                                                |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "view.video"                                                                           | <p>Set component type</p>                                                                                                                  |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                          |
| `fullHeight`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels.</p>                  |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                          |
| `maxWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Maximum width of the element in pixels, must be greater than `minWidth`.</p>                                                            |
| `minWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Minimum width of the element in pixels. Takes priority over `maxWidth`.</p>                                                             |
| `ratio`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>The aspect ratio of the video block. An array of two numbers: the first sets the width of the block and the second sets the height.</p> |
| `ratio[]`                                | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Relative size of one side.</p>                                                                                                          |
| `url`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Link to the video file.</p>                                                                                                             |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                      |
