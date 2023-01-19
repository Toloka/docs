# view.link-group

Puts links into groups.

The most important link in a group can be highlighted with a border: set the `theme` property to `primary` for this link.

This only groups links, unlike [view.group](view.group.md).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/rLm1v_pq3tzB5n)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.link-group" | Set component type ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `links`<span style="color: red">\*</span> | _array_ | Array of links that make up a group. ||
|| `links[]` | _object_ | Link parameters. ||
|| `links[].content`<span style="color: red">\*</span> | _string_ | Link text displayed to a Toloker. Unviewed links are blue and underlined, and clicked links are purple. ||
|| `links[].theme` | _string_ | Defines the appearance of the link. If you specify `"theme": "primary"`, it's a button, otherwise it's a text link. ||
|| `links[].url`<span style="color: red">\*</span> | _string_ | Link address. Inserts a link with the search query when [helper. search-query](helper.search-query.md) is used. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
