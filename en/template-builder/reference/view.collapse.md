# view.collapse

Expandable block.

Lets you add hidden content that doesn't need to be shown initially or that takes up a large space.

The block heading is always visible.

If you set the `defaultOpened` property to `true`, the block is expanded immediately, but it can be collapsed.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.collapse" | Set component type ||
|| `label`<span style="color: red">\*</span> | _string_ | Block heading. ||
|| `content`<span style="color: red">\*</span> | _view_ | Content hidden in the block. ||
|| `defaultOpened` | _boolean_ | If `true`, the block is immediately displayed in expanded form. By default, `false` (the block is collapsed). ||
|| `hint` | _string_ | Hint text. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
