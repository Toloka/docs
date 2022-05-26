# view.link-group

Puts links into groups.

The most important link in a group can be highlighted with a border: set the `theme` property to `primary` for this link.

This only groups links, unlike [view.group](view.group.md).

[View example in the sandbox](https://ya.cc/t/M1VwlI_RHZNkC).

## Component properties {#properties}

| Name                                                | Type              | Description                                                                                                                       |
| --------------------------------------------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "view.link-group" | <p>Set component type</p>                                                                                                         |
| `label`                                             | _string_          | <p>Label above the component.</p>                                                                                                 |
| `hint`                                              | _string_          | <p>Hint text.</p>                                                                                                                 |
| `links`<span style="color: red">\*</span>           | _array_           | <p>Array of links that make up a group.</p>                                                                                       |
| `links[]`                                           | _object_          | <p>Link parameters.</p>                                                                                                           |
| `links[].content`<span style="color: red">\*</span> | _string_          | <p>Link text that's displayed to the user. Unviewed links are blue and underlined, and clicked links are purple.</p>              |
| `links[].theme`                                     | _string_          | <p>Defines the appearance of the link. If you specify `"theme": "primary"`, it's a button, otherwise it's a text link.</p>        |
| `links[].url`<span style="color: red">\*</span>     | _string_          | <p>Link address. Inserts a link with the search query when <a href="helper.search-query.md">helper. search-query</a> is used.</p> |
| `validation`                                        | _condition_       | <p>Validation based on condition.</p>                                                                                             |
