# layout.columns

A component for placing content in columns.

Use it to customize the display of content: set the column width and adjust the vertical alignment of content.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/W-APYFlT3xtrzV)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.columns" | Set component type. ||
|| `fullHeight` | _boolean_ | Switches the component to column mode at full height and with individual scrolling. Otherwise, the height is determined by the height of the column that is filled in the most. ||
|| `items`<span style="color: red">\*</span> | _array_ | Columns to divide the interface into. ||
|| `items[]` | _view_ | Column content. ||
|| `minWidth` | _number_ | The minimum width of the component; if it is narrower, columns are output sequentially, one by one. ||
|| `ratio` | _array_ | An array of values that specify the relative width of columns. For example, if you have 3 columns, the value `[1,2,1]` divides the space into 4 parts and the column in the middle is twice as large as the other columns.

If the number of columns exceeds the number of values in the `ratio` property, the values are repeated. For example, if you have 4 columns and the `ratio` is set to `[1,2]`, the result is the same as for `[1,2,1,2]`.

If the number of columns is less than the number of values in the `ratio` property, extra values are simply ignored. ||
|| `ratio[]` | _number_ | Relative column width. ||
|| `validation` | _condition_ | Validation based on condition. ||
|| `verticalAlign` | _string_ | Vertical alignment of column content:

- `top` — Aligned to the top of a column.
- `middle` — Aligned to the middle of the column that is filled in the most.
- `bottom` — Aligned to the bottom of a column. ||
  |#
