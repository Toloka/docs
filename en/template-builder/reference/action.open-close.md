# action.open-close

This component changes the display mode of another component by opening or closing it. What happens to the component depends on the type of component:

- [view.image](view.image.md) — expands the image to full screen.
- [view.collapse](view.collapse.md) — expands or collapses a collapsible section of content.

[View example in the sandbox](https://clck.ru/Rf2c3).

## Component properties {#properties}

| Name                                     | Type                                                                       | Description                                                |
| ---------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "action.open-close"                                                        | <p>Set component type</p>                                  |
| `view`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/ref">ref</a> | <p>Points to the component to perform the action with.</p> |
