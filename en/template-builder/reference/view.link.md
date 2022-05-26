# view.link

Universal way to add a link.

This link changes color when clicked.

We recommend using this component if you need to insert a link without additional formatting.

If you want to insert a button that will open the link, use the [view.action-button](view.action-button.md) and [action.open-link](action.open-link.md) components. [View example in the sandbox](https://clck.ru/asSwj).

To insert a link with a search query, use [helper.search-query](helper.search-query.md). [View example in the sandbox](https://clck.ru/TRCLB).

## Component properties {#properties}

| Name                                     | Type        | Description                             |
| ---------------------------------------- | ----------- | --------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.link" | <p>Set component type</p>               |
| `label`                                  | _string_    | <p>Label above the component.</p>       |
| `content`                                | _string_    | <p>Link text displayed to the user.</p> |
| `hint`                                   | _string_    | <p>Hint text.</p>                       |
| `url`<span style="color: red">\*</span>  | _string_    | <p>Link URL.</p>                        |
| `validation`                             | _condition_ | <p>Validation based on condition.</p>   |
