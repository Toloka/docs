# MediaFileFieldV1
`toloka.client.project.template_builder.fields.MediaFileFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/fields.py#L332)

```python
MediaFileFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    accept: Optional[Union[BaseComponent, Accept]] = None,
    *,
    multiple: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for uploading media files.


For more information, see [field.media-file](https://toloka.ai/docs/template-builder/reference/field.media-file).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`accept`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Accept](toloka.client.project.template_builder.fields.MediaFileFieldV1.Accept.md)\]\]**|<p>Selecting file sources. Every source adds an upload button.</p>
`multiple`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`True` — Multiple files can be uploaded.</li> <li>`False` — A single file can be uploaded.</li> </ul> <p></p><p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>

**Examples:**

A component for uploading an image or taking a photo.

```python
image_loader = tb.fields.MediaFileFieldV1(
    label='Upload a photo',
    data=tb.data.OutputData(path='image'),
    validation=tb.conditions.RequiredConditionV1(),
    accept=tb.fields.MediaFileFieldV1.Accept(photo=True, gallery=True),
    multiple=False
)
```
