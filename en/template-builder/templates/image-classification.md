# Image classification

For this type of project, you can use the  template (). Note that validation, keyboard shortcuts, and task layout are already configured in this example.

#### Components used in the example

- [view.image](../reference/view.image.md): Image.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.
- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

{% note info %}

You can add
{% cut "media files" %}

audio files, videos, images

{% endcut %}

 from your own server, [Yandex.Disk](../reference/helper.proxy.md), or a cloud storage like [Yandex.Cloud]({{ toloka-requester-concepts-yacloud-dita }}), Google Cloud, or Amazon AWS.

{% endnote %}



## What else can be configured {#add-more}

- To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

- To let performers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

- Add keyboard shortcuts to rotate and zoom in images in the [plugin.hotkeys](../reference/plugin.hotkeys.md) configuration.


If these templates don't meet your needs, see other examples in this section.


## Other options for buttons {#mult-ans-options}

Decide whether the performer can select only one or multiple answer options:

#### Multiple options (checkboxes)

If there are several possible answers to the question, use [field.checkbox-group](../reference/field.checkbox-group.md) checkboxes.

#### One option (a radio button)

The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2-4 short answer options.

If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.


## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. For example, it lets the user select correct statements about an image only if the image loaded.


## Image and search query comparison {#search}

#### Does the image match the search query

Add a button that opens the search results and generate a search query link using the [helper.search-query](../reference/helper.search-query.md) component. To make sure that the performer clicked on the link and checked its contents, configure validation, as in the example.

#### Side-by-side image and web page comparison

You can display the web page in the built-in window using the [view.iframe](../reference/view.iframe.md) component. Place the image next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

#### Side-by-side image and mobile web page comparison

This is a more complex example that compares the image with the results of a search query. The following components are added:

- [view.iframe](../reference/view.iframe.md): Displays the web page in an embedded window.
- [view.device-frame](../reference/view.device-frame.md): Wraps the window in a smartphone frame.
- [layout.side-by-side](../reference/layout.side-by-side.md): Places the image and the search results window next to each other.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
