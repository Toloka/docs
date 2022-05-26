# view.collapse

Expandable block.

Lets you add hidden content that doesn't need to be shown initially or that takes up a large space.

The block heading is always visible.

If you set the `defaultOpened` property to `true`, the block is expanded immediately, but it can be collapsed.

## Component properties {#properties}

| Name                                        | Type            | Description                                                                                                          |
| ------------------------------------------- | --------------- | -------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>    | "view.collapse" | <p>Set component type</p>                                                                                            |
| `label`<span style="color: red">\*</span>   | _string_        | <p>Block heading.</p>                                                                                                |
| `content`<span style="color: red">\*</span> | _view_          | <p>Content hidden in the block.</p>                                                                                  |
| `defaultOpened`                             | _boolean_       | <p>If `true`, the block is immediately displayed in expanded form. By default, `false` (the block is collapsed).</p> |
| `hint`                                      | _string_        | <p>Hint text.</p>                                                                                                    |
| `validation`                                | _condition_     | <p>Validation based on condition.</p>                                                                                |
