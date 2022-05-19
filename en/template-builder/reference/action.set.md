# action.set

Sets the value from `payload` in the data in the `data` property.

[Learn more about working with data](../operations/work-with-data.dita).

For example, let's say you want to add shortcuts for the [field.radio-group](field.radio-group.md) option. You need the shortcut to perform the same action as the selected option, which is to set the specified value in the data. To set this action, use `action.set`.

[View example in the sandbox](https://clck.ru/asRw2).

As another example, you can use this component to count the number of clicks on an option and write the value in the output data. When the page is refreshed, set the value to 0.

[View example in the sandbox](https://clck.ru/asRwg).

## Component properties {#properties}

| Name                                     | Type                                                                                 | Description                                                |
| ---------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "action.set"                                                                         | <p>Set component type</p>                                  |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a> | <p>Data with values that will be processed or changed.</p> |
| `payload`                                | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>           | <p>The value to write to the data.</p>                     |
