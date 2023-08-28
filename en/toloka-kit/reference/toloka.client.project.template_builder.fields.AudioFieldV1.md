# AudioFieldV1
`toloka.client.project.template_builder.fields.AudioFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L74)

```python
AudioFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    multiple: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for recording audio.


For more information, see [field.audio](https://toloka.ai/docs/template-builder/reference/field.audio).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`multiple`|**Optional\[Any\]**|<ul> <li>`True` — Multiple audio files can be recorded or uploaded.</li> <li>`False` — A single file can be recorded or uploaded.</li> </ul> <p></p><p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
