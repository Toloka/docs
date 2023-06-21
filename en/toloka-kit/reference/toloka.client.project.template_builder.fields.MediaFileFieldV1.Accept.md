# Accept
`toloka.client.project.template_builder.fields.MediaFileFieldV1.Accept` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/fields.py#L359)

```python
Accept(
    self,
    *,
    file_system: Optional[Union[BaseComponent, bool]] = None,
    gallery: Optional[Union[BaseComponent, bool]] = None,
    photo: Optional[Union[BaseComponent, bool]] = None,
    video: Optional[Union[BaseComponent, bool]] = None
)
```

A choice of buttons for uploading media files from different sources.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`file_system`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Files from a file manager.</p>
`gallery`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Files from a gallery.</p>
`photo`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Taking photos.</p>
`video`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Taking videos.</p>
