# Inserting videos

This section describes how [to insert a video](#insert-videos) and [make sure the user viewed it](#condition.played).


## Inserting videos {#insert-video}

To add a video file to the task interface, use the [view.video](../reference/view.video.md) component. In the `url` property, specify a direct link to the file or component that returns the link. To use the link from the input data, use the [data.input](work-with-data.md) component.

If you want to add several videos to a page, see the examples in [Comparing video clips](sbs-video.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQCuAJwA2bKqNqMWbPDwCGdVZzhQmYukJGi8TdQAtlBOHwEhDOAL41D9zPZCCQ23XRRp0EwzxefgtTOjomAGdkAHoY+CkiAFoiAA9VAFsmRMikyAzOBDg6UzEAIy0IGLFsiFUeSJiAJgAGAEYAdhiWgBZ4uESAfTTM7KJBgFkABR7BgDYelsGAZgmAcU4snrx-VxB7IA).

## Make sure that the user watched the video {#condition.played}

{% list tabs %}

- Started watching

  To make sure that the user played the video, in the `validation` property use the `condition.played` component.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQA2AQwBGRMWzwAVAE4MsYMXDABrOFARYAygFcpAWzh0scU6aI84EurNUkLACwhHLAZzoSldLr6dG5EWLz8nEIiNHhGSnIotG50dEzeyAD0mfBiRAC0RAAeEqZMed75kKacCO4mnHAQmUblEBI83pkATAAMAIwA7Jm9ACw5cHkA+sWl5URTALIACqNTAGyjvVMAzIsA4pxlo9HUOHj4Eho8jk1QbFSi5-TMrEl4kFD2gdCc5RIMOynJ7JXR0eQgACaniwUCIdiwdAgWF8-ksITCEWR-0BSjwMRwAF8YsSoISQIIQLomF4UGhyYSgA).

- Viewed completely

  To make sure that the user viewed the video completely, in the `validation` property use the `condition.played-fully` component.

  [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0hAJkRHgA0mGrQA2AQwBGRMWzwAVAE4MsAZzoSldOFARY6ACyJZe-LBKg8sYMXDABrXfoDKAVykBbOHSwkfhhBuviQSdGCGzlg+WG5QOmIGxlhEVpxCIjR4bkpyKLSGdHRMasgA9GXwYkQAtEQAHhKeTNVqNZCenAgBHpxwEGVuLRASPGplAEwADACMAOxlUwAslXDVAPoNTS1E6wCyAApL6wBsS1PrAMx7AOKczUsZ1Dh4+BJ2PGH9UGxUoi-0ZisfJ4SBWHzfTgtCQMIg8GowNxiMQMJ7-Aq6OjyEAATSCWCgRDhBggfjCESSJjMpNscCYsXia0pKSseEyOAAvpkuVAOSBBCBdExgig0HyOUA).

{% endlist %}

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
