# @toloka/helper.proxy

You can use this component to download files from Yandex Disk.

{% include [yandex-disk-warning](../../_includes/yandex-disk-warning.md) %}

To use `@toloka/helper.proxy`, you must have Yandex Disk connected to your Toloka account and proxy added. See the [instructions](../../guide/concepts/prepare-data.md) for more details.

Select the component that you want to add, such as [view.image](view.image.md) for an image or [view.audio](view.audio.md) for an audio file. In the `url` property of this component, select the `@toloka/helper.proxy` type.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/CGsrA8bO4FAepj)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@toloka/helper.proxy" | Set component type. ||
|| `path`<span style="color: red">\*</span> | _string_ | Path to the file in the `/<Proxy name>/<File name>.<type>` format ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
