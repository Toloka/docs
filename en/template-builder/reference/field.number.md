# field.number

A component that allows the user to enter a number.

Only numbers and decimal separators can be entered in the field. The user can enter a dot or a comma as a separator, but the dot is always used in the output.

When the user enters a number, the separator automatically changes to the one specified in the regional settings. For Russia, the separator is a comma.

You can also set up validation, for example, disable negative or fractional numbers. [Learn more](../operations/components-for-numbers.dita).

## Component properties {#properties}

| Name                                     | Type           | Description                                                                |
| ---------------------------------------- | -------------- | -------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.number" | <p>Set component type</p>                                                  |
| `data`<span style="color: red">\*</span> | _writable_     | <p>Data with values that will be processed or changed.</p>                 |
| `label`                                  | _string_       | <p>Label above the component.</p>                                          |
| `hint`                                   | _string_       | <p>Hint text.</p>                                                          |
| `maximum`                                | _integer_      | <p>Maximum number that can be entered.</p>                                 |
| `minimum`                                | _integer_      | <p>Minimum number that can be entered.</p>                                 |
| `placeholder`                            | _string_       | <p>A semi-transparent label that is shown in the box when it is empty.</p> |
| `validation`                             | _condition_    | <p>Validation based on condition.</p>                                      |
