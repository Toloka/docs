# action.rotate

Rotates the specified component by 90 degrees.

By default it rotates to the right, but you can specify the direction in the `payload` property.

[View example in the sandbox](https://clck.ru/asRrg).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "action.rotate"                                                                  | <p>Set component type</p>                                                                  |
| `payload`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Sets the direction of rotation:</p><ul><li>`right` (default).</li><li>`left`.</li></ul> |
| `view`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/ref">ref</a>       | <p>Points to the component to perform the action with.</p>                                 |
