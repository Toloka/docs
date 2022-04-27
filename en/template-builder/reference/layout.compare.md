# layout.compare

Use it to arrange interface elements for comparing them. For example, you can compare several photos.

Selection buttons can be placed under each of the compared items. You can also add common elements, such as a field for comments.

[View example in the sandbox](https://clck.ru/asSjd).

Differences from [layout.side-by-side](layout.side-by-side.md):

- No buttons for hiding items. These are useful if you need to compare 5 photos at once and it's difficult to choose between two of them.
- You can add individual selection buttons for every item being compared.

## Component properties {#properties}

| Name                                      | Type                                                                                   | Description                                                                                                                                                                                                                                    |
| ----------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>  | "layout.compare"                                                                       | <p>Set component type</p>                                                                                                                                                                                                                      |
| `commonControls`                          | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>The common fields of the component. Add information blocks that are common to all the elements being compared.</p>                                                                                                                          |
| `items`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>An array with properties of the elements being compared. Set the appearance of the component blocks.</p>                                                                                                                                    |
| `items[]`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>The compared element.</p>                                                                                                                                                                                                                   |
| `items[].content`                         | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>The content of the element that's being compared. Add images, audio recordings, videos, links, or other types of data.</p>                                                                                                                  |
| `items[].controls`                        | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Configure the input fields to make the user select an item.</p>                                                                                                                                                                             |
| `minWidth`                                | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Minimum width of the element in pixels. Default: 400 pixels.</p>                                                                                                                                                                            |
| `validation`                              | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                                                                                                          |
| `wideCommonControls`                      | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>This property increases the common field size of the elements being compared.It's set to `false` by default: the common fields are displayed in the center, not stretched. If `true`, the fields are wider than with the default value.</p> |
