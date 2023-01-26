# Image classification

For this type of project, you can use the **Image classification** preset. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/EmabzTqA3ttFVs)

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.
- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## What else can be configured {#add-more}

- To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/VfAHjs2V3ttFWX)

- To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/iMo8AGit3ttFWz)

- Add keyboard shortcuts to rotate and zoom in images in the [plugin.hotkeys](../reference/plugin.hotkeys.md) configuration.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/gLh9ufLx3ttFXM)

If this preset doesn't meet your needs, see other examples in this section.

## Other options for buttons {#mult-ans-options}

Decide whether a Toloker can select only one or multiple answer options:

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers to the question, use [field.checkbox-group](../reference/field.checkbox-group.md) checkboxes.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/KUpCR4gj3ttFY7)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/BQPuzqRh3ttFYX)

{% endlist %}

## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. For example, it lets a Toloker select correct statements about an image only if the image is loaded.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RbqyYj2-3ttFYz)

## Image and search query comparison {#search}

### Does the image match the search query

Add a button that opens the search results and generate a search query link using the [helper.search-query](../reference/helper.search-query.md) component. To make sure that a Toloker clicked on the link and checked its contents, configure validation, as in the example.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/h9tN8XX73ttFZm)

### Side-by-side image and web page comparison

You can display the web page in the built-in window using the [view.iframe](../reference/view.iframe.md) component. Place the image next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/na-qel_u3ttFbf)

### Side-by-side image and mobile web page comparison

This is a more complex example that compares the image with the results of a search query. The following components are added:

- [view.iframe](../reference/view.iframe.md): Displays the web page in an embedded window.
- [view.device-frame](../reference/view.device-frame.md): Wraps the window in a smartphone frame.
- [layout.side-by-side](../reference/layout.side-by-side.md): Places the image and the search results window next to each other.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/K7CBlPlT3ttFdJ)

## See also {#see-also}

- [Tutorials — image classification](../../guide/tutorials/image-classification.md)

{% include [contact-support](../_includes/contact-support.md) %}