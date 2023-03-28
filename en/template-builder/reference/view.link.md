# view.link

Universal way to add a link.

This link changes color when clicked.

We recommend using this component if you need to insert a link without additional formatting.

If you want to insert a button that will open the link, use the [view.action-button](view.action-button.md) and [action.open-link](action.open-link.md) components.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/NaCxphQV3xPEYn)

To insert a link with a search query, use [helper.search-query](helper.search-query.md).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/W5KExwg_3vwB57)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.link" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `content` | _string_ | Link text displayed to a Toloker. ||
|| `hint` | _string_ | Hint text. ||
|| `url`<span style="color: red">\*</span> | _string_ | Link URL. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
