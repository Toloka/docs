# view.iframe

Displays the web page at the URL in an iframe window.

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                                                                                                                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.iframe"                                                                          | <p>Set component type</p>                                                                                                                                               |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                                                       |
| `fullHeight`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels.</p>                                               |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                                                       |
| `maxWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Maximum width of the element in pixels, must be greater than `minWidth`.</p>                                                                                         |
| `minWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Minimum width of the element in pixels. Takes priority over `maxWidth`.</p>                                                                                          |
| `ratio`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).</p><p>Not valid if `"fullHeight": true`.</p> |
| `ratio[]`                                | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Relative size of one side.</p>                                                                                                                                       |
| `url`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>URL of the web page.</p>                                                                                                                                             |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                                   |