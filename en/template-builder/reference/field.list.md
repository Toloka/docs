# field.list

A component that allows the user to add and remove list items, such as text fields to fill in.

This way you can allow the user to give multiple answers to a question.

[View example in the sandbox](https://clck.ru/asSUJ).

The list items can contain any component, including a list of other components. For example, this allows you to create a table where you can add and delete rows.

[View example in the sandbox](https://clck.ru/asSUq).

## Managing components

To add a new list item, the user clicks the button. To remove an item, they click on the x on the right (it appears when hovering over a list item).

To prevent the user from adding too many list items, set the maximum list length. You can also use the `editable` property to block users from changing a component, like when a certain event occurs.

## Component properties {#properties}

| Name                                       | Type                                                                                   | Description                                                                                                                                                                                               |
| ------------------------------------------ | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>   | "field.list"                                                                           | <p>Set component type</p>                                                                                                                                                                                 |
| `data`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>                                                                                                                                                |
| `label`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                                                                                         |
| `buttonLabel`                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Text on the button for adding list items.</p>                                                                                                                                                          |
| `direction`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>The direction of the list:</p><ul><li>`vertical` (default).</li><li>`horizontal`</li></ul>                                                                                                             |
| `editable`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>A property that indicates whether adding and removing list items is allowed. Set `false` to disable. By default it is `true` (allowed). </p>                                                           |
| `hint`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                                                                                         |
| `maxLength`                                | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Maximum number of list items.</p>                                                                                                                                                                      |
| `render`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Interface template for list items, such as a text field.</p><p>In nested `field.*` components, use `data.relative` for recording responses, otherwise all the list items will have the same value.</p> |
| `size`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>The distance between list items. Acceptable values in ascending order: `s`, `m` (default).</p>                                                                                                         |
| `validation`                               | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                                                                     |
