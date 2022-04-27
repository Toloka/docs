# @yandex-toloka/helper.proxy

You can use this component to download files from Yandex.Disk.

To use `@yandex-toloka/helper.proxy`, connect Yandex.Disk to your Toloka account and add the proxy by following [the instructions](https://toloka.ai/docs/guide/concepts/prepare-data.html).

Select the component that you want to add, such as [view.image](view.image.md) for an image or [view.audio](view.audio.md) for an audio file. In the `url` property of this component, select the `@yandex-toloka/helper.proxy` type.

[View example in the sandbox](https://clck.ru/SVRpe).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "@yandex-toloka/helper.proxy"                                                    | <p>Set component type</p>                                                                  |
| `path`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Path to the file in the `/&lt;Proxy name&gt;/&lt;File name&gt;.&lt;type&gt;` format</p> |
