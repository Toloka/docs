# YandexDiskProxyHelperV1
`toloka.client.project.template_builder.helpers.YandexDiskProxyHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/project/template_builder/helpers.py#L288)

```python
YandexDiskProxyHelperV1(
    self,
    path: Optional[Union[BaseComponent, str]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

You can use this component to download files from Yandex&#160;Disk.


To use YandexDiskProxyHelper, connect Yandex&#160;Disk to your Toloka account and add the proxy by following
the [instructions](https://toloka.ai/en/docs/guide/concepts/prepare-data)
Select the component that you want to add, such as view.image for an image or view.audio for an audio file.
In the url property of this component, use YandexDiskProxyHelper.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`path`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>Path to the file in the &lt;Proxy name&gt;/&lt;File name&gt;.&lt;type&gt; format</p>
