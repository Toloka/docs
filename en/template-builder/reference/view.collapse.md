# view.collapse

Expandable block.

Lets you add hidden content that doesn't need to be shown initially or that takes up a large space.

The block heading is always visible.

If you set the `defaultOpened` property to `true`, the block is expanded immediately, but it can be collapsed.

## Component properties {#properties}

| Name                                        | Type                                                                                   | Description                                                                                                          |
| ------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>    | "view.collapse"                                                                        | <p>Set component type</p>                                                                                            |
| `label`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Block heading.</p>                                                                                                |
| `content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Content hidden in the block.</p>                                                                                  |
| `defaultOpened`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>If `true`, the block is immediately displayed in expanded form. By default, `false` (the block is collapsed).</p> |
| `hint`                                      | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                    |
| `validation`                                | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                |
