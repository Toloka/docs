# field.list

A component that allows an annotator to add and remove list items, such as text fields to fill in.

This way you can allow an annotator to give multiple answers to a question.

[View example in the sandbox](https://clck.ru/asSUJ).

The list items can contain any component, including a list of other components. For example, this allows you to create a table where you can add and delete rows.

[View example in the sandbox](https://clck.ru/asSUq).

## Managing components

To add a new list item, annotators click the button. To remove an item, they click on the x on the right (it appears when hovering over a list item).

To prevent an annotator from adding too many list items, set the maximum list length. You can also use the `editable` property to block annotators from changing a component, like when a certain event occurs.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.list" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `addedItems` | _array_ | – ||
|| `addedItems[]` | _view_ | – ||
|| `buttonLabel` | _string_ | Text on the button for adding list items. ||
|| `direction` | _string_ | The direction of the list:

- `vertical` (default).
- `horizontal` ||
  || `editable` | _boolean_ | A property that indicates whether adding and removing list items is allowed. Set `false` to disable. By default it is `true` (allowed). ||
  || `hint` | _string_ | Hint text. ||
  || `maxLength` | _number_ | Maximum number of list items. ||
  || `minLength` | _number_ | – ||
  || `removeVariant` | _string_ | – ||
  || `render`<span style="color: red">\*</span> | _view_ | Interface template for list items, such as a text field.

In nested `field.*` components, use `data.relative` for recording responses, otherwise all the list items will have the same value. ||
|| `size` | _string_ | The distance between list items. Acceptable values in ascending order: `s`, `m` (default). ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
