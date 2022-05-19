# view.link-group

Puts links into groups.

The most important link in a group can be highlighted with a border: set the `theme` property to `primary` for this link.

This only groups links, unlike [view.group](view.group.md).

[View example in the sandbox](https://ya.cc/t/M1VwlI_RHZNkC).

## Component properties {#properties}

| Name                                                | Type                                                                                   | Description                                                                                                                       |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "view.link-group"                                                                      | <p>Set component type</p>                                                                                                         |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                 |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                 |
| `links`<span style="color: red">\*</span>           | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Array of links that make up a group.</p>                                                                                       |
| `links[]`                                           | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Link parameters.</p>                                                                                                           |
| `links[].content`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Link text that's displayed to the user. Unviewed links are blue and underlined, and clicked links are purple.</p>              |
| `links[].theme`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Defines the appearance of the link. If you specify `"theme": "primary"`, it's a button, otherwise it's a text link.</p>        |
| `links[].url`<span style="color: red">\*</span>     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Link address. Inserts a link with the search query when <a href="helper.search-query.md">helper. search-query</a> is used.</p> |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                             |
