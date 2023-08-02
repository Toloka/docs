# Comparing video clips

This section describes how to [compare two videos](#video-side-by-side), how to make them [start and pause simultaneously](#same-time-video), and how to put [multiple videos on a page](#compare-more-video).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Two videos side-by-side {#video-side-by-side}

To place two videos next to each other, you can use the [layout.side-by-side](../reference/layout.side-by-side.md) component. Add components with video ([view.video](../reference/view.video.md)) to the `items` property, and fields for responses to the `controls` property.

{% note info %}

Unlike other components, [layout.side-by-side](../reference/layout.side-by-side.md) has options allowing you to hide or display any of the elements in `items`.

{% endnote %}

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/pu9bV4003ttCMs)

Instead of [layout.side-by-side](../reference/layout.side-by-side.md), you can use other components, for example:

- [view.list](../reference/view.list.md): A list of any elements, vertical or horizontal.

- [layout.columns](../reference/layout.columns.md): A set of horizontal columns that you can put the videos in. As opposed to [view.list](../reference/view.list.md), this component provides more options for column width setup.

## Parallel playback of two videos {#same-time-video}

You can sync playback and pause for both videos.

To do this, add a button ([view.action-button](../reference/view.action-button.md)) that will trigger the [action.play-pause](../reference/action.play-pause.md) action for both videos. To call two actions using one button (for each video), use the [action.bulk](../reference/action.bulk.md) component.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/-9UsIJDN3ttCPr)

You can also trigger playback using a hotkey. The button's shortcut will be shown on the button label.

Use [plugin.hotkeys](../reference/plugin.hotkeys.md) for this. To assign a shortcut to the button, do the same thing with the shortcut.

{% note tip %}

To call the same action from different parts of the code, put it in a separate variable inside `vars`. Then reference this variable using the `$ref` structure. For more information, see [Reuse code](../best-practices/reuse.md).

{% endnote %}

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/YErQ-Pd93ttCRm)

## Compare multiple videos {#compare-more-video}

In the examples below, you can add as many video components as you like using the `items` property.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ROoWiLNY3ttCSc)

If you want to add multiple videos that a Toloker doesn't have to view at the same time, position them vertically using the [view.list](../reference/view.list.md) component. To make sure that the response selection buttons don't get lost, use the [layout.sidebar](../reference/layout.sidebar.md) component.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ycaNgDNe3ttCUM)

{% include [contact-support](../_includes/contact-support.md) %}