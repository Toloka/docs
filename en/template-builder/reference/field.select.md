# field.select

Button for selecting from a drop-down list. Use this component when the list is long and only one option can be chosen.

For short lists (2-4 items), it's better to use [field.radio-group](field.radio-group.md) or [field.button-radio-group](field.button-radio-group.md), where all the options are visible at once.

To allow selecting multiple options, use the [field.checkbox-group](field.checkbox-group.md) component.

## Component properties {#properties}

| Name                                                | Type                                                                                   | Description                                                                |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "field.select"                                                                         | <p>Set component type</p>                                                  |
| `data`<span style="color: red">\*</span>            | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>                 |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                          |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                          |
| `options`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Options to choose from.</p>                                             |
| `options[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Option parameters.</p>                                                  |
| `options[].label`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>The name of the option to display in the list.</p>                      |
| `options[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>             | <p>The value to write to the data in the `data` property.</p>              |
| `placeholder`                                       | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>The text that will be displayed if none of the options is selected.</p> |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                      |
