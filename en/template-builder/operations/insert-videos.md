# Inserting videos

This section describes how [to insert a video](#insert-videos) and [make sure the Toloker viewed it](#condition.played).


## Inserting videos {#insert-video}

To add a video file to the task interface, use the [view.video](../reference/view.video.md) component. In the `url` property, specify a direct link to the file or component that returns the link. To use the link from the input data, use the [data.input](work-with-data.md) component.

If you want to add several videos to a page, see the examples in [Comparing video clips](sbs-video.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ArTxPxvp3Yb7Tu)

## Make sure that the Toloker watched the video {#condition.played}

{% list tabs %}

- Started watching

  To make sure that the Toloker played the video, in the `validation` property use the `condition.played` component.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/TpsvNGHw3Yb7y5)

- Viewed completely

  To make sure that the Toloker viewed the video completely, in the `validation` property use the `condition.played-fully` component.

  [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/AXwEoWDF3Yb8PN)

{% endlist %}

{% include [contact-support](../_includes/contact-support.md) %}