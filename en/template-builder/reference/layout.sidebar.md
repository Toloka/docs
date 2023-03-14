# layout.sidebar

An option for placing _(layout)_ items, which lets you arrange on a page:

- The main content block.
- An adjacent panel with controls.

The `minWidth` property sets the threshold for switching between widescreen and compact modes: when the width of the `layout.sidebar` component itself becomes less than the value set by the `minWidth` property, compact mode is enabled.

In widescreen mode, the control panel is located to the right of the main block.

In compact mode, controls stretch to the entire width and are located under each other.

To add an extra panel with controls, use the `extraControls` property.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/NrCQ0fS844To7d)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.sidebar" | Set component type ||
|| `content`<span style="color: red">\*</span> | _view_ | Content placed in the main area. ||
|| `controls`<span style="color: red">\*</span> | _view_ | Content of the control panel. ||
|| `controlsWidth` | _number_ | The width of the control panel in widescreen mode. In compact mode, the panel takes up the entire available width. Default: 200 pixels. ||
|| `extraControls` | _view_ | An additional panel with controls. Located below the main panel. ||
|| `minWidth` | _number_ | The minimum width, in pixels, for widescreen mode. If the component width becomes less than the specified value, the interface switches to compact mode. Default: 400 pixels. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
