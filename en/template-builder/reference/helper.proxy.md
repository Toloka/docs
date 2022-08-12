# @yandex-toloka/helper.proxy

You can use this component to download files from Yandex Disk.

To use `@yandex-toloka/helper.proxy`, connect Yandex Disk to your Toloka account and add the proxy by following [the instructions](https://toloka.ai/docs/guide/concepts/prepare-data.html).

Select the component that you want to add, such as [view.image](view.image.md) for an image or [view.audio](view.audio.md) for an audio file. In the `url` property of this component, select the `@yandex-toloka/helper.proxy` type.

[![image](../_images/buttons/view-example.svg)](https://clck.ru/SVRpe)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/helper.proxy" | Set component type ||
|| `path`<span style="color: red">\*</span> | _string_ | Path to the file in the `/<Proxy name>/<File name>.<type>` format ||
|#
