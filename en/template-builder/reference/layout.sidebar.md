# layout.sidebar

An option for placing _(layout)_ items, which lets you arrange on a page:

- The main content block.
- An adjacent panel with controls.

The `minWidth` property sets the threshold for switching between widescreen and compact modes: when the width of the `layout.sidebar` component itself becomes less than the value set by the `minWidth` property, compact mode is enabled.

In widescreen mode, the control panel is located to the right of the main block.

In compact mode, controls stretch to the entire width and are located under each other.

To add an extra panel with controls, use the `extraControls` property.

## Component properties {#properties}

| Name                                         | Type                                                                                   | Description                                                                                                                                                                          |
| -------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span>     | "layout.sidebar"                                                                       | <p>Set component type</p>                                                                                                                                                            |
| `content`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Content placed in the main area.</p>                                                                                                                                              |
| `controls`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>Content of the control panel.</p>                                                                                                                                                 |
| `controlsWidth`                              | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>The width of the control panel in widescreen mode. In compact mode, the panel takes up the entire available width. Default: 200 pixels.</p>                                       |
| `extraControls`                              | <a class="xref popup-link" href="../concepts/types.dita#types/view">view</a>           | <p>An additional panel with controls. Located below the main panel.</p>                                                                                                              |
| `minWidth`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>The minimum width, in pixels, for widescreen mode. If the component width becomes less than the specified value, the interface switches to compact mode. Default: 400 pixels.</p> |
| `validation`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                                                |
