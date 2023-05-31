# action.open-close

This component changes the display mode of another component by opening or closing it. What happens to the component depends on the type of component:

- [view.image](view.image.md) — expands the image to full screen.
- [view.collapse](view.collapse.md) — expands or collapses a collapsible section of content.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/5rw-rEtC3tzAcs)

{% cut "Components used in the example" %}

- [layout.sidebar](layout.sidebar.md): Lets you place the main content block and an adjacent panel with controls on a page.
- [view.list](view.list.md): Displays data in a list.
- [view.collapse](view.collapse.md): Displays an expandable block.
- [view.text](view.text.md): Displays a text.
- [view.image](view.image.md): Displays an image.
- [view.action-button](view.action-button.md): Displays a button that calls an action.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.open-close" | Set component type. ||
|| `view` | _ref_ | Points to the component to perform the action with. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
