# Inserting videos

This section describes how [to insert a video](#insert-videos) and [make sure the user viewed it](#condition.played).


## Inserting videos {#insert-video}

To add a video file to the task interface, use the [view.video](../reference/view.video.md) component. In the `url` property, specify a direct link to the file or component that returns the link. To use the link from the input data, use the [data.input](work-with-data.md) component.

If you want to add several videos to a page, see the examples in [Comparing video clips](sbs-video.md).

{% note info %}

You can add
{% cut "media files" %}

audio files, videos, images

{% endcut %}

 from your own server, [Yandex.Disk](../reference/helper.proxy.md), or a cloud storage like [Yandex.Cloud]({{ toloka-requester-concepts-yacloud-dita }}), Google Cloud, or Amazon AWS.

{% endnote %}



## Make sure that the user watched the video {#condition.played}

#### Started watching
To make sure that the user played the video, in the `validation` property use the `condition.played` component.
#### Viewed completely
To make sure that the user viewed the video completely, in the `validation` property use the `condition.played-fully` component.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
